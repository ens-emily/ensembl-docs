# Multiple genome alignments

Multiple alignments are calculated between groups of genomes. These are used to calculate [ancestral sequences](ancestral_sequences.md), [age of base](age_of_base.md), [conservation scores and constrained elements](conservation_and_constrained.md).

## Alignments available

Name | Genomes | Method used
--- | --- | ---
[31 amniota vertebrates](http://www.ensembl.org/info/genome/compara/mlss.html?mlss=1104) | Human, Chimpanzee, Bonobo, Gorilla, Orangutan, Gibbon, Olive baboon, Vervet-AGM, Macaque, Crab-eating macaque, Marmoset, Mouse lemur, Mouse, Algerian mouse, Ryukyu mouse, Shrew mouse, Rat, Prairie vole, Rabbit, Cow, Sheep, Pig, Dog, Cat, Horse, Opossum, Platypus, Chicken, Turkey, Zebra finch, Anole lizard | PECAN
[5 teleost fish](http://www.ensembl.org/info/genome/compara/mlss.html?mlss=768) | Zebrafish, Medaka, Tetraodon, Stickleback, Spotted gar | EPO
[12 primates](http://www.ensembl.org/info/genome/compara/mlss.html?mlss=1101) | Human, Gorilla, Chimpanzee, Bonobo, Orangutan, Gibbon, Crab-eating macaque, Macaque, Olive baboon, Vervet-AGM, Marmoset, Mouse lemur  | EPO
[4 sauropsids](http://www.ensembl.org/info/genome/compara/mlss.html?mlss=825) | Anole lizard, Zebra finch, Chicken, Turkey | EPO
[25 eutherian mammals](http://www.ensembl.org/info/genome/compara/mlss.html?mlss=1102) | Human, Chimpanzee, Bonobo, Gorilla, Orangutan, Gibbon, Olive baboon, Vervet-AGM, Macaque, Crab-eating macaque, Marmoset, Mouse lemur, Mouse, Algerian mouse, Ryukyu mouse, Shrew mouse, Rat, Prairie vole, Rabbit, Cow, Sheep, Pig, Dog, Cat, Horse | EPO
[11 fish](http://www.ensembl.org/info/genome/compara/mlss.html?mlss=793) | Zebrafish, Cave fish, Cod, Tilapia, Medaka, Platyfish, Amazon molly, Fugu, Tetraodon, Stickleback, Spotted gar  | EPO_LOW_COVERAGE
[7 sauropsids](http://www.ensembl.org/info/genome/compara/mlss.html?mlss=826) | Duck, Chicken, Turkey, Chinese softshell turtle, Anole lizard, Zebra finch, Flycatcher | EPO_LOW_COVERAGE
[67 eutherian mammals](http://www.ensembl.org/info/genome/compara/mlss.html?mlss=1103) | Human, Chimpanzee, Bonobo, Gorilla, Orangutan, Gibbon, Angola colobus, Golden snub-nosed monekey, Black snub-nosed monkey, Pig-tailed macaque, Macaque, Crab-eating macaque, Olive baboon, Vervet-AGM, Sooty mangabey, Drill, Marmoset, Capuchin, Bolivian squirrel monkey, Ma's night monkey, Tarsier, Coquerel's sifaka, Mouse lemur, Bushbaby, Mouse, Algerian mouse, Ryukyu mouse, Shew mouse, Rat, Upper Gallilee mountains blnd mole rat, Chinese hamster CriGri, Chinese hamster CHOK1GS, Golden Hamster, Northern American deer mouse, Prairie vole, Lesser Egyptian jerboa, Kangaroo rat, Long-tailed chinchilla, Guinea pig, Brazilian guinea pig, Degu, Naked mole rate female, Naked mole rat male, Damara mole rat, Squirrel, Pika, Rabbit, Tree shrew, Horse, Dog, Panda, Ferret, Cat, Hedgehog, Shrew, Cow, Sheep, Dolphin, Alpaca, Pig, Microbat, Megabat, Sloth, Armadillo, Lesser hedgehog tenrec, Hyrax, Elephant | EPO_LOW_COVERAGE
[18 murinae](http://www.ensembl.org/info/genome/compara/mlss.html?mlss=835) | Mouse , Mouse DBA/2J, Mouse CAST/EiJ, Mouse C57BL/6NJ, Mouse C3H/HeJ, Mouse WSB/EiJ, Mouse A/J, Mouse BALB/cJ, Mouse LP/J, Mouse NOD/ShiLtJ, Mouse 129S1/SvImJ, Mouse CBA/J, Mouse AKR/J, Mouse NZO/HlLtJ, Mouse FVB/NJ, Mouse PWK/PhJ, Mouse SPRET/EiJ, Rat  | Cactus alignment

## Alignment methods

### PECAN Multiple Alignment

[Pecan](http://hgwdev.cse.ucsc.edu/~benedict/code/Pecan.html) is used to provide global multiple genomic alignments. First, Mercator is used to build a synteny map between the genomes and then Pecan builds alignments in these syntenic regions.

Pecan is a global multiple sequence alignment program that makes practical the probabilistic consistency methodology for significant numbers of sequences of practically arbitrary length. As input it takes a set of sequences and a phylogenetic tree. The parameters and heuristics it employs are highly user configurable, it is written entirely in Java and also requires the installation of Exonerate.

### EPO Multiple Alignment

The [EPO (Enredo, Pecan, Ortheus) pipeline](EPO_pipeline.md) is a three step pipeline for whole-genome multiple alignments.
1. Enredo produces colinear segments from extant genomes handling both rearrangements, deletions and duplications.
2. Pecan, as described above, is used to align these segments.
3. Finally, Ortheus is used to create genome-wide ancestral sequence reconstructions.

Further details on these methods can be found at: [Enredo and Pecan: Genome-wide mammalian consistency-based multiple alignment with paralogs](http://europepmc.org/abstract/MED/18849524)

Due to difficulties with running Ortheus on the fragmented assemblies, we have two flavours of the pipeline.
1. The plain EPO pipeline is available on the chromosome-level genomes, listed as EPO in the table above
2. The scaffold-level genomes are then projected onto the EPO alignments using LastZ-net alignments, listed as EPO_LOW_COVERAGE.

By construction, each pair of EPO and EPO_LOW_COVERAGE alignments represent the exact same alignment of chromosome-level genomes.

### Progressive Cactus

Progressive-Cactus is a next-generation aligner that stores whole-genome alignments in a graph structure. Genomes can be added incrementally, which makes it scalable to hundreds of genomes. Further details on these methods can be found in [Algorithms for genome multiple sequence alignment](http://europepmc.org/articles/PMC3166836) and [Cactus graphs for genome comparisons](http://europepmc.org/abstract/MED/21385048).
