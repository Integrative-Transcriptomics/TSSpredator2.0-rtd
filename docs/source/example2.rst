HowTo: example analysis with Campylobacter data
================================================

Quick step-by-step guide to use TSSpredator with the example data provided with the software.
The example data provided here is the multistrain Campylobacter data from Dugar et al., PLOS Genetics 9(5), 2013.

1. Open a Terminal and navigate to the folder with the TSSpredator jar file. Type:

.. code-block:: console
   java -jar TSSpredator-1.1beta.jar
    
   You can also try to start TSSpredator by a double-click on the **TSSpredator-1.1beta.jar** file.
   You will be asked for the memory to be allocated.
   Click the big button for an automated selection or choose a value.
   (For the full example data (4 strains, 2 replicates each) it is recommended to start the software with at least 1GB RAM).
	You can now choose to load the config file called *Campy.config* that is provided and continue with step 8 or you continue with the following steps 2-7.
	If you want to use the config file you need to adjust the paths in the config file to the correct paths on your computer. This can easily be done with a text editor.
   
2. Select an alignment file.
   In the upper right corner of the TSSpredator window
   you can choose an alignment file.
   Choose *alignment.xmfa*, which is in the **example-data/Campy-Data-multipleStrains folder**.
   You will be asked if the names and the number of genomes
   should be read from the file: click Yes.
   
3. Choose an output folder.
   In the upper right corner of the TSSpredator window
   you can choose an output folder,
   where all result files will be put.
   You can choose the **results** folder in **example-data/Campy-Data-multipleStrains**.
   
4. Set the number of replicates.
   In the upper left corner of the TSSpredator window
   you can set the number of replicates.
   For this example data, set this number to **2** and press **Set**.
   
5. You can also give a name to the Project in the upper left corner.

6. Load genomes, annotations.
   In the lower part of the TSSpredator window you will find a tab
   for each strain (genome) that was loaded from the alignment.
   In each tab load the respective files for the genomic sequence (fasta)
   and the genome annotation (GFF).
   The files can be found in **example-data/Campy-Data-multipleStrains** in the **fasta** and **gff** folders, respectively.
   
7. Load the RNA-seq data.
   In each tab you will also find two tabs for the RNA-Seq Graph Files
   (One for each replicate).
   The respective (wiggle) graph files can be found in **example-data/Campy-Data-multipleStrains**
   in the **graphs** folder.
   Each file name is set up as
   StrainName_R[1,2]_[enriched,normal]_RefseqID_[plus,minus].gr
   and can thus be easily identified.
   For example: *81-176_R1_enriched_NC_008787_minus.gr* denotes the graph file
   of strain 81-176 with the RefSeq-ID NC_008787, first replicate of the enriched library
   mapped to the minus strand.
   
8. Save the configuration.
   The configuration is now complete using standard parameters.
   If you want, you can save the configuration for later use
   by clicking the **Save** button in the lower left corner.
   
9. Start the detection procedure.
   Start the process by clicking the **RUN** button
   in the lower right corner.
   
10. View the results.
    An overview statistic will be shown at the end of the process
    in the message area (lower part of the TSSpredator window).
	Detailed results can be found in the output folder.
    The *MasterTable* contains detailed information on all predicted TSS.
    In *TSSstatistics.tsv* you can find a more detailed overview
    of TSS classifications.


