# Manual gene annotation by Havana

Manual annotation is carried out on human, mouse, zebrafish, pig and rat genomes by the HAVANA group. It complements the automatic annotation, new transcript models and extra support for existing transcript models. Manual annotation is more sensitive than automatic annotation and aims to annotate all possible transcripts.


## How manual annotation is done

* Finished genomic sequence is analysed on a clone by clone basis using a combination of similarity searches against nucleotide and protein databases and *ab initio* gene predictions (GENSCAN, AUGUSTUS).

* In addition, sequence conservation data and a variety of DAS (Distributed Annotation System) tracks are loaded.

* The data thus gathered is then used to manually annotate genomic clones with gene and transcript structures and nomenclature and associated poly-A features, bringing in data from publications.

* The annotation is based on supporting homology evidence only and includes all types of genes: protein coding, non-coding and pseudogenes.

* There is a fine-grained classification system for [gene and transcript types](biotypes.md) (e.g. different types of pseudogenes, different types of non-coding RNAs).
