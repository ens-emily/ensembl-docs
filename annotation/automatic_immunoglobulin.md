# Annotation of immunoglobulin and T-cell receptor genes

## VDJ recombination

![Diagram of VDJ recombination](https://upload.wikimedia.org/wikipedia/commons/3/3e/VDJ_recombination.png "VDJ recombination")

The Immunoglobulin (Ig) and T-cell receptor (Tcr) genes are present in germ-line genomic DNA. They comprise the four segment types, variable (V), diversity (D), joining (J) and constant (C), which are rearranged and brought together by [VDJ recombination](https://en.wikipedia.org/wiki/V(D)J_recombination) to form functional Ig and Tcr genes during B-cell and T-cell maturation. This results in genetically different B-cells and T-cells, which encode different proteins to recognise specific antigens as part of the acquired immune system.

The protein and nucleotide databases contain many sequences of mature Ig/Tcr genes. Inferring gene structures by aligning these to the genome using the standard Ensembl annotation process pipeline gives unsatisfactory results, for two main reasons:

* The non-coding DNA that separates pairs of gene segments brought together by V-D-J recombination is not an intron, and the gene boundaries display different sequence signals to splice sites. Spliced alignment programs such as [GeneWise](http://genome.cshlp.org/content/14/5/988) therefore require retuning in order to predict the gene structure correctly.

* Some genes comprise multiple exons. Delineating a "spliced" alignment of a mature Ig/Tcr sequence to the genome into its constituent segments is therefore not straightforward.

## Annotation of Ig/Tcr genes

For this reason, Ig/Tcr gene segments have been annotated differently to other Ensembl genes. Ensembl makes use of the [IMGT](http://www.imgt.org/) database, which provides annotation of individual gene segments on reference sequences. Ensembl use a combination of manual annotation by [Havana](manual_havana.md) and automatic annotation by extracting individual gene sequences and aligning them to the genome using the [Exonerate](http://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-6-31) alignment tool for Ig/Tcr genes.

To reflect their role in the VDJ recombination process, segments are annotated as belonging to one of four classes: V, D, J and C. At present, Ensembl Ig/Tcr gene annotations are only available for human and mouse.

## References

Lefranc M.-P., Giudicelli V., Kaas Q., Duprat E., Jabado-Michaloud J., Scaviner D., Ginestoux C., Clément O., Chaume D. and Lefranc G.
IMGT, the international ImMunoGeneTics information system.
Nucl. Acids Res. 2005 33:D593-D597

Slater G.S. and Birney E.
Automated generation of heuristics for biological sequence comparison.
BMC Bioinformatics 2005 6:31
doi:10.1186/1471-2105-6-31

Ewan Birney, Michele Clamp and Richard Durbin
GeneWise and Genomewise
Genome Research 2004 14(5):988-995. doi:10.1101/gr.1865504
