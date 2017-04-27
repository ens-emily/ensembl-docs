# TreeFam HMM library

The TreeFam HMM library is based upon the [Panther database (version 9)](ftp://ftp.pantherdb.org//hmm_scoring/current_release). In order to define a common and comprehensive set of HMMs to be used across all the Ensembl divisions we added extra families defined in the [TreeFam database (version 9)](http://www.treefam.org/), and built new ones to model gene-families that were not previously described in either databases.

## Species coverage

The gene models used in this study come from the version 82 of Ensembl, and version 29 of Ensembl Genomes. We selected all the genomes used in the protein-tree analysis of these databases to maximize the coverage of the tree of life. We used sequences from 708 species, of which 313 fungi, 130 protists, 41 plants, 119 metazoans (incl. 64 chordates) and 105 bacteria.

## HMM library

The procedure to build the HMM library is described here:

1. We first removed the redundancy between Panther 9 and TreeFam 9. This was done by:
  1. Emitting consensus sequences from the 15,736 TreeFam 9 HMM profiles.
  2. Classifying them against the 7,181 Panther 9 profiles with PantherScore.
   As a result:
  * 13,638 TreeFam 9 families that had a hit on the Panther 9 profiles were discarded from the overall library.
  * 2,098 TreeFam families remained after this filter.

2. We classified all the available sequences (8,488,481) according to their scores to these HMM profiles using PantherScore.

3. We used [Mafft](http://mafft.cbrc.jp/alignment/software/) to align all these clusters.

4. We used [TrimAl](http://europepmc.org/articles/PMC2712344) and [Notung](http://europepmc.org/articles/PMC3436813) to estimate the quality of the alignments, and also computed metrics such as the percentage of gaps in the alignment. We identified a number of very large Panther families and decided to promote their sub-families HMMs (as defined in the Panther database) to the family rank in order to replace the Family HMM. After this step, the library is composed of 38,554 HMMs coming from Panther (5,103 from families, and 33,451 from sub-families).

5. We reclustered all the sequences against the new library.

6. Sequences that did not match any of the profiles were then clustered together with [hcluster_sg](https://sourceforge.net/p/treesoft/code/HEAD/tree/) (a hierarchical clustering software for sparse graphs) using a blast all-vs-all approach (see the [Protein tree pipeline documentation](protein_trees.md)).

7. Given the large number (404,108) of clusters we applied further filtering and quality-control checks. We used the following metrics and evaluated different thresholds:
  a. Taxonomic coverage (ratio of taxa present in a particular HMM profile vs all the taxa in our species tree) for each member in all the clusters.
  b. Minimum number of genes.
  c. Minimum number of species.
   Overall, filtering the clusters by the number of different species per family and per division turned out to be the clearest way of discarding very small clusters. We used these thresholds:
  a. Clusters with at least 3 different species for protists division only.
  b. Clusters with at least 5 different species for all other divisions.
   Out of the 404,108 clusters, only 128,233 passed these filters, of which 34,119 come from Panther 9, 1,451 from Treefam 9.

8. The new clusters (92,663) built with hcluster_sg that passed the filtering step were prefixed with TF6xxxxx in order to diferentiate them from previous TreeFam families.

9. We used Mafft to align all these clusters, and built HMM profiles on them. We calibrated most of the profiles (the calibration of a few very big alignments has failed)

## Statistics

Total number of families before filtering:	404,108
Total number of families after filtering:	128,233

Breakdown by source and nomenclature:

Panther v9:	34,119	PTHRxxxxx
TreeFam v9:	8	TF1xxxxx
1,443	TF3xxxxx
New clusters:	92,663	TF6xxxxx
