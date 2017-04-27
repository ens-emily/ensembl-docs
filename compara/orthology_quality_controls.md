# Orthology quality controls

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
![Example GOC comparison](http://www.ensembl.org/info/genome/compara/ortholog_qc_goc_thumb.png "Example GOC comparison")

Of the four neighbouring genes, three are orthologues and in conserved order and position, resulting in a GOC score of 75%.

### Availability
This pipeline on run on all bony vertebrates (Euteleostomi)

## Whole genome alignment score

We assume that genes which are orthologous to each other will fall within genomic regions that can be aligned to one another. Since we calculate [pairwise whole genome alignments](pairwise_genome_alignments.md), we can use these to check the regions surrounding orthologues.

The whole genome alignment score calculates the coverage of the alignment over the orthologue pair, as follows:
1. Exon boundaries are fetched for all genes in all species of interest.
2. The species are paired off and all alignments between each pair are detected. All predicted orthologues between the pair are fetched.
3. The coverage over each member of the orthology is calculated using every available alignment. Coverage over exons is regarded as a higher importance than intronic regions, so a weighted score is generated. The score takes the coverage over exons as a base, with bonus points given for coverage over the introns (normalised by the proportion of intronic sequence in the gene).
4. An overall score for the homology prediction, as a whole, is computed. This can be defined as the maximum score, after the score for the pair of genes has been averaged for each alignment i.e. we report the average score for the greatest-coverage alignment.

### Example comparison
![Example WGA comparison](http://www.ensembl.org/info/genome/compara/ortholog_qc_wga_thumb.png "Example WGA comparison")

### Availability
This pipeline on run on all LastZ and EPO alignments.

## High confidence orthologies

Orthologue pairs may be tagged as high confidence if they meet certain thresholds for these two measures as well as identity. The thresholds we use depend on the most-recent common ancestor of the species pair, according to the table below. The orthologue pair must satisfy all the criteria to be tagged as high confidence.

Clades | GOC score threshold | WGA score threshold | % identity threshold
--- | --- | --- | ---
Apes, Murinae | 75 | 75 | 80
Mammalia, Aves, Percomorpha | 75 | 75 |50
Euteleostomi | 50 | 50 | 25
Others | No threshold used | No threshold used | 25
