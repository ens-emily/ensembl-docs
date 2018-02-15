# Automatic annotation of non-coding genes

Non-coding RNAs (ncRNAs) are involved in many biological processes and are increasingly seen as important. As is the case with proteins, it is the overall structure of the molecule which imparts function. However, while similar protein structures are often reflected in a conserved amino acid sequence, sequences underlying RNA secondary structure are very variable; this makes ncRNAs difficult to detect using sequence alone.

## Types of ncRNA

| Abbreviation | Definition |
| --- | --- |
| tRNA | transfer RNA |
| Mt-tRNA | transfer RNA located in the mitochondrial genome |
| rRNA | ribosomal RNA |
| scRNA | small cytoplasmic RNA |
| snRNA | small nuclear RNA |
|snoRNA | small nucleolar RNA |
| miRNA | microRNA precursors |
| misc_RNA | miscellaneous other RNA |
| lincRNA | Long intergenic non-coding RNAs |

## Annotation Details

Most ncRNAs are annotated by aligning genomic sequence against [RFAM](http://rfam.xfam.org/) using [BLASTN](http://blast.wustl.edu/). The BLAST hits are clustered and filtered by E-value and are used to seed Infernal searches of the locus with the corresponding RFAM covariance models. The purpose of this is to reduce the search space required, as to scan the entire genome with all the RFAM covariance models would be extremely CPU-intensive. The resulting BLAST hits are then used as supporting evidence for ncRNA genes.

Some ncRNAs have specialised annotation.

### miRNAs

miRNAs are imported from [miRBase](http://www.mirbase.org/). All species are used.

### tRNAs

tRNAs are annotated as part of the raw compute process using [tRNAscan-SE](http://lowelab.ucsc.edu/tRNAscan-SE/). Because of this, they are not included as genes in the database, but as Simple Features instead.

### lincRNA

lincRNA (Long intergenic non-coding RNAs) Ensembl gene annotation, cDNA alignments and chromatin-state map data from the Ensembl regulatory build are used to predict lincRNAs for human and mouse. We do not import the lincRNAs identified by Guttman et al [1], but their publication guided us to our current approach for automatically annotating lincRNAs. First, regions of chromatin methylation (H3K4me3 and H3K36me3) outside known protein-coding loci are identified. Next, cDNAs which overlap with H3K4me3 or H3K36me3 features are identified as candidate lincRNAs. A final evaluation step investigates if each candidate lincRNA has any protein-coding potential. Any candidate lincRNA containing a substantial open reading frame (ORF) covering 35% or more of its length and containing PFAM/tigrfam protein domains will be rejected. Candidate lincRNAs that pass the final evaluation step are included in the human or mouse gene set as lincRNA genes.

References

Guttman M, Amit I, Garber M, French C, Lin MF, Feldser D, Huarte M, Zuk O, Carey BW, Cassady JP, Cabili MN, Jaenisch R, Mikkelsen TS, Jacks T, Hacohen N, Bernstein BE, Kellis M, Regev A, Rinn JL, Lander ES

[Chromatin signature reveals over a thousand highly conserved large non-coding RNAs in mammals.](http://europepmc.org/articles/PMC2754849)

Nature 2009 458:223-227
