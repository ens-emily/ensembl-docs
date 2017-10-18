# BioMart RESTful access (Perl and wget)

BioMart RESTful access is a quick and easy way to query the Ensembl marts using wget or perl and doesn't require any programing knowledge.

### Summary

1.  [Obtaining the BioMart xml from the BioMart website](#biomartxml)
2.  [Using the wget UNIX command](#wget)
3.  [Using the BioMart PERL API script](#biomartperlapi)
4.  [The xml Completion Stamp](#completionstamp)

## Obtaining the BioMart xml from the BioMart website

You can easily obtain a BioMart xml file from the BioMart interface. For example, [navigate to the Ensembl gene mart on the Ensembl website](http://www.ensembl.org/biomart), apply your required filters and select the attribute you are insterested in. [As shown in the example below, filter on the human Ensembl Gene ID "ENSG00000139618" and select the Ensembl Gene, Transcript IDs, HGNC IDs and symbols and Uniprot Swissprot accessions attribute](www.ensembl.org/biomart/martview?VIRTUALSCHEMANAME=default&ATTRIBUTES=hsapiens_gene_ensembl.default.feature_page.ensembl_gene_id|hsapiens_gene_ensembl.default.feature_page.ensembl_transcript_id|hsapiens_gene_ensembl.default.feature_page.hgnc_symbol|hsapiens_gene_ensembl.default.feature_page.hgnc_id|hsapiens_gene_ensembl.default.feature_page.uniprot_swissprot&FILTERS=hsapiens_gene_ensembl.default.filters.ensembl_gene_id.ENSG00000139618&VISIBLEPANEL=resultspanel). The BioMart xml file can be downloaded from the BioMart result page accessible via the "Results" button. To get your BioMart query in xml, just click on the xml button as indicated by the red box in the image below.

[![](http://www.ensembl.org/img/biomart_xml.png)](www.ensembl.org/biomart/martview?VIRTUALSCHEMANAME=default&ATTRIBUTES=hsapiens_gene_ensembl.default.feature_page.ensembl_gene_id|hsapiens_gene_ensembl.default.feature_page.ensembl_transcript_id|hsapiens_gene_ensembl.default.feature_page.hgnc_symbol|hsapiens_gene_ensembl.default.feature_page.hgnc_id|hsapiens_gene_ensembl.default.feature_page.uniprot_swissprot&FILTERS=hsapiens_gene_ensembl.default.filters.ensembl_gene_id.ENSG00000139618&VISIBLEPANEL=resultspanel)

The xml button will open a new browser window and display the BioMart query in xml format, the text will be similar to the following image.

![](www.ensembl.org/img/biomart_xml2.png)

Just save the content of this page in a new file on your computer, e.g 'hgnc_swissprot.xml' in our example.

## Using the wget UNIX command

Type the following command in your terminal:

<pre class="code">wget -O result.txt 'http://www.ensembl.org/biomart/martservice?query=
</pre>

Then copy the content of the previouly saved xml file all in one line after the "query=", you should now have the following:

<pre class="code">wget -O result.txt 'http://www.ensembl.org/biomart/martservice?query=<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE Query><Query  virtualSchemaName = "default" formatter = "TSV" header = "0" uniqueRows = "0" count = "" datasetConfigVersion = "0.6" ><Dataset name = "hsapiens_gene_ensembl" interface = "default" ><Filter name = "ensembl_gene_id" value = "ENSG00000139618"/><Attribute name = "ensembl_gene_id" /><Attribute name = "ensembl_transcript_id" /><Attribute name = "hgnc_symbol" /><Attribute name = "hgnc_id" /><Attribute name = "uniprot_swissprot" /></Dataset></Query>'
</pre>

Finally, just run the command to get the BioMart data stored inside the "result.txt" file. In our example, we get the following result.txt file:

<pre class="code">less result.txt

ENSG00000139618  ENST00000380152  BRCA2  HGNC:1101  P51587
ENSG00000139618  ENST00000528762  BRCA2  HGNC:1101
ENSG00000139618  ENST00000470094  BRCA2  HGNC:1101
ENSG00000139618  ENST00000544455  BRCA2  HGNC:1101  P51587
</pre>

<a name="biomartperlapi"></a>

## Using the BioMart PERL API script

First, you will need to download the BioMart API ([Complete documentation can be found on the biomart.org website](http://www.biomart.org/other/install-overview.html)), to do this you can follow the command below:

<pre class="code">git clone --branch cvs/release-0_7 https://github.com/biomart/biomart-perl
</pre>

To use the Ensembl marts from the ensembl.org website, just edit the path variable in the biomart-perl/scripts/webExample.pl Perl script to the following:

<pre class="code">my $path="http://www.ensembl.org/biomart/martservice?";
</pre>

Finally run the biomart-perl/scripts/webExample.pl Perl script with the xml file obtained in the ["Obtaining the BioMart xml"](#biomartxml) section:

<pre class="code">biomart-perl/scripts: perl webExample.pl hgnc_swissprot.xml
</pre>

You should get an output similar to the following:

<pre class="code">ENSG00000139618  ENST00000380152  BRCA2  HGNC:1101  P51587
ENSG00000139618  ENST00000528762  BRCA2  HGNC:1101
ENSG00000139618  ENST00000470094  BRCA2  HGNC:1101
ENSG00000139618  ENST00000544455  BRCA2  HGNC:1101  P51587
</pre>

<a name="completionstamp"></a>

## The xml Completion Stamp

If you want to make sure you are getting all the data from your BioMart query, you can add a "CompletionStamp" to the xml file. To do this, just open the previously obtained xml file in the ["Obtaining the BioMart xml"](#biomartxml) section and add the following text in the query tag:

<pre class="code">completionStamp = "1"
</pre>

The above command should be paste in the location indicated by the red box in the image below:

<div class="image-wrap" style="">![](/img/biomart_completion_stamp.png)</div>

Then either use [the wget command](#wget) or [the BioMart Perl script](#biomartperlapi). If the query successfuly ran, you will get a "[success]" after running the wget or BioMart perl script:

<pre class="code">biomart-perl/scripts: perl webExample.pl hgnc_swissprot_completionstamp.xml

ENSG00000139618  ENST00000380152  BRCA2  HGNC:1101  P51587
ENSG00000139618  ENST00000528762  BRCA2  HGNC:1101
ENSG00000139618  ENST00000470094  BRCA2  HGNC:1101
ENSG00000139618  ENST00000544455  BRCA2  HGNC:1101  P51587
[success]
</pre>
