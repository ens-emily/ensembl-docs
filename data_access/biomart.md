# BioMart

Tables of Ensembl data can be downloaded via the highly customisable [BioMart data mining tool](/biomart/martview). The easy-to-use web-based tool allows extraction of data without any programming knowledge or understanding of the underlying database structure.

[![screenshot of the biomart interface](http://www.ensembl.org/img/biomart.png)](/biomart/martview?VIRTUALSCHEMANAME=default&ATTRIBUTES=hsapiens_gene_ensembl.default.feature_page.ensembl_gene_id|hsapiens_gene_ensembl.default.feature_page.ensembl_transcript_id|hsapiens_gene_ensembl.default.feature_page.hgnc_id|hsapiens_gene_ensembl.default.feature_page.hgnc_symbol&FILTERS=hsapiens_gene_ensembl.default.filters.chromosome_name.1&VISIBLEPANEL=resultspanel)  

## BioMart tutorials and FAQs

*   [How to use BioMart](./how_to_use_biomart.html)
*   [BioMart tutorials](/info/website/tutorials/): BioMart short videos and written materials.
*   [BioMart FAQs](/Help/Faq): BioMart Frequently Asked Questions.
    *   [How can I download all the proteins in the human proteome? Do I use BioMart?](/Help/Faq?id=215)
    *   [Ensembl BioMart shows results for protein-coding genes when protein-associated attributes are chosen. Non-coding genes that pass filters will not be shown in the results if certain protein-associated attributes are chosen. Why does this occur?](/Help/Faq?id=476)
*   [Combining multiple species datasets](./biomart_combining_species_datasets.html): Example on how to combine multiple mart datasets inside one mart or accross different marts.

## BioMart R package, RESTful access and API

*   [BiomaRt, Bioconductor R package](./biomart_r_package.html)
*   [BioMart RESTful access (Perl and wget)](./biomart_restful.html)
*   [BioMart perl API](./biomart_perl_api.html)
