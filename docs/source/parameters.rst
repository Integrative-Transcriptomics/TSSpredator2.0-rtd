Settings and Parameters
=========================

Study Setup
-------------

**Project Name** Enter a name for the study.
Type of Study Choose between *Comparison of different conditions* and *Comparison
of different strains/species*.
For a cross-strain analysis an Alignment file has to be provided (see below). In addition,
in each genome tab an individual genomic sequence and genome annotation has to be set.
When comparing different conditions no alignment file is needed and the genomic sequence
and genome annotation of the organism has to be set in the first genome tab only.

**Number of Genomes** Set the number of di erent strains/conditions in the study.
Press the 'Set' button to generate a settings tab for each strain/condition and each replicate
of the study.

**Number of Replicates** Set the number of different replicates for each strain/condition.
Press the 'Set' button to generate a settings tab for each strain/condition and each replicate
of the study.

**Output Data Path** Select the folder in which all result files will be placed.

**Alignment File** Select the xmfa alignment file containing the aligned genomes. If the
study compares different conditions, this field is inactive.

TSS prediction parameters
--------------------------
In the following the parameters a ecting the TSS prediction procedure are described.
Instead of changing the parameters manually it is also possible to select prede ned parameters
sets using the parameter presets drop-down menu.

**step height** This value relates to the minimal number of read starts at a certain genomic
position to be considered as a TSS candidate. To account for di erent sequencing depths
this is a relative value based on the 90th percentile of the expression height distribution.
A lower value results in a higher sensitivity.

**step height reduction** When comparing di erent strains/conditions and the step
height threshold is reached in at least one strain/condition, the threshold is reduced
for the other strains/conditions by the value set here. A higher value results in a higher
sensitivity. Note that this value must be smaller than the step height threshold.

**step factor** This is the minimal factor by which the TSS height has to exceed the local
expression background. This feature makes sure that a TSS candidate has to show a
higher expression in regions of locally high expression than would be necessary in regions
where no expression background is detected. A lower value results in a higher sensitivity.
Set this value to 1 to disable the consideration of the local expression level.

**step factor reduction** When comparing di erent strains/conditions and the step factor
threshold is reached in at least one strain/condition, the threshold is reduced for the other
strains/conditions by the value set here. A higher value results in a higher sensitivity.
Note that this value must be smaller than the step factor threshold.

**enrichment factor** The minimal enrichment factor for a TSS candidate. The threshold
has to be exceeded in at least one strain/condition. If the threshold is not exceeded in
another condition the TSS candidate is still marked as detected but not as enriched in
this strain/condition. A lower value results in a higher sensitivity. Set this value to 0 to
disable the consideration of the enrichment factor.

**processing site factor** The maximal factor by which the untreated library may be
higher than the treated library and above which the TSS candidate is considered as
a processing site and not annotated as detected. A higher value results in a higher
sensitivity.

**step length** Minimal length of the TSS related expression region (in base pairs). This
value depends on the length of the reads that are stacking at the TSS position. In most
cases this feature can be disabled by setting it to '0'. However, it can be useful if RNA-seq
reads have been trimmed extensively before mapping.

**base height** This value relates to the minimal number of reads in the non-enriched
library that start at the TSS position. This feature is disabled by default.

Normalization Settings
-----------------------

**normalization percentile** By default a percentile normalization is performed on the
RNA-seq data. This value defines the percentile that is used as a normalization factor.
Set this value to '0' to disable normalization.

**enrichment normalization** percentile By default a percentile normalization is performed
on the enrichment values. This value defines the percentile that is used as a
normalization factor. Set this value to '0' to disable normalization.

Output options
---------------

**write RNA-seq graphs** If this option is enabled, the normalized RNA-seq graphs are
written into the output folder. Disable this option, if the normalized graphs are not
needed or if they have been written before. Note that writing the graphs will increase the
runtime.

TSS Clustering Settings
------------------------

**cluster method** TSS candidates in close vicinity are clustered and only one of the
candidates is kept. HIGHEST keeps the candidate with the highest expression. FIRST
keeps the candidate that is located most upstream.

**TSS clustering distance** This value determines the maximal distance (in base pairs)
between TSS candidates to be clustered together. Set this value to '0' to disable clustering.

Comparative Settings
--------------------

**allowed cross-genome/condition shift** This is the maximal positional difference (bp)
for TSS candidates from different strains/conditions to be assigned to each other.

**allowed cross-replicate shift** This is the maximal positional difference (bp) for TSS
candidates from different replicates to be assigned to each other.

**matching replicates** This is the minimal number of replicates in which a TSS candidate
has to be detected. A lower value results in a higher sensitivity.

Classification Settings
------------------------
**UTR length** The maximal upstream distance (in base pairs) of a TSS candidate from
the start codon of a gene that is allowed to be assigned as a primary or secondary TSS
for that gene.

**antisense UTR length** The maximal upstream or downstream distance (in base pairs)
of a TSS candidate from the start or end of a gene to which the TSS candidate is in
antisense orientation that is allowed to be assigned as an antisense TSS for that gene. If
the TSS is located inside the coding region on the antisense strand it is also annotated as
an antisense TSS.

Genome specific Settings
------------------------

**Name** Brief unique name for this strain/condition, which can be freely chosen. As this
name is also used in some filenames any special characters (including spaces) should be
avoided.

**Alignment ID** The identifier of this genome in the alignment file. If Mauve was used
to align the genomes, the identifiers are just numbers assigned to the genomes in the
order as they have been chosen as input in Mauve.

The first lines of the alignment file should also contain this information:

.. code-block:: console

	#FormatVersion Mauve1
	#Sequence1File genomeA.fa
	#Sequence1Format FastA
	#Sequence2File genomeB.fa
	#Sequence2Format FastA
	
In this example `genomeA' has ID 1 and `genomeB' has ID 2.
When loading an alignment file (xmfa) TSSpredator tries to set the alignment IDs
automatically.

**genome FASTA** FASTA file containing the genomic sequence of this genome.

**genome annotation** GFF/GTF file containing genomic annotations for this genome
(as can be downloaded from NCBI).

**output ID** The specified output ID defines which gene tag in the attributes column
(in the provided gff annotation file) should be used for TSS classification. Examples are
`locus tag' or `gene id'.


Graph Files
------------

**enriched plus** Select the file containing the RNA-seq expression graph for the plus
strand (forward) from the 5' enrichment library.

**enriched minus** Select the file containing the RNA-seq expression graph for the minus
strand (reverse) from the 5' enrichment library.

**normal plus** Select the file containing the RNA-seq expression graph for the plus strand
(forward) from the library without 5' enrichment.

**normal minus** Select the file containing the RNA-seq expression graph for the minus
strand (reverse) from the library without 5' enrichment.