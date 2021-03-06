User Interface
===============

.. _userinterface:

See :ref:`figGUI` for the explanation of the GUI of TSSpredator.




**Study setup** In the study setup area (:ref:`figGUI` A) general settings for the study can be
made. Most importantly these are the type of the study (comparison of strains (requires
alignment file) or conditions), the number of genomes/conditions and replicates, and the
path to the output directory. A project name can also be specified.

**Parameter area** In the parameter area (:ref:`figGUI` B) specific parameters of the TSS
prediction procedure can be changed. Instead of changing individual parameters it is also
possible to select a parameter preset from the drop-down menu.

**Genome/Condition related settings** For each genome/condition of the study a tab
is generated (:ref:`figGUI` C), in which settings specific for this genome/condition can be made.
This includes the name and ID, and file paths to the genomic sequence (FASTA) and the
genome annotation (GFF). In addition, for each replicate a tab is displayed within the
respective genome/condition tab, where the RNA-seq wiggle files of the replicate can be
entered. If only fastq files are available instead of wiggle files, it is recommended to use
the READemption pipeline (see section :doc:`reademption` to generate them).

**Message Area** In the message area (:ref:`figGUI` D) information about a running prediction
process is displayed. Thus, it can be easily determined in which step a running prediction
procedure currently is. At the end of the procedure a brief summary is shown.

**Load/Save Configuration** Using the Save or Load button (:ref:`figGUI` E) a configuration
including all settings can be saved, or a previously saved configuration can be loaded,
respectively. Loading a configuration overwrites all current settings.

**Run prediction** By pressing the RUN button (:ref:`figGUI` F) the prediction procedure is
started using the current settings and parameters. Information about the running process
is displayed in the message area. The running prediction can be canceled using the Cancel
button. Note that this might result in incomplete output files.


.. _figGUI:

.. figure:: images/TSSpredatorgui.png
	:width: 200
	:align: center 
	
    Figure 4