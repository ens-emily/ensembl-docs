# Haplotypes and patches

All genome assemblies in Ensembl are haploid and for most species there is only a single path through the genome.

Currently, human and mouse are the only genome assemblies where there is more than one path through the genome. They include **haplotypes**, which are different versions of particular regions of the genome that are found in different individuals. They can include small differences in sequence, or larger differences such as different genes or gene order compared to the primary assembly. Since they are sequences found in real individuals, they are equally valid compared to the primary assembly.

The human genome assembly (GRCh38) and the mouse genome assembly (GRCm38) are maintained by the Genome Reference Consortium (GRC). In addition to the primary assembly, the GRCh38 major assembly release of the human genome included 261 alternate loci including eight haplotypes on the MHC region of chromosome six.

Subsequent minor releases on the GRC assemblies introduce additional alternate sequences known as patches. There are two types of assembly patches:

* **Novel patches**: provide alternate alleles. These regions are coloured red in the Chromosome summary page and Region in detail page. These will become haplotypes in the next major assembly release. They are equally valid compared to the primary assembly.
* **Fix patches**: provide improved sequence for known assembly errors. These patches will be incorporated into the primary assembly in the next major assembly release. They are coloured green in the Chromosome summary page and Region in detail page. They are improvements on the primary assembly and should be used preferentially over the primary assembly.

Minor assembly releases have the following naming convention: GRCm38.p3 for the third patch release of GRCm38.

In Ensembl, we display the primary assembly for all species as default. This means that our chromosome coordinates for human and mouse will match those on other genome browsers for the same major assembly release. The alternate loci are displayed alongside the primary assembly, allowing their annotation to be viewed and compared to the primary.

Video: Patches and haplotypes in the human genome