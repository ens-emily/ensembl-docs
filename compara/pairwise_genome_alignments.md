# Pairwise whole genome alignments

Pairwise whole genome alignments can be used to determine conservation or differences between pairs of species, or to match up regions between species, so as to study the same genomic region in multiple species.

[LastZ](http://www.bx.psu.edu/~rsharris/lastz/) and its predecessor [Bla](http://europepmc.org/articles/PMC430961)[stZ](http://europepmc.org/articles/PMC208784) are used to align the genome sequences at the DNA level.

Genomes are compared to one another, for comparison between species, and to themselves, to identify paralogous regions. In self-alignment analyses, the trivial alignments (i.e. regions against themselves) are removed, such that only the paralogous regions remain.

The actual whole-genome alignments are the results of post-processing the raw LastZ (or BlastZ) results. In the first step, original blocks are chained according to their location in both genomes. The netting process chooses for the reference species the best sub-chain in each region.

These alignments are used to calculate [synteny](synteny.md) and for [scoring orthologue quality](orthology_quality_controls.md).

## Alignments available

[[SCRIPT::EnsEMBL::Web::Document::HTML::Compara::BlastZ]]
