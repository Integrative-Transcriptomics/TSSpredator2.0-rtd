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
step height reduction When comparing di erent strains/conditions and the step
height threshold is reached in at least one strain/condition, the threshold is reduced
for the other strains/conditions by the value set here. A higher value results in a higher
sensitivity. Note that this value must be smaller than the step height threshold.
step factor This is the minimal factor by which the TSS height has to exceed the local
expression background. This feature makes sure that a TSS candidate has to show a
higher expression in regions of locally high expression than would be necessary in regions
where no expression background is detected. A lower value results in a higher sensitivity.
Set this value to 1 to disable the consideration of the local expression level.
step factor reduction When comparing di erent strains/conditions and the step factor
threshold is reached in at least one strain/condition, the threshold is reduced for the other
strains/conditions by the value set here. A higher value results in a higher sensitivity.
Note that this value must be smaller than the step factor threshold.
enrichment factor The minimal enrichment factor for a TSS candidate. The threshold
has to be exceeded in at least one strain/condition. If the threshold is not exceeded in
another condition the TSS candidate is still marked as detected but not as enriched in
this strain/condition. A lower value results in a higher sensitivity. Set this value to 0 to
disable the consideration of the enrichment factor.
processing site factor The maximal factor by which the untreated library may be
higher than the treated library and above which the TSS candidate is considered as
a processing site and not annotated as detected. A higher value results in a higher
sensitivity.
step length Minimal length of the TSS related expression region (in base pairs). This
value depends on the length of the reads that are stacking at the TSS position. In most
cases this feature can be disabled by setting it to '0'. However, it can be useful if RNA-seq
reads have been trimmed extensively before mapping.
base height This value relates to the minimal number of reads in the non-enriched
library that start at the TSS position. This feature is disabled by default.