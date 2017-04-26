# Comparative Genomics

Ensembl Compara provides cross-species resources and analyses, at both the sequence level and the gene level.


## Gene analyses

All Ensembl gene sequences are compared to one another in order to produce gene trees, infer homologues and produce gene families. These processes are different for coding and non-coding genes.

* [Protein trees and homologues](protein_trees_and_homologues.md)
* [ncRNA trees and homologues](ncRNA_trees_and_homologues.md)
* [Gene families](gene_families.md)
* [Orthologue quality scores](orthology_quality_controls.md)
* [Gene tree stable IDs](gene_tree_stable_id.md)


## Genome analyses

Whole genome alignments are produced, both pairwise alignments and multiple alignments. From these we calculate ancestral sequences, when bases were fixed, conservation scores, constrained elements and syntenies.

* [Pairwise alignments](pairwise_genome_alignments.md)
* [Multiple alignments](multiple_genome_alignments.md)
* [Ancestral sequences](ancestral_sequences.md)
* [Conservation scores and constrained elements](conservation_and_constrained.md)
* [Synteny](synteny.md)



## Species tree

The Compara pipelines use various species trees.

The Protein-trees pipeline follows the NCBI taxonomy.
The ncRNA-trees pipeline uses the NCBI taxonomy as a base and flattens the three following sub-trees: Eutheria, Sauria, and Clupeocephala.
The CAFE pipelines (Gene Gain/Loss trees) also follows the NCBI taxonomy, and use the TimeTree database for the branch lengths.
The Alignment pipelines follow a binary species tree that is maintained in-house (in accordance with the litterature). A Newick file representing this topology (without branch lengths) is on GitHub.
The Constrained Elements / Conservation Scores pipelines need branch lengths, and we compute branch lengths for 4 sub-trees of the previous tree by running phyloFit (part of the PHAST package) on our multiple alignments (see above). They are available in Newick format on GitHub: mammals, sauropsids, amniotes, fish.


## Access

Data can be accessed using the Compara Perl API, BioMart, or comparative genomics pages on the browser. Gene trees can be viewed from any 'Gene' page on the browser, and exported via the control panel and the Jalview plug-in in the pop-ups that appear when clicking on any part of the tree.

Please refer to the Compara FAQs or the Ensembl Helpdesk if you have further questions.
