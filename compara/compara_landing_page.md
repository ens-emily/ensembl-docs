# Comparative Genomics

Ensembl Compara provides cross-species resources and analyses, at both the sequence level and the gene level.


## Gene-based resources

We automatically integrate the gene annotations produced by the Ensembl genebuild team across all the species.

Phylogenetic trees

We compute phylogenetic trees across the whole set of protein-coding genes with one pipeline, and ncRNA genes with another. They both result in a set of trees that are visualized and accessed the exact same way. From both set of gene trees, we extract homologues (orthologues and paralogues). We also analyze the gene gain and loss events using the CAFE software.

Protein trees are constructed using a representative protein for every gene in Ensembl: proteins are clustered using hcluster_sg based on NCBI BLAST+ e-values, and each cluster of proteins is aligned using M-Coffee or Mafft. Finally, TreeBeST is used to produce a gene tree from each multiple alignment, reconciling it with the species tree to call duplication events. More information → Tree statistics →
ncRNA trees are constructed using gene families represented in RFAM, for which a specific covariance model is provided. For each gene family, we build several trees using secondary structure alignments with INFERNAL and genomic alignments with PRANK. All the trees are merged into a final tree using TreeBeST. More information → Tree statistics →
TreeFam Families

We also extend our gene-based resources to the whole set of Metazoan proteins from UniProtKB SwissProt and SPTREMBL in a resource named TreeFam Families. Briefly, the pipeline classifies all Ensembl proteins (potentially several per gene) and the above-mentionned set of UniProt proteins against the TreeFam HMM library. Clusters are then aligned with Mafft. More information →

Stable ID mapping

Ensembl Families and Protein Trees undergo a step of stable IDs mapping, that allows one to track the update of a tree or a family across releases. Please note that the mapping exclusively relates to the content, and not to the actual conservation of the alignment or tree topology. More information →. 
ncRNA trees can be naturally mapped across releases using their RFAM identifier.



## Sequence-based resources

Whole genome alignments

Sometimes abbreviated as WGA, they are performed either pairwise between two species, or using multiple species. Pairwise alignments are based on lastZ-net (although we have not recomputed all the previous BlastZ-net). In the past, we also generated translated-Blat alignments. Multiple alignments are mainly based on the EPO pipeline (extended to include fragmented genomes) and Mercator/Pecan. More information →

Following is the list of additional analysis that are applied on the whole-genome alignments:

Ancestral sequences

From the multiple alignments performed with the EPO pipeline, we can predict ancestral sequences for a number of ancestral taxa. More information →

Age of Base (Beta)

In turn, from these ancestral events, we estimate when mutation events occurred along the species tree. This experimental track is currently computed only for substitutions along the human lineage. More information →

Conservation scores and constrained elements

Additionally we use Gerp (Cooper GM et al., Genome Res., 2005; 15:901-913) to calculate conservation scores and call constrained elements on the Mercator/Pecan and EPO-2X multiple alignments. Conservation scores are estimated on a column-by-column basis. Constrained elements are stretches of the multiple alignment where the sequences are highly conserved according to the previous score.

Syntenies

Finally, we can derive synteny mappings from the pairwise alignments of species whose genome assembly is not too fragmented. More information →



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
