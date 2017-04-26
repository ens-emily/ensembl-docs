Gene Families in Compara

Introduction

Ensembl families are determined through classification of all Ensembl proteins along with metazoan sequences from UniProtKB. It therefore provides a way of exploring orthologues and closely related homologues across a range of animal species.

Pipeline overview

The pipeline consists of the following steps:

Load members from Ensembl
Load UniProt entries
Run HMM search (using the HMM library described in this document, excluding the TF6 families)
Store the families
Align the families with Mafft
Annotate the family with a consensus description (from its members' descriptions)
Details

Family ID
The families have been assigned the stable ID of their corresponding HMM, as defined in this document.
Consensus Annotation
For each cluster obtained, a consensus annotation is automatically generated from the UniProt/Swiss-Prot and UniProt/TrEMBL description lines of all UniProtKB members using the following approach: 
If the description covers less than 40% of UniProt members in the cluster, the family description is assigned 'AMBIGUOUS'. If the annotation confidence score, described below, is zero, 'UNKNOWN' is assigned. Be aware that 'UNCHARACTERIZED' is a UniProt description for a protein, and does not reflect the score. 
The annotation confidence score is the percentage of UniProtKB family members with this description, or part of it. Note that only family members with 'informative' UniProt descriptions are taken into account.
Multiple Alignments
Ensembl provides pre-calculated multiple sequence alignments of all members for each cluster. 
If the Java runtime environment, JRE, is properly installed on your computer, then buttons will produce a new window with multiple alignments of family members displayed in JalView. The first option includes Ensembl protein prediction from the current, as well as all other species supported by Ensembl. The second option also includes UniProtKB members. You can also export a text file with the alignments of all the family members - a wide range of formats is available from the control panel. 
Alternatively, export alignments using the Compara Perl API.
