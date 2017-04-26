PECAN Multiple Alignment

Pecan is used to provide global multiple genomic alignments. First, Mercator is used to build a synteny map between the genomes and then Pecan builds alignments in these syntenic regions.

Pecan is a global multiple sequence alignment program that makes practical the probabilistic consistency methodology for significant numbers of sequences of practically arbitrary length. As input it takes a set of sequences and a phylogenetic tree. The parameters and heuristics it employs are highly user configurable, it is written entirely in Java and also requires the installation of Exonerate. Pecan source code.

24 amniota vertebrates Pecan
EPO Multiple Alignment

The EPO (Enredo, Pecan, Ortheus) pipeline is a three step pipeline for whole-genome multiple alignments. Enredo produces colinear segments from extant genomes handling both rearrangements, deletions and duplications. Pecan, as described above, is used to align these segments. Finally, Ortheus is used to create genome-wide ancestral sequence reconstructions. Further details on these methods can be found at:

Enredo and Pecan: Genome-wide mammalian consistency-based multiple alignment with paralogs
Genome-wide nucleotide-level mammalian ancestor reconstruction
Ancestral sequences are inferred from the EPO multiple alignments using Ortheus. Ortheus is a probabilistic method for the inference of ancestor, a.k.a tree, alignments. The main contribution of Ortheus is the use of a phylogenetic model incorporating gaps to infer insertion and deletion events. Ancestral sequences are predicted for each node of the phylogenetic tree that relates the sequences. Each ancestral sequence is named according to the derived extant species. For example, a sequence named Hsap, Ptro, Mmul corresponds to the ancestor of the Homo sapiens, Pan troglodytes, and Macaca mulatta genomes.

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
Age of Base

From those ancestral sequences, we infer the age of a base, i.e. the timing of the most recent mutation for each base of the genome. Each position of the genome is compared to its immediate inferred ancestor, then its ancestor, etc. until a difference is found. The inferred substitution event therefore occurred on a specific branch of the tree, which is identified by all the extant species which eventually descended from that branch, as illustrated below.

Age of Base schema
This track is currently only available for the human genome.
