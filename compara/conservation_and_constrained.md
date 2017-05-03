# Conservation scores and constrained elements

We use [GERP](http://mendel.stanford.edu/SidowLab/downloads/gerp/) to calculate conservation scores and call constrained elements on the amniota vertebrate Pecan, mammals EPO_LOW_COVERAGE, fish EPO_LOW_COVERAGE and sauropsids EPO_LOW_COVERAGE [multiple alignments](multiple_genome_alignment.md). Calculation of these scores for different species groups allows the determination of regions that are conserved in one taxon but not another.

## Conservation scores
Conservation scores are calculated per base, indicating how many species in a given multiple alignment match at each locus.

## Constrained elements
Constrained elements are stretches of the multiple alignment where the sequences are highly conserved according to the previous score. This is done using GERP, which uses a permutation test to identify specific segments of the alignment that appear to be more conserved than expected by random chance.
