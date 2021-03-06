# ncRNA trees

ncRNA trees are generated by a pipeline that uses a strategy similar to the one used for [protein trees](protein_trees.md), but adapted to the specific characteristics of ncRNAs. This is important because ncRNA genes are well known to form secondary structures where pairs of residues are matched to form loops and other structures. Substitution models that consider pairs of sites have been proposed and implemented in several packages like PHASE or [RAxML](http://europepmc.org/abstract/MED/16928733).

[diagram of tree building]

## Details on tree building

The ncRNA tree pipeline consists of the following steps:
1. Get and store ncRNA family models from [RFAM](http://rfam.xfam.org/).
2. Load and identify all the ncRNA members annotated in all the Ensembl genomes.
3. Filter out extra copies in low-coverage assemblies using our [EPO multiple alignments](multiple_genome_alignment.md).
4. Build secondary structure alignments using [INFERNAL](http://europepmc.org/articles/PMC2912718) and refinement of the covariance model.
5. Build ncRNA trees with [RAxML](http://europepmc.org/abstract/MED/16928733) using 16 different secondary structure models.
6. In parallel with the secondary structure alignments and trees, build multiple alignments with [PRANK](http://europepmc.org/articles/PMC3009689) with the genomic sequences of the ncRNAs. For these alignments we include the flanking region of the genes (twice the length of the gene at each side).
7. With the genomic alignments, build a neighbour-joining (NJ) and a maximum-likelihood (ML) tree using [TreeBeST](http://treesoft.sourceforge.net/treebest.shtml).
8. For very big families, build fast and efficient trees using [FastTree](http://europepmc.org/articles/PMC2835736) and [RAxML-Light](http://sco.h-its.org/exelixis/software.html).
9. For each family, add the species tree to the set of trees already obtained and reconcile them all using [TreeBeST](http://treesoft.sourceforge.net/treebest.shtml) obtaining one final tree for each family.

![Tree reconcilation](Tree_reconciliation.png "Tree reconcilation")

## References

[ncRNA orthologies in the vertebrate lineage. Miguel Pignatelli, Albert J. Vilella, Matthieu Muffato, Leo Gordon, Simon White, Paul Flicek, Javier Herrero. Database (Oxford) 2016 pii:bav127.](http://europepmc.org/articles/PMC4792531)
