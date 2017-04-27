# Gene families

Ensembl families are determined through classification of all Ensembl proteins, including multiple isoforms of the same gene, along with metazoan sequences from [UniProt](http://www.uniprot.org/). It therefore provides a way of exploring orthologues and closely related homologues across a range of animal species.

## Pipeline

The pipeline consists of the following steps:
1. Load proteins from Ensembl and UniProt.
2. Run HMM search (using the HMM library described in [this document](treefam_hmm_library.md), excluding the TF6 families) to find the families.
3. Align the families with [Mafft](http://mafft.cbrc.jp/alignment/software/).
4. Annotate the family with a consensus description, based on its members' descriptions.

### Family ID
The families have been assigned the stable ID of their [corresponding HMM](treefam_hmm_library.md).

### Consensus Annotation
For each cluster obtained, a consensus annotation is automatically generated from the UniProt description lines using the following approach: 
* If the description covers less than 40% of UniProt members in the cluster, the family description is assigned 'AMBIGUOUS'.
* If the annotation confidence score, described below, is zero, 'UNKNOWN' is assigned.
* Be aware that 'UNCHARACTERIZED' is a UniProt description for a protein, and does not reflect the score. 

The annotation confidence score is the percentage of UniProt family members with this description, or part of it. Note that only family members with 'informative' UniProt descriptions are taken into account.

### Multiple Alignments
Ensembl provides pre-calculated multiple sequence alignments of all members for each cluster. We provide a [Wasabi viewer](http://wasabiapp.org/) in the browser for viewing the alignments between just the Ensembl proteins, and the Ensembl and UniProt proteins together.
