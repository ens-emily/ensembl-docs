# Transcript tags

Transcript tags can be used to identify the highest quality or most relevant transcripts for your studies. We used three different tags:

* [Transcript support level (TSL)]
* [APPRIS]
* [GENCODE Basic]

## Transcript support level

The Transcript Support Level (TSL) is a method to highlight the well-supported and poorly-supported transcript models for users. The method relies on the primary data that can support full-length transcript structure: mRNA and EST alignments supplied by [UCSC](https://genome.ucsc.edu/) and Ensembl.

It is important to understand how to assess transcript annotations that you see in [GENCODE](https://www.gencodegenes.org/). While some transcript models have a high level of support through the full length of their exon structure, there are also transcripts that are poorly supported and that should be considered speculative. 

### TSL Method

The mRNA and EST alignments are compared to the GENCODE transcripts and the transcripts are scored according to how well the alignment matches over its full length. The GENCODE TSL provides a consistent method of evaluating the level of support that a GENCODE transcript annotation is actually expressed in humans. Human transcript sequences from the International Nucleotide Sequence Database Collaboration (GenBank, ENA, and DDBJ) are used as the evidence for this analysis. Exonerate RNA alignments from Ensembl, BLAT RNA and EST alignments from the UCSC Genome Browser Database are used in the analysis. Erroneous transcripts and libraries identified in lists maintained by the Ensembl, UCSC, HAVANA and RefSeq groups are flagged as suspect. GENCODE annotations for protein-coding and non-protein-coding transcripts are compared with the evidence alignments.

Annotations in the MHC region and other immunological genes are not evaluated, as automatic alignments tend to be very problematic. Methods for evaluating single-exon genes are still being developed and they are not included in the current analysis.

Multi-exon GENCODE annotations are evaluated using the criteria that all introns are supported by an evidence alignment and the evidence alignment does not indicate that there are unannotated exons. Small insertions and deletions in evidence alignments are assumed to be due to polymorphisms and not considered as differing from the annotations. All intron boundaries must match exactly. The transcript start and end locations are allowed to differ.

### TSL Categories

The following categories are assigned to each of the evaluated annotations:
* **tsl1** – all splice junctions of the transcript are supported by at least one non-suspect mRNA
* **tsl2** – the best supporting mRNA is flagged as suspect or the support is from multiple ESTs
* **tsl3** – the only support is from a single EST
* **tsl4** – the best supporting EST is flagged as suspect
* **tsl5** – no single transcript supports the model structure
* **tslNA** – the transcript was not analysed for one of the following reasons:
  * pseudogene annotation, including transcribed pseudogenes
  * human leukocyte antigen (HLA) transcript
  * immunoglobin gene transcript
  * T-cell receptor transcript
  * single-exon transcript (will be included in a future version)

## APPRIS

APPRIS is a system to annotate alternatively spliced transcripts based on a range of computational methods. It provides value to the annotations of the human, mouse, zebrafish, rat, and pig genomes. (http://nar.oxfordjournals.org/content/41/D1/D110.long).

APPRIS has selected a single CDS variant for each gene as the 'PRINCIPAL' isoform. Principal isoforms are tagged with the numbers 1 to 5, with 1 being the most reliable.

* **PRINCIPAL:1** Transcript(s) expected to code for the main functional isoform based solely on the core modules in the APPRIS.
* **PRINCIPAL:2** Where the APPRIS core modules are unable to choose a clear principal variant (approximately 25% of human protein coding genes), the database chooses two or more of the CDS variants as "candidates" to be the principal variant.
* **PRINCIPAL:3** Where the APPRIS core modules are unable to choose a clear principal variant and there more than one of the variants have distinct CCDS identifiers, APPRIS selects the variant with lowest CCDS identifier as the principal variant. The lower the CCDS identifier, the earlier it was annotated.
* **PRINCIPAL:4** Where the APPRIS core modules are unable to choose a clear principal CDS and there is more than one variant with a distinct (but consecutive) CCDS identifiers, APPRIS selects the longest CCDS isoform as the principal variant.
* **PRINCIPAL:5** Where the APPRIS core modules are unable to choose a clear principal variant and none of the candidate variants are annotated by CCDS, APPRIS selects the longest of the candidate isoforms as the principal variant.

For genes in which the APPRIS core modules are unable to choose a clear principal variant (approximately 25% of human protein coding genes), the "candidate" variants not chosen as principal are labeled in the following way:
* **ALTERNATIVE:1** Candidate transcript(s) models that are conserved in at least three tested species.
* **ALTERNATIVE:2** Candidate transcript(s) models that appear to be conserved in fewer than three tested species.

Non-candidate transcripts are not tagged and are considered as "Minor" transcripts. Further information and additional web services can be found at the [APPRIS website](http://appris.bioinfo.cnio.es/#/).

## GENCODE Basic

The GENCODE gene set is the gene set Ensembl displays for human and mouse. GENCODE Basic is a subset of the GENCODE gene set, and is intended to provide a simplified, high-quality subset of the GENCODE transcript annotations that will be useful to the majority. This subset prioritises full-length protein coding transcripts over partial or non-protein coding transcripts within the same gene.

GENCODE Basic includes all genes in the GENCODE gene set, with a representative subset of the transcripts (splice variants). The GENCODE Basic set is available for the human and mouse gene sets from Ensembl release 75.

### Rules for GENCODE Basic

We worked with GENCODE to decide how to tag transcripts as 'Basic'. These are the rules that we use to tag which transcripts are included in the GENCODE Basic set, for each gene:

1. Loop through all protein-coding (and similar biotype) transcripts and tag all the complete (CDS start- and end found) transcripts. If none of the transcripts are complete, tag only the transcript(s) with the longest CDS.
2. Loop through all the small noncoding and antisense transcripts and tag all the complete (mRNA start- and end found) transcripts. If none are complete, loop through the long-noncoding transcripts too and then tag only the transcript(s) with the longest combined exon length.
3. Combine the results from steps (1) and (2) and this is what is displayed as ‘GENCODE Basic’.
4. If, after step (3), we've got an empty basket and no transcripts in the gene are tagged as 'Basic', we look for pseudogene transcripts and tag all the pseudogene transcripts that we find.
5. Finally, we've still got no transcripts tagged from steps (1) or (2) or (4), then we tag transcripts with 'problematic' biotypes ie. retained_intron, TEC, ambiguous_ORF and disrupted_domain.