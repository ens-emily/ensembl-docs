# Orthology quality-controls

We have two methods to provide quality scores for orthologue pairs:
* [Gene order conservation (GOC) score](#Gene_order_conservation_score)
* [Whole genome alignment score](#Whole_Genome_Alignment_score)

These methods are completely indepenent of each other and of the orthology inference itself. The scores can be used to determine how likely it is that the orthologue pairs are real.

## Gene order conservation score

Genes that are descended from the same gene are likely to be part of a block of genes, all in the same order, in both species. Some rearrangements between genes may occur over time, particularly in distantly related species, but it is less likely that an isolated gene which does not share gene neighbours with its inferred orthologue is a real orthologue.

The gene order conservation (GOC) score indicates how many of the four closest neighbours of a gene match between orthologous pairs. It is calculated by following these steps:
1. Load all the predicted orthologues for a pair of species.
2. Discard any orthologue that is by itself (usually in a scaffold). As these orthologues automatically get a NULL score for having no neighbours.
3. For each orthologous pair, fetch the two genes upstream and downstream, and check whether they are also identified as orthologues and in the same orientation.
4. Each match is scored as 25% meaning if all four neighbouring genes match that orthologue gets a GOC score of 100% for this species.
5. Go back to step three and repeat using the alternative species as the reference genome
6. Now we have two GOC scores for each other. We currently report the maximum of these scores

### Example comparison
![Example comparison](http://www.ensembl.org/info/genome/compara/ortholog_qc_goc_thumb.png "Example comparison")

Of the four neighbouring genes, three are orthologues and in conserved order and position, resulting in a GOC score of 75%.

### Availability
This pipeline on run on all bony vertebrates (Euteleostomi)

## Whole Genome Alignment score

We assume that genes which are orthologous to each other will fall within genomic regions that can be aligned to one another.

The pipeline that focuses on the nucleotide level mutations generates the whole genome alignment (WGA) score. It assumes that high-quality “true” orthologs should be well aligned to each other. This approach is based on the nucleotide level differences, taking advantage of the wealth of alignment information available through EnsEMBL’s comparative genetics analyses.

The main steps of this WGA pipeline are:
First, as the coverage over exonic regions is taken into account by this pipeline, exon boundaries are fetched for all genes in all species of interest. These are stored in a local table for efficiency gains later
Next, the species are paired off and all alignments between each pair are detected. All predicted orthologs between the pair are fetched and batched (default = 10)
The coverage over each member of the orthology is calculated using every available alignment. Coverage over exons is regarded as a higher importance than intronic regions, so a weighted score is generated. The score takes the coverage over exons as a base, with bonus points given for coverage over the introns (normalized by the proportion of intronic sequence in the gene). Scores for every alignment over both genes is stored in an intermediate table
Finally, an overall score for the homology prediction, as a whole is computed. This can be defined as the maximum score, after the score for the pair of genes has been averaged for each alignment i.e. we report the average score for the greatest-coverage alignment
Example comparison

ortholog_qc_wga
Availability
This pipeline on run on all LastZ and EPO alignments.

High-confidence orthologies

We have defined for several taxonomic groups stringent thresholds to flag orthologies as high-confidence. For each pair of species, we select the thresholds corresponding to their most-recent common ancestor. To be flagged as high-confidence, a pair of orthologue must have a sufficient %identity, and have a GOC score or WGA coverage greater or equal to the threshold. If none of the latter two metrics are available for this pair of species, we fall back to the tree-compliance metric explained in this document.

Clades	Min. GOC score	Min. WGA score	Min. %identity
Apes, Murinae	75	75	80
Mammalia, Aves, Percomorpha	75	75	50
Euteleostomi	50	50	25
Others	No threshold used	No threshold used	25
