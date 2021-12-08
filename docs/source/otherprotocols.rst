Other protocols
==========

.. _otherprotocols:

Cappable-Seq
-------------

Cappable-Seq was developed by Ettwiller et al. in 2016 for the directly capturing of the
5' end of primary transcripts [#FN2]_. Besides the Cappable-seq library a control library is
also prepared omitting the streptavidin capture step. Now TSSpredator can be ran
with Cappable-seq library as the enriched library and the control library as the normal
not enriched library.

TagRNA-Seq
-----------

TagRNA-seq is a modified RNA-seq method which is based on the differential labelling of
5' RNA ends, enabling the discrimination of primary from processed 5' RNA ends. Details
of the method can be found in the paper of Innocenti, N. et al. [#FN3]_. Using distinct sequence
tags for processed start sites (PSS) and transcription start sites (TSS) 5' RNA ends are
differentially labeled. Now prior alignment reads can be sorted by their tag sequences. To
use this data with TSSpredator the TSS reads should be used as the enriched library
and the PSS reads or PSS and unassigned reads as the normal unenriched library. Which
reads are better for using as the unenriched library is not confirmed yet.