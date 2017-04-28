# Multiple genome alignments

Multiple alignments are calculated between groups of genomes. These are used to calculate [ancestral sequences](ancestral_sequences.md), [age of base](age_of_base.md), [conservation scores and constrained elements](conservation_and_constrained.md).

## Alignments available

Name | Genomes | Method used
--- | --- | ---
[24 amniota vertebrates](http://www.ensembl.org/info/genome/compara/mlss.html?mlss=830) | Human, Gorilla, Chimpanzee, Orangutan, Macaque, Olive, Vervet-AGM, Marmoset, Mouse, Mouse, Rat, Rabbit, Horse, Cat, Dog, Pig, Cow, Sheep, Opossum, Platypus, Anole lizard, Zebra, Chicken, Turkey | PECAN
[5 teleost fish](http://www.ensembl.org/info/genome/compara/mlss.html?mlss=768) | Zebrafish, Medaka, Tetraodon, Stickleback, Spotted gar | EPO
8 primates |  | EPO
4 sauropsids |  | EPO
18 eutherian mammals |  | EPO
11 fish |  | EPO_LOW_COVERAGE
7 sauropsids |  | EPO_LOW_COVERAGE
40 eutherian mammals |  | EPO_LOW_COVERAGE
18 murinae |  | Cactus alignment

## Alignment methods

PECAN Multiple Alignment

Pecan is used to provide global multiple genomic alignments. First, Mercator is used to build a synteny map between the genomes and then Pecan builds alignments in these syntenic regions.

Pecan is a global multiple sequence alignment program that makes practical the probabilistic consistency methodology for significant numbers of sequences of practically arbitrary length. As input it takes a set of sequences and a phylogenetic tree. The parameters and heuristics it employs are highly user configurable, it is written entirely in Java and also requires the installation of Exonerate. Pecan source code.

24 amniota vertebrates Pecan
EPO Multiple Alignment

The EPO (Enredo, Pecan, Ortheus) pipeline is a three step pipeline for whole-genome multiple alignments. Enredo produces colinear segments from extant genomes handling both rearrangements, deletions and duplications. Pecan, as described above, is used to align these segments. Finally, Ortheus is used to create genome-wide ancestral sequence reconstructions. Further details on these methods can be found at:

Enredo and Pecan: Genome-wide mammalian consistency-based multiple alignment with paralogs

Due to difficulties with running Ortheus on the fragmented assemblies, we have two flavours of the pipeline. First, the plain EPO pipeline is available on the chromosome-level genomes:

5 teleost fish EPO
8 primates EPO
4 sauropsids EPO
18 eutherian mammals EPO
The scaffold-level genomes are then projected onto the EPO alignments using LastZ-net alignments:

11 fish EPO_LOW_COVERAGE
7 sauropsids EPO_LOW_COVERAGE
40 eutherian mammals EPO_LOW_COVERAGE
By construction, each pair of EPO and EPO_LOW_COVERAGE alignments represent the exact same alignment of chromosome-level genomes.

Progressive Cactus

Progressive-Cactus is a next-generation aligner that stores whole-genome alignments in a graph structure. Genomes can be added incrementally, which makes it scalable to hundreds of genomes. Further details on these methods can be found in Algorithms for genome multiple sequence alignment and Cactus graphs for genome comparisons.

18 murinae Cactus alignment
