# Regulatory features

Regions that are predicted to regulate gene expression are called **Regulatory features** in Ensembl. The different types of regulatory features annotated include:

* Promoters (regions at the 5' end of genes where transcription factors and RNA polymerase bind to initiate transcription)
* Promoter flanking regions (transcription factor binding regions that flank the above)
* Enhancers (regions that bind transcription factors and interact with promoters to stimulate transcription of distant genes)
* CTCF binding sites (regions that bind CTCF, the insulator protein that demarcates open and closed chromatin)
* Transcription factor binding sites (sites which bind transcription factors, for which no other role can be determined as yet)
* Open chromatin regions (regions of spaced out histones, making them accessible to protein interactions)

For each cell type the regulatory features are assigned labels to describe their activity levels. These include:

* ACTIVE, when the feature displays an active epigenetic signature.
* POISED, when the feature displays a epigenetic signature with the potential to be activated.
* REPRESSED, when the feature is epigenetically repressed.
* INACTIVE, when the region bears no epigenetic modifications from the ones included in the Regulatory Build.
* NA, when there is no available data in the cell type for this feature.

## Determination of regulatory features

Regulatory features are inferred from [publicly available experimental data sets](regulation_sources.md), including:

* Open chromatin assays ([DNase-seq](https://en.wikipedia.org/wiki/DNase-Seq))
* Histone modification assays ([ChIP-seq](https://en.wikipedia.org/wiki/ChIP-sequencing))
* Transcription factor binding assays ([ChIP-seq](https://en.wikipedia.org/wiki/ChIP-sequencing))

In short, raw sequencing data are aligned against the reference genome and then a genome segmentation algorithm is applied to define genomic loci of distinct epigenomic profiles. Finally each epigenomic profile is classified into one type of regulatory features based on a decision tree that takes into consideration transcription factor binding sites (TFBSs), gene annotation and histone modification signal enrichment. This process is called the [Regulatory Build](regulatory_build.md).