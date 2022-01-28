Methods
======

.. _normalization:

Normalization
------------
Before the comparative analysis we normalize the expression graph data that is used
as input. A percentile normalization step is applied to normalize the graphs from the
enriched library. For this the 90th percentile (default, see normalization percentile) of all
data values is calculated for each graph of a treated library. This value is then used to
normalize this graph as well as the respective graph of the untreated library. Thus, the
relative di erences between each pair of libraries (treated and untreated) are not changed
in this normalization step. All graphs are multiplied with the overall lowest value to
restore the original data range.
To account for di erent enrichment rates a further normalization step is applied. During
this step a prediction of TSS candidates is performed for each strain/condition. These
candidates are then used to determine the median enrichment factor for each library pair
(default, see enrichment normalization percentile). Using these medians all untreated
libraries are then normalized against the library with the strongest enrichment.

The SuperGenome
-----------

To be able to assign TSS that have been detected in di erent genomes to each other
TSSpredator computes a common coordinate system for the genomes. This is done on
the basis of a whole-genome alignment. For the generation of whole-genome alignments
the software Mauve can be used, for example. It is able to detect genomic rearrangements
and builds multiple whole-genome alignments as a set of collinearly aligned blocks. The
resulting xmfa  le is then read by TSSpredator and the alignment information in the
blocks is used to calculate a joint coordinate system for the aligned genomes and mappings
between this coordinate system and the original genomic coordinates. In addition
to the cross-genome comparison of detected TSS this allows for an alignment of RNA-seq 
expression graphs, which can then be visualized in a genome browser. If different experimental
conditions are compared with the same genome, the SuperGenome construction
step is skipped (see Type of Study setting).

TSS prediction
-------

The initial detection of TSS in the single strains/conditions is based on the localization
of positions, where a signi cant number of reads start. Thus, for each position i in
the RNA-seq graph corresponding to the treated library the algorithm calculates e(i)-e(i-1), where e(i) is the expression height at position i. In addition, the factor of
height change is calculated, i.e. e(i)/e(i-1). To evaluate if the reads starting at this
position are originating from primary transcripts the enrichment factor is calculated as
e*treated*(i)/e*untreated*(i). For all positions where these values exceed the threshold a TSS
candidate is annotated. If the TSS candidate reaches the thresholds in at least one
strain/condition the thresholds are decreased for the other strains/conditions. We declare
a TSS candidate to be enriched in a strain/condition if the respective enrichment factor
reaches the respective threshold. A TSS candidate has to be enriched in at least one
strain/condition and is discarded otherwise. If a TSS candidate does not appear to be
enriched in a strain/condition but still reaches the other thresholds it is only indicated
as detected. However, a TSS candidate can only be labeled as detected in a condition
if its untreated expression value does not exceed its treated expression value by a factor
higher than the chosen processing site factor. Otherwise we consider it to be a processing
site. TSS candidates that are in close vicinity (TSS cluster distance) are grouped into a
cluster and by default only the TSS candidate with the highest expression is kept (see
cluster method). The  nal TSS annotations are then characterized with respect to their
occurrence in the di erent strains/conditions and in which strain/condition they appear
to be enriched. The TSS are then further classi ed according to their location relative to
annotated genes. For this we used a similar classification scheme as previously described
[1]. Thus for each TSS it is decided if it is the primary or secondary TSS of a gene, if
it is an internal TSS, an antisense TSS or if it cannot be assigned to one of these classes
(orphan). A TSS is classifed as primary or secondary if it is located upstream of a gene
not further apart than the chosen UTR length. The TSS with the strongest expression
considering all conditions is classified as primary. All other TSS that are assigned to
the same gene are classified as secondary. Internal TSS are located within an annotated
gene on the sense strand and antisense TSS are located inside a gene or within a chosen
maximal distance (antisense UTR length) on the antisense strand. These assignments are
indicated by a 1 in the respective column of the MasterTable. Orphan TSS, which are
not in the vicinity of an annotated gene, are indicated by zeros in all four columns.


