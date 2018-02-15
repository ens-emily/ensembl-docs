# Multiple genome alignments

Multiple alignments are calculated between groups of genomes. These are used to calculate [ancestral sequences](ancestral_sequences.md), [age of base](age_of_base.md), [conservation scores and constrained elements](conservation_and_constrained.md).

## Alignments available

[[SCRIPT::EnsEMBL::Web::Document::HTML::Compara::format_wga_table()]]

## Alignment methods

### PECAN Multiple Alignment

[Pecan](http://hgwdev.cse.ucsc.edu/~benedict/code/Pecan.html) is used to provide global multiple genomic alignments. First, Mercator is used to build a synteny map between the genomes and then Pecan builds alignments in these syntenic regions.

Pecan is a global multiple sequence alignment program that makes practical the probabilistic consistency methodology for significant numbers of sequences of practically arbitrary length. As input it takes a set of sequences and a phylogenetic tree. The parameters and heuristics it employs are highly user configurable, it is written entirely in Java and also requires the installation of Exonerate.

### EPO Multiple Alignment

The [EPO (Enredo, Pecan, Ortheus) pipeline](EPO_pipeline.md) is a three step pipeline for whole-genome multiple alignments.
1. Enredo produces colinear segments from extant genomes handling both rearrangements, deletions and duplications.
2. Pecan, as described above, is used to align these segments.
3. Finally, Ortheus is used to create genome-wide ancestral sequence reconstructions.

Further details on these methods can be found at: [Enredo and Pecan: Genome-wide mammalian consistency-based multiple alignment with paralogs](http://europepmc.org/abstract/MED/18849524)

Due to difficulties with running Ortheus on the fragmented assemblies, we have two flavours of the pipeline.
1. The plain EPO pipeline is available on the chromosome-level genomes, listed as EPO in the table above
2. The scaffold-level genomes are then projected onto the EPO alignments using LastZ-net alignments, listed as EPO_LOW_COVERAGE.

By construction, each pair of EPO and EPO_LOW_COVERAGE alignments represent the exact same alignment of chromosome-level genomes.

### Progressive Cactus

Progressive-Cactus is a next-generation aligner that stores whole-genome alignments in a graph structure. Genomes can be added incrementally, which makes it scalable to hundreds of genomes. Further details on these methods can be found in [Algorithms for genome multiple sequence alignment](http://europepmc.org/articles/PMC3166836) and [Cactus graphs for genome comparisons](http://europepmc.org/abstract/MED/21385048).
