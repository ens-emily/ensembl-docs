# Combining multiple species datasets

The BioMart interface allow you to link two different species datasets together but also to query two different marts at the same time.

### Summary

1.  [How to combine two Ensembl gene mart species datasets](#linkdatasets)
2.  [How to combine two mart species datasets located in two different Ensembl marts](#linkmarts)

<a name="linkdatasets"></a>

## How to combine two Ensembl gene mart species datasets

The BioMart interface allow you to link two different species datasets together to get combined results back from BioMart. First, go to the [Ensembl BioMart page](/biomart/martview). As shown in the image below, [filter on human chromosome 1 and select the Ensembl Gene and Transcript IDs, HGNC IDs and symbols attributes.](/biomart/martview?VIRTUALSCHEMANAME=default&ATTRIBUTES=hsapiens_gene_ensembl.default.feature_page.ensembl_gene_id|hsapiens_gene_ensembl.default.feature_page.ensembl_transcript_id|hsapiens_gene_ensembl.default.feature_page.hgnc_id|hsapiens_gene_ensembl.default.feature_page.hgnc_symbol&FILTERS=hsapiens_gene_ensembl.default.filters.chromosome_name.1&VISIBLEPANEL=resultspanel)

[

<div class="image-wrap" style="">![](/img/link_biomart_ds1.png)</div>

](/biomart/martview?VIRTUALSCHEMANAME=default&ATTRIBUTES=hsapiens_gene_ensembl.default.feature_page.ensembl_gene_id|hsapiens_gene_ensembl.default.feature_page.ensembl_transcript_id|hsapiens_gene_ensembl.default.feature_page.hgnc_id|hsapiens_gene_ensembl.default.feature_page.hgnc_symbol&FILTERS=hsapiens_gene_ensembl.default.filters.chromosome_name.1&VISIBLEPANEL=resultspanel)

Click on the second "Dataset" button indicated by the Arrow 1 in the image below.

<div class="image-wrap" style="">![](/img/link_biomart_ds2.png)</div>

You will noticed a new dropdown (indicated by the Arrow 2 in the image above), click on it to select the second species dataset that you are interested in.

In this example, select "Mus musculus genes" in the dropdown as indicated by the red arrow in the image below.

<div class="image-wrap" style="">![](/img/link_biomart_ds3.png)</div>

Finally, you will be fetching all the Ensembl Gene and Transcript IDs, MGI IDs and symbols located on mouse chromosome 1\. Click on the result page. You can see on the image below that the red box represent the human attributes selected in the first dataset and the green box the mouse attributes selected in the second dataset.

<div class="image-wrap" style="">![](/img/link_biomart_ds4.png)</div>

<a name="linkmarts"></a>

## How to combine two mart species datasets located in two different Ensembl marts

The BioMart interface allows you to go further and query species datasets from two different marts.

First, go to the [Ensembl BioMart page](/biomart/martview). As shown in the image below, filter on human chromosome 1 and select the Ensembl Gene and Transcript IDs, HGNC IDs and symbols attributes.[

<div class="image-wrap" style="">![](/img/link_biomart_ds1.png)</div>

](/biomart/martview?VIRTUALSCHEMANAME=default&ATTRIBUTES=hsapiens_gene_ensembl.default.feature_page.ensembl_gene_id|hsapiens_gene_ensembl.default.feature_page.ensembl_transcript_id|hsapiens_gene_ensembl.default.feature_page.hgnc_id|hsapiens_gene_ensembl.default.feature_page.hgnc_symbol&FILTERS=hsapiens_gene_ensembl.default.filters.chromosome_name.1&VISIBLEPANEL=resultspanel)

As in the previous example, you will click on the second "Dataset" button and select "Homo sapiens Short Variation (SNPs and indels)" the dropdown as indicated by the red arrow in the image below.

<div class="image-wrap" style="">![](/img/link_marts1.png)</div>

Finally, filter on human chromosome 1 and select the Variation Names, sources and descriptions, Variant Alleles and Minor alleles (ALL) attributes. Click on the result page. You can see on the image below that the red box represent the human attributes selected in the Ensembl gene mart and the green box the human short variation attributes selected in the Ensembl Variation mart.

<div class="image-wrap" style="">![](/img/link_marts2.png)</div>
