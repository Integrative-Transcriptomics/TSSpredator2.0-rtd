Output
=========

.. _output:

Master Table (MasterTable.tsv)
-------------------------------

This table contains information on positions and class assignments of all automatically
annotated TSS. The table consists of the following columns:

**SuperPos** The position of the TSS in the SuperGenome.

**SuperStrand** The strand of the TSS in the SuperGenome.

**MapCount** Number of strains into which the TSS can be mapped. Separate entry lines
exist for each strain to which the TSS can be mapped whether the TSS was detected in
that strain or not.

**detCount** The number of strains/conditions in which this TSS was detected in the
RNA-seq data.

**Condition** The identifier of the strain/condition to which the rest of the line relates.

**detected** Contains a '1' if the TSS was detected in this strain/condition.

**enriched** Contains a '1' if the TSS is enriched in this strain/condition.

**stepHeight** The expression height change at the position of the TSS. This relates to
the number of reads starting at this position. (e(i) - e(i-1); e(i): expression height at
position i)

**stepFactor** The factor of height change at the position of the TSS. (e(i)/e(i-1); e(i):
expression height at position i)

**enrichmentFactor** The enrichment factor at the position of the TSS.

**classCount** The number of classes to which this TSS was assigned.

**Pos** Position of the TSS in that genome.

**Strand** Strand of the TSS in that genome.

**Locus tag** The locus tag of the gene to which the classi cation relates.

**Product** The product description of this gene.

**UTRlength** The length of the untranslated region between the TSS and the respective
gene (nt). (Only applies to 'primary' and 'secondary' TSS.)

**GeneLength** The length of the gene (nt).

**Primary** Contains a '1' if the TSS was classified as 'primary' with respect to the gene
stated in 'locusTag'.

**Secondary** Contains a '1' if the TSS was classified as 'secondary' with respect to the
gene stated in 'locusTag'.

**Internal** Contains a '1' if the TSS was classified as 'internal' with respect to the gene
stated in 'locusTag'.

**Antisense** Contains a '1' if the TSS was classified as 'antisense' with respect to the
gene stated in 'locusTag'.

**Automated** Contains a '1' if the TSS was detected automatically.

**Manual** Contains a '1' if the TSS was annotated manually.

**Putative sRNA** Contains a '1' if the TSS might be related to a novel sRNA. (Not
evaluated automatically)

**Putative asRNA** Contains a '1' if the TSS might be related to an asRNA.

**Sequence -50 nt upstream + TSS (51nt)** Contains the base of the TSS and the 50
nucleotides upstream of the TSS.

Supplemental Files
--------------------
** *strain* _super.fa** Contains the genome sequence of each strain mapped to the coordinate
system of the SuperGenome. All 4 files together actually contain the whole-genome
alignment. These files can be used in genome browsers that allow the user to load several
sequences simultaneously.

***strain*_super.gff**  Contains the gene annotations of each strain mapped to the coordinate
system of the SuperGenome.

***strain*_super*Type*Strand.gr** Contains the xy-graphs of each strain mapped to the
coordinate system of the SuperGenome. Type is either 'FivePrime' (treated) or 'Normal'
(untreated). Strand is either 'Plus' or 'Minus'. Note that the files now contain the value
0.0001 instead of 0 as a value of 0 (i.e. no entry line) now indicates a gap. This is necessary
for IGB's thresholding feature (see below).

**superTSS.gff**  Contains all TSS predicted in the four strains in the coordinate system
of the SuperGenome. Also all TSS that were only predicted in one strain are listed.
The information in how many strains (and in which) a TSS was detected is given in
superClasses.tsv. In the header line all parameter names and values which are used for
the run are reported.

**TSSstatistics.tsv** Contains some general statistics about the TSS prediction results.