# Age of base

From the calculated [ancestral sequences](ancestral_sequences.md), we infer the age of a base, i.e. the timing of the most recent mutation for each base of the genome. Each position of the genome is compared to its immediate inferred ancestor, then its ancestor, etc. until a difference is found. The inferred substitution event therefore occurred on a specific branch of the tree, which is identified by all the extant species which eventually descended from that branch, as illustrated below.

![Age of Base schema](http://www.ensembl.org/info/genome/compara/age_of_base.png "Age of base schema")

This track is currently only available for the human genome.
