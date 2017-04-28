# Synteny

[Synteny](https://en.wikipedia.org/wiki/Synteny) is the conserved order of aligned genomic blocks between species. It is calculated from the [pairwise genome alignments](pairwise_genome_alignments.md) created by Ensembl, when both species have a chromosome-level assembly.

The search is run in two phases:
1. We search for alignment blocks that are in the same order in the two genomes. Syntenic alignments that are closer than 200 kb are grouped into a synteny block.
2. Groups that are in synteny are linked, provided that no more than two non-syntenic groups are found between them and they are less than 3 Mb apart.

Here is the list of all the synteny comparisons that are available:

[Table like below with search facets for species]

Species | Human | Mouse | Chimp | etc
--- | --- | --- | --- | ---
Human | [doc link] | [doc link] | [doc link] | etc
Mouse | [doc link] | [doc link] | [doc link] | etc
Chimp | [doc link] | [doc link] | [doc link] | etc
etc | | [doc link] | [doc link] | [doc link] | etc
