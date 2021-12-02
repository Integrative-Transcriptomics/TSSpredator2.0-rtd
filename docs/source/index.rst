TSSpredator - A TSS prediction and classification tool
===================================

TSSpredator is a tool for the comparative detection of transcription start sites (TSS) from RNA-seq data. It can integrate data from different experimental conditions but also from different organisms on the basis of a multiple whole-genome alignment.

So far TSSpredator has been successfully applied to many data sets generated using the so-called dRNA-seq protocol by Sharma *et al.*, 2010 [#FN1]_. 
In addition we have started using it on RNA-seq data produced with the protocol by Ettwiller [#FN2]_ or Innocenti [#FN3]_.
In this UserGuide we will concentrate on dRNA-seq data, in section :doc:`otherprotocols` we will give a short overview of how to use TSSpredator on data produced by that protocols.

##**Lumache** (/lu'make/) is a Python library for #cooks and food lovers
#that creates recipes mixing random ingredients.
#It pulls data from the `Open Food Facts database #<https://world.openfoodfacts.org/>`_
#and offers a *simple* and *intuitive* API.

#Check out the :doc:`usage` section for further #information, including
#how to :ref:`installation` the project.

.. note::

   This project is under active development.

Contents
--------

.. toctree::

   usage
   start
   methods
   userinterface
   parameters
   output
   otherprotocols
   reademption
   
.. [#FN1] Cynthia M Sharma, Steve Hoffmann, Fabien Darfeuille, Jèrèmy Reignier, Sven Findeiß , Alexandra Sittka, Sandrine Chabas, Kristin Reiche, Jörg Hackermüller, Richard Reinhardt, et al. 
	*"The primary transcriptome of the major human pathogen Helicobacter pylori"* Nature, 464(7286):250, 2010.
.. [#FN2] Laurence Ettwiller, John Buswell, Erbay Yigit, and Ira Schildkraut. 
	*"A novel enrichment strategy reveals unprecedented number of novel transcription start sites at single base resolution in a model prokaryote and the gut microbiome"*. BMC genomics, 17(1):1{14, 2016.
.. [#FN3] Nicolas Innocenti, Monica Golumbeanu, Aymeric Fouquier d'H erouel,
Caroline Lacoux, R emy A Bonnin, Sean P Kennedy, Fran coise Wessner,
Pascale Serror, Philippe Bouloc, Francis Repoila, et al. "Whole-genome
mapping of 5 RNA ends in bacteria by tagged sequencing: a comprehensive
view in Enterococcus faecalis". Rna, 21(5):1018{1030, 2015.