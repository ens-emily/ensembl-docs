# Species trees

The Compara pipelines use various species trees.

The Protein-trees pipeline follows the NCBI taxonomy.
The ncRNA-trees pipeline uses the NCBI taxonomy as a base and flattens the three following sub-trees: Eutheria, Sauria, and Clupeocephala.
The CAFE pipelines (Gene Gain/Loss trees) also follows the NCBI taxonomy, and use the TimeTree database for the branch lengths.
The Alignment pipelines follow a binary species tree that is maintained in-house (in accordance with the litterature). A Newick file representing this topology (without branch lengths) is on GitHub.
The Constrained Elements / Conservation Scores pipelines need branch lengths, and we compute branch lengths for 4 sub-trees of the previous tree by running phyloFit (part of the PHAST package) on our multiple alignments (see above). They are available in Newick format on GitHub: mammals, sauropsids, amniotes, fish.
