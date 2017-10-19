# BiomaRt, Bioconductor R package

The Bioconductor BiomaRt R package is a quick, easy and powerful way to access BioMart right from your R software terminal.

The following documention is using R 2.2 and Bioconductor version 3.1.

### Summary

1.  [How to install the Bioconductor BiomaRt R package](#biomartinstall)
2.  [Bioconductor BiomaRt R package documentation](#biomartdoc)
3.  [Bioconductor BiomaRt R examples with the Ensembl Gene mart](#biomartexamples)

## How to install the Bioconductor BiomaRt R package

First make sure you have installed the [R software](http://www.r-project.org/) on your computer.

Then, run the following commands to install the Bioconductor BiomaRt R package:

<pre class="code">source("http://bioconductor.org/biocLite.R")
biocLite("biomaRt")
</pre>

<a name="biomartdoc"></a>

## Bioconductor BiomaRt R package documentation

More information regarding the Bioconductor BiomaRt, R package and documentation can be found on the [BiomaRt Bioconductor page](http://www.bioconductor.org/packages/release/bioc/html/biomaRt.html).

<a name="biomartexamples"></a>

## Bioconductor BiomaRt R examples with the Ensembl Gene mart

### listEnsembl & listDatasets

To get the list of all the Ensembl mart availables on the ensembl.org website, run the "listEnsembl" function:

<pre class="code">> library(biomaRt)

> listEnsembl()

     biomart               version
1    ensembl               Ensembl Genes 79
2        snp               Ensembl Variation 79
3 regulation               Ensembl Regulation 79
</pre>

You can give an Ensembl archive version as a parameter to get the list of archived Ensembl marts, for example for the Ensembl GRCh37 or release 78 marts:

<pre class="code">> listEnsembl("GRCh=37")

     biomart            version
1    ensembl            Ensembl Genes
2        snp            Ensembl Variation
3 regulation            Ensembl Regulation

> listEnsembl(version=78)

     biomart               version
1    ensembl               Ensembl Genes 78
2        snp               Ensembl Variation 78
3 regulation               Ensembl Regulation 78
</pre>

The "listDatasets" function will give you the list of all the species available (mart datasets) for a given mart:

<pre class="code">> library(biomaRt)
> ensembl = useEnsembl(biomart="ensembl")
> head(listDatasets(ensembl))
                         dataset                                description version
1         oanatinus_gene_ensembl     Ornithorhynchus anatinus genes (OANA5)   OANA5
2        cporcellus_gene_ensembl            Cavia porcellus genes (cavPor3) cavPor3
3        gaculeatus_gene_ensembl     Gasterosteus aculeatus genes (BROADS1) BROADS1
4         lafricana_gene_ensembl         Loxodonta africana genes (loxAfr3) loxAfr3
5 itridecemlineatus_gene_ensembl Ictidomys tridecemlineatus genes (spetri2) spetri2
6        choffmanni_gene_ensembl        Choloepus hoffmanni genes (choHof1) choHof1
</pre>

You can also use listDatasets with the Ensembl GRCh37 and archived marts:

<pre class="code">> library(biomaRt)
> grch37 = useEnsembl(biomart="ensembl",GRCh=37)
> listDatasets(grch37)[31:35,]
                    dataset                                description      version
31    hsapiens_gene_ensembl            Homo sapiens genes (GRCh37.p13)   GRCh37.p13
32       mfuro_gene_ensembl Mustela putorius furo genes (MusPutFur1.0) MusPutFur1.0
33  tbelangeri_gene_ensembl           Tupaia belangeri genes (tupBel1)      tupBel1
34     ggallus_gene_ensembl              Gallus gallus genes (Galgal4)      Galgal4
35 xtropicalis_gene_ensembl          Xenopus tropicalis genes (JGI4.2)       JGI4.2

> ensembl78 = useEnsembl(biomart="ensembl",version=78)
> listDatasets(ensembl78)[31:35,]

                  dataset                                description      version
31 mlucifugus_gene_ensembl           Myotis lucifugus genes (myoLuc2)      myoLuc2
32   hsapiens_gene_ensembl                Homo sapiens genes (GRCh38)       GRCh38
33   pformosa_gene_ensembl      Poecilia formosa genes (PoeFor_5.1.2) PoeFor_5.1.2
34      mfuro_gene_ensembl Mustela putorius furo genes (MusPutFur1.0) MusPutFur1.0
35 tbelangeri_gene_ensembl           Tupaia belangeri genes (tupBel1)      tupBel1
</pre>

### useEnsembl

The "useEnsembl" function allow you to connect to an Ensembl website mart by specifying a BioMart and dataset parameters. For example, to connect to the Ensembl live gene mart human dataset (GRCh38):

<pre class="code">> library(biomaRt)
> ensembl = useEnsembl(biomart="ensembl", dataset="hsapiens_gene_ensembl")
</pre>

To connect to the human dataset of the Ensembl GRCh37 or release 78 gene marts:

<pre class="code">> library(biomaRt)
> ensembl = useEnsembl(biomart="ensembl", dataset="hsapiens_gene_ensembl", GRCh=37)

> ensembl = useEnsembl(biomart="ensembl", dataset="hsapiens_gene_ensembl", version=78)
</pre>

### listMarts, listDatasets and useMart for the Ensembl mirrors

You can connect to the following Ensembl mirrors using the listMarts, listDatasets and useMart functions:

*   Ensembl US West: [http://uswest.ensembl.org/index.html](http://uswest.ensembl.org/index.html)
*   Ensembl US East: [http://useast.ensembl.org/index.html](http://useast.ensembl.org/index.html)
*   Ensembl Asia: [http://asia.ensembl.org/index.html](http://asia.ensembl.org/index.html)

For example to connect to the Ensembl US West mirror:

<pre class="code">> library(biomaRt)
> listMarts(host="uswest.ensembl.org")
               biomart               version
1 ENSEMBL_MART_ENSEMBL               Ensembl Genes 79
2     ENSEMBL_MART_SNP               Ensembl Variation 79
3 ENSEMBL_MART_FUNCGEN               Ensembl Regulation 79
4    ENSEMBL_MART_VEGA               Vega 59
5                pride               PRIDE (EBI UK)

> ensembl_us_west = useMart(biomart="ENSEMBL_MART_ENSEMBL", host="uswest.ensembl.org")

> head(listDatasets(ensembl_us_west))

                         dataset                                description version
1         oanatinus_gene_ensembl     Ornithorhynchus anatinus genes (OANA5)   OANA5
2        cporcellus_gene_ensembl            Cavia porcellus genes (cavPor3) cavPor3
3        gaculeatus_gene_ensembl     Gasterosteus aculeatus genes (BROADS1) BROADS1
4         lafricana_gene_ensembl         Loxodonta africana genes (loxAfr3) loxAfr3
5 itridecemlineatus_gene_ensembl Ictidomys tridecemlineatus genes (spetri2) spetri2
6        choffmanni_gene_ensembl        Choloepus hoffmanni genes (choHof1) choHof1

</pre>

Please note that the useMart function will always require a biomart and host parameters when connecting to an Ensembl mirror website.

### listFilters & listAttributes

The "listFilters" function will give you the list of available filters for a given mart and species:

<pre class="code">> library(biomaRt)
> ensembl = useEnsembl(biomart="ensembl", dataset="hsapiens_gene_ensembl")
> head(listFilters(ensembl))
             name     description
1 chromosome_name Chromosome name
2           start Gene Start (bp)
3             end   Gene End (bp)
4      band_start      Band Start
5        band_end        Band End
6    marker_start    Marker Start
</pre>

The "listAttributes" function will give you the list of the available attributes for a given mart and species:

<pre class="code">> library(biomaRt)
> ensembl = useEnsembl(biomart="ensembl", dataset="hsapiens_gene_ensembl")
> head(listAttributes(ensembl))
                   name           description
1       ensembl_gene_id       Ensembl Gene ID
2 ensembl_transcript_id Ensembl Transcript ID
3    ensembl_peptide_id    Ensembl Protein ID
4       ensembl_exon_id       Ensembl Exon ID
5           description           Description
6       chromosome_name       Chromosome Name
</pre>

### getBM

The "getBM" function allow you to build a BioMart query using a list of mart filters and attributes.

### Example query: Fetch all the Ensembl gene, transcript IDs, HGNC symbols and chromosome locations located on the human chromosome 1

<pre class="code">> library(biomaRt)
> ensembl = useEnsembl(biomart="ensembl", dataset="hsapiens_gene_ensembl")
> chr1_genes <- getBM(attributes=c('ensembl_gene_id',
'ensembl_transcript_id','hgnc_symbol','chromosome_name','start_position','end_position'), filters =
'chromosome_name', values ="1", mart = ensembl)

> head(chr1_gene)

ensembl_gene_id ensembl_transcript_id hgnc_symbol chromosome_name start_position end_position
1 ENSG00000231510       ENST00000443270                           1        5086459      5090899
2 ENSG00000162444       ENST00000315901        RBP7               1        9997206     10016020
3 ENSG00000162444       ENST00000294435        RBP7               1        9997206     10016020
4 ENSG00000270171       ENST00000602640                           1        7693124      7694844
5 ENSG00000225643       ENST00000412797                           1       25581478     25590356
6 ENSG00000116497       ENST00000530710     S100PBP               1       32816767     32858879
</pre>

### Example query: Fetch Ensembl Gene, Transcript IDs, HGNC IDs and symbols and Uniprot Swissprot accessions mapped to the human Ensembl Gene ID "ENSG00000139618"

<pre class="code">> library(biomaRt)
> ensembl = useEnsembl(biomart="ensembl", dataset="hsapiens_gene_ensembl")
> hgnc_swissprot <- getBM(attributes=c('ensembl_gene_id','ensembl_transcript_id','hgnc_symbol','hgnc_id','uniprot_swissprot'),filters = 'ensembl_gene_id', values = 'ENSG00000139618', mart = ensembl)
> hgnc_swissprot
  ensembl_gene_id ensembl_transcript_id hgnc_symbol   hgnc_id uniprot_swissprot
1 ENSG00000139618       ENST00000380152       BRCA2 HGNC:1101            P51587
2 ENSG00000139618       ENST00000528762       BRCA2 HGNC:1101                  
3 ENSG00000139618       ENST00000470094       BRCA2 HGNC:1101                  
4 ENSG00000139618       ENST00000544455       BRCA2 HGNC:1101            P51587
</pre>
