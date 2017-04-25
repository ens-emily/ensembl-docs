# Gene annotation in Ensembl

Gene annotation is the plotting of genes onto genome assemblies, and indexing their genomic coordinates.

Gene annotation provided by Ensembl includes automatic annotation, ie genome-wide determination of transcripts. For selected species (ie human, mouse, zebrafish, pig, rat), gene annotation may also include manual curation, ie reviewed determination of transcripts on a case-by-case basis. Furthermore, Ensembl imports annotation from FlyBase, WormBase and SGD.

Ensembl transcripts displayed on our website are products of the Ensembl automatic gene annotation system (a collection of gene annotation pipelines), termed the Ensembl annotation process. All Ensembl transcripts are based on experimental evidence and thus the automated pipeline relies on the mRNAs and protein sequences deposited into public databases from the scientific community. Manually-curated transcripts produced by the HAVANA group.

An Ensembl gene (with a unique ENSG... ID) includes any spliced transcripts (ENST...) with overlapping coding sequence, with the exception of manually annotated readthrough genes which are annotated as a separate locus. Transcripts from the Ensembl annotation process, the Havana/Vega set and the Consensus Coding Sequence (CCDS project) set may all be clustered into the same gene. Transcripts that belong to the same gene ID may differ in splice events, exons, and can give rise to very different proteins. These are isoforms, arising from alternative splicing. Transcript clusters with no overlapping coding sequence are annotated as separate genes. Two transcripts may overlap in non-coding sequence (ie intronic sequence or UnTranslated Region (UTR), and be classified under two separate genes. After the Ensembl gene and transcript sequences are defined, the gene and transcript names are assigned.

[Cartoon of a gene in Ensembl]

The sequence of any gene or transcript shown in Ensembl is the sequence in the underlying genome assembly, where the sequence of any protein is the translated genomic sequence. This is to prevent any mismatch between the genes and the genome. For this reason, sequences of genes, transcripts and proteins in Ensembl may differ from other databases, who may use sequence from other individuals than were used to produce the genome.

Find out more about the different types of gene annotation used by Ensembl, and where we get our data from:
* [Automatic annotation of coding genes.](automatic_coding.md)
* [Automatic annotation of non-coding genes.](automatic_noncoding.md)
* [Annotation of immunoglobulin and T-cell receptor genes.](automatic_immunoglobulin.md)
* [Automatic annotation using RNA-seq data.](automatic_RNAseq.md)
* [Manual gene annotation by Havana.](manual_havana.md)
* [The Ensembl and Havana merge.](annotation_merge.md)
* [CCDS.](ccds_annotation.md)
* [Gene annotation of low quality assemblies.](low_quality_assemblies.md)
* [Sources of data for gene annotation.](annotation_sources.md)
* [Gene naming.](gene_names.md)
* [Transcript tags.](transcript_quality_tags.md)
* [Gene and transcript types.](biotypes.md)
* [External references.](xrefs.md)
