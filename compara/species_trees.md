# Species trees

The Compara pipelines use various species trees:

* The [protein trees](protein_trees.md) pipeline follows the [NCBI taxonomy](https://www.ncbi.nlm.nih.gov/Taxonomy/taxonomyhome.html/).
* The [ncRNA trees](ncRNA_trees.md) pipeline uses the NCBI taxonomy as a base and flattens the three following sub-trees: *Eutheria*, *Sauria*, and *Clupeocephala*.
* The CAFE pipelines (gene gain/loss trees) also follows the NCBI taxonomy, and use the [TimeTree database](http://www.timetree.org/) for the branch lengths.
* The [alignment pipelines](multiple_genome_alignment.md) follow a binary species tree that is [maintained in-house](https://github.com/Ensembl/ensembl-compara/blob/release/88/scripts/pipeline/species_tree.ensembl.topology.nw) (in accordance with the literature).
* The [constrained elements and conservation scores](conservation_and_constrained.md) pipelines need branch lengths, and we compute branch lengths for four sub-trees of the previous tree by running [phyloFit](http://compgen.cshl.edu/phast/) (part of the PHAST package) on our multiple alignments. They are available in Newick format: [mammals](https://github.com/Ensembl/ensembl-compara/blob/release/88/scripts/pipeline/species_tree.39mammals.branch_len.nw), [sauropsids](https://github.com/Ensembl/ensembl-compara/blob/release/88/scripts/pipeline/species_tree.7sauropsids.branch_len.nw), [amniotes](https://github.com/Ensembl/ensembl-compara/blob/release/88/scripts/pipeline/species_tree.23amniots.branch_len.nw), [fish](https://github.com/Ensembl/ensembl-compara/blob/release/88/scripts/pipeline/species_tree.11fish.branch_len.nw).
