# Sources of data for gene annotation

## Protein coding genes

Ensembl coding transcripts are based on mRNA and protein from the following databases. If you do not find a transcript that you expected in Ensembl, make sure there is sequence submitted into these databases. If the sequence is missing, consider submitting your experimental evidence to [ENA](http://www.ebi.ac.uk/ena).


| Source | About |
| --- | --- |
| [The European Nucleotide Archive (ENA)](http://www.ebi.ac.uk/ena) | The European aspect of the International Nucleotide Sequence Database Consortium, INSDC, and is maintained at the European Bioinformatics Institute, the [EMBL-EBI](http://www.ebi.ac.uk/). All sequence records are synchronised with the other partners in the INSDC, namely [NCBI GenBank](https://www.ncbi.nlm.nih.gov/genbank/) in North America and [DDBJ](http://www.ddbj.nig.ac.jp/) in Japan.|
| [UniProtKB](http://www.uniprot.org/) | A collection of reviewed, manually annotated protein sequences, UniProtKB/Swiss-Prot, and a set of unreviewed proteins translated from the ENA/GenBank/DDBJ nucleotide set, UniProtKB/TrEMBL. Both of these are used by Ensembl. |
| [NCBI RefSeq](http://www.ncbi.nlm.nih.gov/RefSeq/) | A comprehensive set of mRNA and proteins. Manually annotated, reviewed proteins have an ID beginning with NP, known protein, while mRNAs in this category begin with NM. Predicted proteins and mRNA begin with XP and XM, respectively. Only the manually annotated proteins and mRNAs are used in the Ensembl annotation process. |

## Non-coding genes

| Source | About |
| --- | --- |
| [RFAM](http://rfam.xfam.org/) | Rfam is a database of RNA families, maintains at the [EMBL-EBI](http://www.ebi.ac.uk/). |
| [miRBase](http://www.mirbase.org/) | miRBase curates submitted miRNA sequences, including the miRNA transcript and predicted hairpin precursor. |
| [tRNAscan-SE](http://lowelab.ucsc.edu/tRNAscan-SE/) | An algorithm for predicting tRNA sequences within genomic sequence. |

## Gene Status

Ensembl genes and transcripts are classified as known, novel or merged.

A known gene or transcript matches to a sequence in a public, scientific database such as UniProtKB and NCBI RefSeq. The match must be for the same species, otherwise the gene is considered to be novel for that species. Ensembl-Havana merges occur when a manually annotated transcript from the Havana project matches to the Ensembl coding sequence exactly. Matches to IDs in other databases, such as UniProtKB and NCBI EntrezGene, are listed under External References in the Transcript tab.

Known miRNAs from the annotation of Non-coding RNAs process must have a match in miRBase for the same species.
