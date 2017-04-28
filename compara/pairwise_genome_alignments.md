# Pairwise whole genome alignments

[LastZ](http://www.bx.psu.edu/~rsharris/lastz/) and its predecessor [Bla](http://europepmc.org/articles/PMC430961)[stZ](http://europepmc.org/articles/PMC208784) are used to align the genome sequences at the DNA level. The actual whole-genome alignments are the results of post-processing the raw LastZ (or BlastZ) results. In the first step, original blocks are chained according to their location in both genomes. The netting process chooses for the reference species the best sub-chain in each region.

In self-alignment analyses, the trivial alignments (i.e. regions against themselves) are removed, such that only the paralogous regions remain.

When both species have a chromosome-level assembly, we summarise the LastZ-net alignment blocks into syntenic regions. We look for stretches where the alignment blocks are in synteny. The search is run in two phases. In the first one, syntenic alignments that are closer than 200 kbp are grouped. In the second phase, the groups that are in synteny are linked provided that no more than 2 non-syntenic groups are found between them and they are less than 3Mbp apart.

Here is the list of all the pairwise comparisons that are available:

[Table like]

Species | Human | Mouse | Chimp | etc
--- | --- | --- | --- | ---
Human | [doc link] | [doc link] | [doc link] | etc
Mouse | [doc link] | [doc link] | [doc link] | etc
Chimp | [doc link] | [doc link] | [doc link] | etc
etc | | [doc link] | [doc link] | [doc link] | etc
