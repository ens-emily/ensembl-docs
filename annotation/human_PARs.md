# Pseudoautosomal regions in human

The pseudoautosomal regions (PAR), where chromosome X and Y share homologous sequence, are defined by the GRC for human. When viewing the PAR on either X or Y in the browser, you will see the region highlighted in blue. You are able to move seamlessly along the chromosome between the PARs and the unique X or Y sequences. Genes and variants found on the PAR will have coordinates listed for both X and Y.

Within our core human database, the Y chromosome is divided into five regions:

* chromosome:GRCh38:Y:1 - 10000 is unique to Y but is a string of 10000 Ns
* chromosome:GRCh38:Y:10001 - 2781479 is shared with X: 10001 - 2781479 (PAR1)
* chromosome:GRCh38:Y:2781480 - 56887902 is unique to Y
* chromosome:GRCh38:Y:56887903 - 57217415 is shared with X: 155701383 - 156030895 (PAR2)
* chromosome:GRCh38:Y:57217416 - 57227415 is unique to Y

We store sequence for only the three unique regions of Y in our database. The DNA for PAR1 and PAR2 are loaded only for chromosome X. The full-length chromosome Y can be generated on-the-fly by our API, where we stitch in the shared sequence from X.