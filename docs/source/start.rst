Getting started
=====

.. _installation:

Preparing the input files
------------

TSSpredator can be run either analyse TSS data derived from one bacterial organism
to compare di erent conditions or from several di erent bacterial organisms to compare
di erent strains/species.
Comparison of di erent strains/species For this case, a multiple genome alignment
of the genomes studied needs to be precomputed. We recommend to compute this
using progressive Mauve (available from #<http://darlinglab.org/mauve/user-guide/progressivemauve.html>). It saves the alignment in an xmfa  le format, which is then
loaded into TSSpredator.
For each analysed organism, TSSpredator needs the genome  le in fastA format.
These need to be the identical fastA  les that were used for the multiple genome
alignment. In addition TSSpredator is able to use an annotation  le in g  or gtf
format for each genome in order to classify found TSS. Please make sure that the
identi er of the header in the annotation  le is written after ##Type DNA identifier or
##sequence-region identifier.
To use Lumache, first install it using pip:

.. code-block:: console

	(.venv) $ pip install lumache

Identifier coherence
----------------

One important issue before starting TSSpredator is to check the input data for the
used identi er. The genome fastA  le(s), the respective g  annotation  le(s) and all
wiggle  les should have the same identi er in the header. The following example shows,
how it can look like:

To retrieve a list of random ingredients,
you can use the ``lumache.get_random_ingredients()`` function:

.. autofunction:: lumache.get_random_ingredients

The ``kind`` parameter should be either ``"meat"``, ``"fish"``,
or ``"veggies"``. Otherwise, :py:func:`lumache.get_random_ingredients`
will raise an exception.

.. autoexception:: lumache.InvalidKindError

For example:

>>> import lumache
>>> lumache.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']

Overview
----------------

There are two ways to use TSSpredator. The most convenient way is to use its graph-
ical user interface (GUI), which is described in section 5. Here, all settings and parameters
can be speci ed that are needed for the prediction. For a detailed description of the
parameters see section 6. After setting up the study the con guration can be saved. Pressing
the RUN button starts the prediction procedure. All results are saved in the speci ed
output folder. The most important result  le is the Master Table (MasterTable.tsv ). For
a detailed description of all result  les see section 7.
Another way to utilize TSSpredator is via its command line interface. This
is especially useful for automatization or integration in an analysis pipeline. For this,
TSSpredator has to be started with a single argument, which is the path of a configuration
file (e.g. called 'config.conf', as it is saved by TSSpredator's GUI. For example:

.. code-block:: console

	java -Xmx1G -jar TSSpredator.jar config.conf
