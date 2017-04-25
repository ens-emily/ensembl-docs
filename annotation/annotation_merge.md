# The Ensembl and Havana merge

Species which have both HAVANA and Ensembl gene annotation undergo a merge of the two sets of gene models. These species are:
* Human
* Mouse
* Zebrafish
* Pig
* Rat

Where manual curation is available for a transcript, the Ensembl and HAVANA transcript models are compared and merged when their splicing structure is identical. If the ends differ between the two models, the HAVANA annotated ends are used and the automatically annotated ends are discarded.

A merged, or golden, gene indicates that annotation was provided by both Ensembl and HAVANA. A merged gene will either contain at least one merged transcript model, or it will contain unmerged transcripts from both Ensembl and HAVANA. Where a transcript model is annotated only by Ensembl or HAVANA, it will be displayed as an unmerged (red) model.

## GENCODE

For human and mouse, this combined Ensembl/HAVANA gene set is the default gene set from the [GENCODE project](https://www.gencodegenes.org/). For both human and mouse, we also guarantee that all transcripts from the Consensus Coding Sequence (CCDS) set are present in the GENCODE gene set.

The complete GENCODE gene set for human and mouse can be viewed on our website in the GENCODE Comprehensive track. A subset of these transcript models are tagged as being in the [GENCODE Basic](transcript_quality_tags.md) set, which is also available on our website.
