HowTo: example analysis with S.aureus
===============================================

Quick step-by-step guide to use TSSpredator with the second example data provided at <https://uni-tuebingen.de/fakultaeten/mathematisch-naturwissenschaftliche-fakultaet/fachbereiche/informatik/lehrstuehle/integrative-transkriptomik/software/tsspredator/>
The example data provided here is the S. aureus data comparing wildtype and a knockout mutant.

1. Open a Terminal and navigate to the folder with the TSSpredator jar file. Type ``java -jar TSSpredator-1.1beta.jar ``

  .. autofunction:: java -jar TSSpredator-1.1beta.jar
  

   You can also try to start TSSpredator by a double-click on the TSSpredator-1.1beta.jar file.
   You will be asked for the memory to be allocated.
   Click the big button for an automated selection or choose a value. 
  
You can now choose to load the config file called **TSSpredator_Saureus.config** that is provided and continue with step 8 or you continue with the following steps 2-7.
If you want to use the config file you need to adjust the paths in the config file to the correct paths on your computer. This can easily be done with a text editor.

2. Choose an output folder.
   In the upper right corner of the TSSpredator window
   you can choose an output folder,
   where all result files will be put.
   You can choose the 'results' folder in 'example-data/Saureus-2Cond-2Repl/Archive/'.
   
3. Set the number of replicates.
   In the upper left corner of the TSSpredator window
   you can set the number of replicates.
   For this example data, set this number to '2' and press 'Set'.
   
4. You can also give a name to the Project in the upper left corner.

5. Load genomes, annotations.
   In the lower part of the TSSpredator window you will find a tab
   for each strain (genome) that was loaded from the alignment.
   In each tab load the respective files for the genomic sequence (fasta)
   and the genome annotation (GFF).
   The files can be found in 'example-data/Saureus-2Cond-2Repl/Archive/' in the 'genome_anno' folder.
   
6. Load the RNA-seq data.
   In each tab you will also find two tabs for the RNA-Seq Graph Files
   (One for each replicate).
   The respective (wiggle) graph files can be found in 'example-data/Saureus-2Cond-2Repl/Archive/S_aureus_coverages'
   folder.
   Each file name from the wildtype is set up as
   GM_SA_WT[2,3]_[plus,minus]_*_[forward,reverse]_in_NC_009641.1.grEach file name from the knockout is set up as
   GM_SA_rny[1,2]_[plus,minus]_*_[forward,reverse]_in_NC_009641.1.gr
   and can thus be easily identified.
   For example: "GM_SA_rny1_minus_TEX.fa_div_by_6538401.0_multi_by_5727088.0_forward.wig_GM_SA_rny1_minus_TEX.fa_forward_in_NC_009641.1"
   denotes the graph file
   of the any mutant, first replicate of the normal (non-enriched) library mapped to the forward strand.
   
7. Save the configuration.
   The configuration is now complete using standard parameters.
   If you want, you can save the configuration for later use
   by clicking the 'Save' button in the lower left corner.
   
8. Start the detection procedure.
   Start the process by clicking the 'RUN' button
   in the lower right corner.
   
9. View the results.
    An overview statistic will be shown at the end of the process
    in the message area (lower part of the TSSpredator window).
    Detailed results can be found in the output folder.
    The 'MasterTable' contains detailed information on all predicted TSS.
    In 'TSSstatistics.tsv' you can find a more detailed overview
    of TSS classifications.