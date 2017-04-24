# CCDS

[CCDS banner]

Annotation of genes on the human and mouse genomes is provided by multiple public resources, using different methods, and resulting in information that is similar but not always identical. The human and mouse genome sequences are now sufficiently stable to start identifying those gene placements that are identical, and to make those data public and supported as a core set by the three major public genome browsers.

Toward this end, the Consensus CDS (CCDS) project was established. The CCDS project is a collaborative effort to identify a core set of protein coding regions that are consistently annotated and of high quality. Initial results from the Consensus CDS (CCDS) project are now available through the appropriate Ensembl gene pages and from the CCDS project page at NCBI.

The CCDS set is built by consensus among the European Bioinformatics Institute (EBI), the National Center for Biotechnology Information (NCBI), the Wellcome Trust Sanger Institute (WTSI), and the University of California at Santa Cruz (UCSC). We envision the CCDS set will become more complete as the independent curation groups agree on cases where they initially differ, as additional experimental validation of weakly supported genes occurs, and as automatic annotation methods continue to improve. Communication among the CCDS collaborating groups is an ongoing activity that will resolve differences and identify refinements between CCDS update cycles.

Annotated genes that are included in the CCDS set are associated with a unique identifier number and version number (e.g., CCDS1.1, CCDS234.1). The version number will update if the CDS structure changes, or if the underlying genome sequence changes at that location. With annotation and sequence based genome browser update cycles, the CCDS set will be mapped forward, maintaining identifiers. All changes to existing CCDS genes are done by collaboration agreement; no single group will change the set unilaterally.

The CCDS set is calculated following coordinated whole genome annotation updates carried out by the NCBI and Ensembl. Annotation updates represent genes that are defined by a mixture of manual curation and automated computational processing.

The general process flow for defining the CCDS gene set includes:

* Comparing genome annotation results.
* Identifying annotated coding regions that have identical location coordinates on the genome.
* Quality evaluation.
* Removing lower quality CDSs from the core set pending additional review among the collaboration groups.

The CCDS set includes coding regions that are annotated as full-length (with an initiating ATG and valid stop-codon), can be translated from the genome without frameshifts, and use consensus splice-sites. The number and type of quality tests performed may be expanded in the future but includes analysis to identify putative pseudogenes, retrotransposed genes, consensus splice sites, supporting transcripts, and protein homology.

