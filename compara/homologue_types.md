# Homology types

Using the Gene Trees, we can infer the following pairwise relationships.

![Homologue types](tree_example1.png "Homologue types")

## Orthologues

Homologues which diverged by a speciation event. There are four types of orthologues:
* 1-to-1 orthologues (ortholog_one2one)
* 1-to-many orthologues (ortholog_one2many)
* many-to-many orthologues (ortholog_many2many)
* between-species paralogues – only as exceptions

Genes in different species and related by a speciation event are defined as **orthologues**. Depending on the number of genes found in each species, we differentiate among 1:1, 1:many and many:many relationships. Please, refer to the figure where there are examples of the three kinds.

## Paralogues

Homologues which diverged by a duplication event. There are two types of paralogues:
* same-species paralogies (within_species_paralog)
* fragments of the same ‐predicted‐ gene (gene_split)

Genes of the same species and related by a duplication event are defined as **paralogues**. In the previous figure, Hsap2 and Hsap2', and Mmus2 and Mmus2' are two examples of within species paralogues. The duplication event relating the paralogues does not need to affect this species only. For example, Mmus2' and Mmus3' are also within species paralogues but the duplication event has occurred in the common ancestor between species Hsap (human) and species Mmus (mouse). The taxonomy level "times" the duplication event to the ancestor of Euarchontoglires.

### Confidence scores

We compute a **duplication confidence score** for each duplication node. This is the [Jaccard index](https://en.wikipedia.org/wiki/Jaccard_index) of the sets of species under the two sub-trees. The score is sometimes refered as "species intersection score". 

![Duplication confidence scores](duplication_confidence_score.merged.41.png "Duplication confidence scores")

### Between species paralogues

A between species paralogue corresponds to a relation between genes of different species where the ancestor node has been labelled as a duplication node e.g. Mmus1:Hsap2 or Mmus1:Hsap3. Currently, we only annotate between species paralogue when there is no better match for any of the genes, and the duplication is weakly-supported (duplication confidence score ≤ 0.25).

Such cases can be the results of real duplications followed by gene losses (as shown in the picture below), but most of the times occur as the result of a wrong gene tree topology with a spurious duplication node. Often assembly errors are behind these problems. It is not clear whether these genes are real orthologues or not, but they are the best available candidates (given the data), and we bend the definition of orthology to tag them as orthologues. They are flagged as "non-compliant with the gene tree". People interested in phylogenetic analysis mixing the orthologies and the trees should probably use the set of tree-compliant orthologies. 

![Between species paralogues](tree_example2.png "Between species paralogues")

### Gene splits

A paralogue labelled as a gene_split occurs when a gene appears to be broken in two. In the [gene tree building process](protein_trees.md) they will each align to one end of the other orthologues of the gene, so will be clustered and placed in the tree alongside the other homologues. They are commonly related to fragmented genome assemblies or a gene prediction that is poor in supporting evidence, resulting in two fragmented genes where there should be one large one.

Right after building the multiple alignment, we detect pairs pairs of genes that lie close to each other (< 1 MB) in the same sequence region and the same strand (see GeneA1/GeneA2 below). They are forced to be paired in the gene trees under gene_split events, and represent our most confident set. When there is no (or little) overlap between the gene fragments in the same species and they lie in different sequence regions in the assembly (see GeneB1/GeneB2 in the image below), we let TreeBeST5 decide their best position in the tree. They are linked by duplication nodes, and have a lower confidence index. 

![Gene split](gene_split.png "Gene split")

## Confidence scoring

We carry a number of extra analyses to assess the quality of the orthology prediction, following external sources of evidence (local synteny, and whole-genome alignments). From there we are able to flag some orthologies as high-confidence. See [this document](orthology_quality_controls.md) for more information.
