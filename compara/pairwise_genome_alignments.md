# Pairwise whole genome alignments

[LastZ](http://www.bx.psu.edu/~rsharris/lastz/) and its predecessor [Bla](http://europepmc.org/articles/PMC430961)[stZ](http://europepmc.org/articles/PMC208784) are used to align the genome sequences at the DNA level. The actual whole-genome alignments are the results of post-processing the raw LastZ (or BlastZ) results. In the first step, original blocks are chained according to their location in both genomes. The netting process chooses for the reference species the best sub-chain in each region.

In self-alignment analyses, the trivial alignments (i.e. regions against themselves) are removed, such that only the paralogous regions remain.

Here is the list of all the pairwise comparisons that are available:

[Table like below with search facets for species]

Species | Human | Mouse | Chimp | etc
--- | --- | --- | --- | ---
Human | [doc link] | [doc link] | [doc link] | etc
Mouse | [doc link] | [doc link] | [doc link] | etc
Chimp | [doc link] | [doc link] | [doc link] | etc
etc | | [doc link] | [doc link] | [doc link] | etc
