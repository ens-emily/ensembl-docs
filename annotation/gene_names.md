# Gene Naming

## Human genes

Most human protein-coding genes have an associated HGNC symbol from the [HUGO Gene Nomenclature Committee](http://www.genenames.org/).

ncRNA genes are given names from miRBase and RFAM.

'Clone-based' identifiers apply to transcripts that cannot be associated with an HGNC symbol.

The list of gene name categories for human is as follows:

* HGNC automatic
* HGNC curated
* Clone-based Ensembl
* Clone-based Vega

On occasion, the Hugo Gene Nomenclature Committee (HGNC) review the approved gene names for a number of genes. This review process aims to assign gene names that describe gene function more accurately. Please see the [HGNC site](http://www.genenames.org/) for more details as to which genes are more at risk of a likely change. Please note that previous symbols will be maintained as ‘synonyms’, however we recommend using the HGNC ID to ensure stability in your pipelines and analyses.

## Other species

Mouse genes are named from [MGI](http://www.informatics.jax.org/), rat genes are named from [RGD](http://rgd.mcw.edu/) and zebrafish genes are named from [ZFIN](https://zfin.org/). Other species have gene names imported from [Uniprot](http://www.uniprot.org/) and [NCBIGene](https://www.ncbi.nlm.nih.gov/gene), or if this is not available, from the human, mouse, rat or zebrafish orthologue.

## Transcript numbering

Each transcript is named using the gene name, followed by a number. If the number starts with '0', eg 001, 002, etc, this is a merged or manually curated transcript from Havana/Vega. If the number starts with '2', such as 200, 201, etc, this is an automatically annotated transcript from Ensembl. This does not take the place of the Ensembl gene ID, ENSG..., which is stable from release to release, and has not changed.
