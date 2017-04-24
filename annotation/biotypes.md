# Gene and transcript types

## Genes

* **Protein coding** Contains an open reading frame (ORF).
  * **Polymorphic** A protein coding gene that has at least one transcript with a valid ORF and one or more coding transcripts that contain a polymorphism.
* **Processed transcript** Doesn't contain an ORF. Divided into three major categories.
  * **Long non-coding RNA (lncRNA)** Subclassified into one of the following types:
    * **Non coding** Contains transcripts which are known from the literature to not be protein coding.
    * **3prime_overlapping_ncRNA** Has transcripts where ditag and/or published experimental data strongly supports the existence of long (>200bp) non-coding transcripts that overlap the 3'UTR of a protein-coding locus on the same strand.
    * **Antisense** Has transcripts that overlap the genomic span (i.e. exon or introns) of a protein-coding locus on the opposite strand.
    * **lincRNA (long interspersed ncRNA)** Has transcripts that are long intergenic non-coding RNA locus with a length >200bp. Requires lack of coding potential and may not be conserved between species.
    * **Retained_intron** Has an alternatively spliced transcript believed to contain intronic sequence relative to other, coding, variants.
    * **Sense_intronic** Has a long non-coding transcript in introns of a coding gene that does not overlap any exons.
    * **Sense_overlapping** Has a long non-coding transcript that contains a coding gene in its intron on the same strand.
    * **Macro_lncRNA** Unspliced lncRNAs that are several kb in size.
Bidirectional lncRNA. A non-coding locus that originates from within the promoter region of a protein-coding gene, with transcription proceeding in the opposite direction on the other strand.
  * **ncRNA**
    * **miRNA** microRNA.
    * **piRNA** piwi-interacting RNA.
    * **rRNA** ribsosomal RNA.
    * **siRNA** small interfering RNA.
    * **snRNA** small nuclear RNA.
    * **snoRNA** small nucleolar RNA.
    * **tRNA** transfer RNA.
    * **vaultRNA** Short non coding RNA genes that form part of the vault ribonucleoprotein complex.
  * **Unclassified processed transcript** Cannot be placed in one of the other categories.
* **Pseudogene** Similar to known proteins but contain a frameshift and/or stop codon(s) which disrupts the ORF. These can be classified into the following:
  * **Processed pseudogene** Pseudogene that lack introns and is thought to arise from reverse transcription of mRNA followed by reinsertion of DNA into the genome.
Unprocessed pseudogene. Pseudogene that can contain introns since produced by gene duplication.
  * **Transcribed pseudogene** Pseudogene where protein homology or genomic structure indicates a pseudogene, but the presence of locus-specific transcripts indicates expression. These can be classified into 'Processed', 'Unprocessed' and 'Unitary'.
  * **Translated pseudogene** Pseudogenes that have mass spec data suggesting that they are also translated. These can be classified into 'Processed', 'Unprocessed'
  * **Polymorphic pseudogene** Pseudogene owing to a SNP/indel but in other individuals/haplotypes/strains the gene is translated.
  * **Unitary pseudogene** A species specific unprocessed pseudogene without a parent gene, as it has an active orthologue in another	species.
  * **IG Pseudogene** Inactivated immunoglobulin gene.
* **IG Gene** Immunoglobulin gene.
* **TR Gene** T cell receptor gene.
* **TEC (To be Experimentally Confirmed)** This is used for non-spliced EST clusters that have polyA features. This category has been specifically created for the ENCODE project to highlight regions that could indicate the presence of protein coding genes that require experimental validation, either by 5' RACE or RT-PCR to extend the transcripts, or by confirming expression of the putatively-encoded peptide with specific antibodies.

## Transcript Classification

