# Species trees

The Compara pipelines use two main species trees.

1.  The [NCBI taxonomy](http://www.ncbi.nlm.nih.gov/Taxonomy/taxonomyhome.html/) (i.e. topology only) in:
    *   the [Protein-trees](/info/genome/compara/homology_method.html) pipeline
    *   the [ncRNA-trees](/info/genome/compara/ncRNA_methods.html) pipeline, where the three sub-trees _Eutheria_, _Sauria_, and _Clupeocephala_ are flattened
    *   the CAFE pipelines (Gene Gain/Loss trees), with branch lengths coming from [the TimeTree database](http://www.timetree.org)
2.  A tree with branch-lengths computed in-house with [Mash](https://github.com/Ensembl/ensembl-compara/blob/release/[[SPECIESDEFS::ENSEMBL_VERSION]]/scripts/pipeline/species_tree.ensembl.branch_len.nw) in:
    *   the [Multiple-alignment](/info/genome/compara/multiple_genome_alignments.html) pipelines
    *   the [Constrained Elements / Conservation Scores](/info/genome/compara/conservation_and_constrained.html) pipelines
