# Homology types

Using the Gene Trees, we can infer the following pairwise relationships.

## Orthologues

Any gene pairwise relation where the ancestor node is a speciation event. We predict several descriptions of orthologues:
* 1-to-1 orthologues (ortholog_one2one)
* 1-to-many orthologues (ortholog_one2many)
* many-to-many orthologues (ortholog_many2many)
* between-species paralogies —only as exceptions, see below — (reusing the three orthology types above)

## Paralogues

Any gene pairwise relation where the ancestor node is a duplication event. We predict several descriptions of paralogues:
* same-species paralogies (within_species_paralog)
* fragments of the same ‐predicted‐ gene (gene_split)

Genes in different species and related by a speciation event are defined as orthologues. Depending on the number of genes found in each species, we differentiate among 1:1, 1:many and many:many relationships. Please, refer to the figure where there are examples of the three kinds.

Genes of the same species and related by a duplication event are defined as paralogues. In the previous figure, Hsap2 and Hsap2', and Mmus2 and Mmus2' are two examples of within-species-paralogs. The duplication event relating the paralogues does not need to affect this species only. For example, Mmus2' and Mmus3' are also within_species_paralog but the duplication event has occurred in the common ancestor between species Hsap (human) and species Mmus (mouse). The taxonomy level "times" the duplication event to the ancestor of Euarchontoglires.

We compute a duplication confidence score for each duplication node as the Jaccard index of the sets of species under the two sub-trees. The score is sometimes refered as "species intersection score". 
duplication_confidence_score.merged.41.png

A between_species_paralog corresponds to a relation between genes of different species where the ancestor node has been labelled as a duplication node e.g. Mmus1:Hsap2 or Mmus1:Hsap3. Currently, we only annotate between_species_paralog when there is no better match for any of the genes, and the duplication is weakly-supported (duplication confidence score ≤ 0.25).

Such cases can be the results of real duplications followed by gene losses (as shown in the picture below), but most of the times occur as the result of a wrong gene tree topology with a spurious duplication node. Often times, assembly errors are behind these problems. It is not clear whether these genes are real orthologs or not, but they are the best available candidates (given the data), and we bend the definition of orthology to tag them as orthologues. They are flagged as "non-compliant with the gene tree". People interested in phylogenetic analysis mixing the orthologies and the trees should probably use the set of tree-compliant orthologies. 
tree_example2

A paralogue labelled as a gene_split is an artefactual type of paralogy. It is commonly related to fragmented genome assemblies or a gene prediction that is poor in supporting evidences (cDNA, ESTs, proteins, etc.). Right after building the multiple alignment, we detect pairs pairs of genes that lie close to each other (<1MB) in the same sequence region and the same strand (see GeneA1/GeneA2 below). They are forced to be paired in the gene trees under gene_split events, and represent our most confident set. When there is no (or little) overlap between the gene fragments in the same species and they lie in different sequence regions in the assembly (see GeneB1/GeneB2 in the image below), we let TreeBeST5 decide their best position in the tree. They are linked by duplication nodes, and have a lower confidence index. 
gene split

We carry a number of extra analyses to assess the quality of the orthology prediction, following external sources of evidence (local synteny, and whole-genome alignments). From there we are able to flag some orthologies as high-confidence. See this document for more information.