* **Protein coding** Protein coding transcripts. These can be further classified as follows:
  * **Known Protein coding** 100% Identical to RefSeq NP or Swiss-Prot entry.
  * **Novel Protein coding** Shares >60% length with known coding sequence from RefSeq or Swiss-Prot or has cross-species/family support or domain evidence.
  * **Putative Protein coding** Shares <60% length with known coding sequence from RefSeq or Swiss-Prot, or has an alternative first or last coding exon.
  * **Nonsense mediated decay** If the coding sequence (following the appropriate reference) of a transcript finishes >50bp from a downstream splice site then it is tagged as NMD. If the variant does not cover the full reference coding sequence then it is annotated as NMD if NMD is unavoidable i.e. no matter what the exon structure of the missing portion is the transcript will be subject to NMD.
  * **Nonstop decay** Transcripts that have polyA features (including signal) without a prior stop codon in the CDS, i.e. a non-genomic polyA tail attached directly to the CDS without 3' UTR. These transcripts are subject to degradation.
* **Processed transcripts** Doesn't contain an ORF. Divided into three major categories.
  * **Long non-coding RNA (lncRNA)** Subclassified into one of the following types:
    * **Non coding** Known from the literature to not be protein coding.
    * **3prime_overlapping_ncRNA** Ditag and/or published experimental data strongly supports the existence of long (>200bp) non-coding transcripts that overlap the 3'UTR of a protein-coding locus on the same strand.
    * **Antisense** Overlap the genomic span (i.e. exon or introns) of a protein-coding locus on the opposite strand.
    * **lincRNA (long interspersed ncRNA)** Long intergenic non-coding RNA locus with a length >200bp. Requires lack of coding potential and may not be conserved between species.
    * **Retained_intron** An alternatively spliced transcript believed to contain intronic sequence relative to other, coding, variants.
    * **Sense_intronic** A long non-coding transcript in introns of a coding gene that does not overlap any exons.
    * **Sense_overlapping** Has a long non-coding transcript that contains a coding gene in its intron on the same strand.
    * **macro_lncRNA** unspliced lncRNAs that are several kb in size.
  * **ncRNA**
    * **miRNA** microRNA.
    * **piRNA** piwi-interacting RNA.
    * **rRNA** ribsosomal RNA.
    * **siRNA** small interfering RNA.
    * **snRNA** small nuclear RNA.
    * **snoRNA** small nucleolar RNA.
    * **tRNA** transfer RNA.
    * **vaultRNA** Short non coding RNA genes that form part of the vault ribonucleoprotein complex.
  * **Unclassified processed transcript** Cannot be placed in one of the other categories.
* **Pseudogene** Have homology to proteins but generally suffer from a disrupted coding sequence and	an active homologous gene can be found at another locus. Sometimes these entries have an intact coding sequence	or an open but truncated ORF, in which case there is other evidence used (for example genomic polyA stretches at the 3' end) to classify them as a pseudogene. Can be further classified as follows:
  * **Processed pseudogene** Pseudogene that appears to have been produced by integration of a reverse transcribed mRNA into the genome.
  * **Unprocessed pseudogene** Pseudogene that shows evidence of loss of function, but has exon-intron structure.
  * **Transcribed pseudogene** Pseudogene where protein homology or genomic structure indicates a pseudogene, but the presence of locus-specific transcripts indicates expression. These can be classified into 'Processed' and 'Unprocessed'.
  * **Translated pseudogene** Pseudogenes that have mass spec data suggesting that they are also translated. These can be classified into 'Processed' and 'Unprocessed'
  * **Polymorphic pseudogene** Pseudogene owing to a SNP/indel but in other individuals/haplotypes/strains the gene is translated.
  * **Unitary pseudogene** A species specific unprocessed pseudogene without a parent gene, as it has an active orthologue in another	species.
  * **IG Pseudogene** Inactivated immunoglobulin gene.
* **TEC (To be Experimentally Confirmed)** This is used for non-spliced EST clusters that have polyA features. This category has been specifically created for the ENCODE project to highlight regions that could indicate the presence of novel protein coding genes that require experimental validation, either by 5' RACE or RT-PCR to extend the transcripts, or by confirming expression of the putatively-encoded peptide with specific antibodies.
* **Artifact** Used to tag mistakes in the public databases (Ensembl/SwissProt/ Trembl). Usually these arise from high-throughput cDNA sequencing projects, which submit automatic annotation sometimes resulting in erroneous coding sequences that are, for example, 3' UTRs.
* **IG Gene** Immunoglobulin gene.
* **TR Gene** T cell receptor gene.