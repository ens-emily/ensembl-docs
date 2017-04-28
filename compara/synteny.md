# Synteny

[Synteny](https://en.wikipedia.org/wiki/Synteny) is the conserved order of aligned genomic blocks between species. It is calculated from the [pairwise genome alignments](pairwise_genome_alignments.md) created by Ensembl, when both species have a chromosome-level assembly.

The search is run in two phases:
1. We search for alignment blocks that are in the same order in the two genomes. Syntenic alignments that are closer than 200 kb are grouped into a synteny block.
2. Groups that are in synteny are linked, provided that no more than two non-syntenic groups are found between them and they are less than 3 Mb apart.

Here is the list of all the synteny comparisons that are available:

[Table like below with search facets for species]

Species | Human | Mouse | Dog | Pig | Cow | Chicken | Zebrafish | Medaka
--- | --- | --- | --- | --- | --- | --- | --- | ---
Human |  | [Mouse/Human](/info/genome/compara/mlss.html?mlss=10080) | [Dog/Human](/info/genome/compara/mlss.html?mlss=10099) | [Pig/Human](/info/genome/compara/mlss.html?mlss=10084) | [Cow/Human](/info/genome/compara/mlss.html?mlss=10098) |  | [Zebrafish/Human](/info/genome/compara/mlss.html?mlss=10112) | [Medaka/Human](/info/genome/compara/mlss.html?mlss=10089)
Gorilla | [Human/Gorilla](/info/genome/compara/mlss.html?mlss=10094) |  |  |  |  |  |  | 
Chimpanzee | [Human/Chimpanzee](/info/genome/compara/mlss.html?mlss=10082) |  |  |  |  |  |  | 
Orangutan | [Human/Orangutan](/info/genome/compara/mlss.html?mlss=10106) |  |  |  |  |  |  | 
Macaque | [Human/Macaque](/info/genome/compara/mlss.html?mlss=10135) |  |  |  |  |  |  | 
Olive baboon | [Human/Olive baboon](/info/genome/compara/mlss.html?mlss=10102) |  |  |  |  |  |  | 
Vervet-AGM | [Human/Vervet-AGM](/info/genome/compara/mlss.html?mlss=10105) |  |  |  |  |  |  | 
Marmoset | [Human/Marmoset](/info/genome/compara/mlss.html?mlss=10101) |  |  |  |  |  |  | 
Mouse | [Human/Mouse](/info/genome/compara/mlss.html?mlss=10080) |  | [Mouse/Dog](/info/genome/compara/mlss.html?mlss=10063) |  |  |  |  | [Medaka/Mouse](/info/genome/compara/mlss.html?mlss=10123)
Mouse SPRET/EiJ | [Human/Mouse SPRET/EiJ](/info/genome/compara/mlss.html?mlss=10136) |  |  |  |  |  |  | 
Rat | [Human/Rat](/info/genome/compara/mlss.html?mlss=10110) |  |  |  |  |  |  | 
Rabbit | [Human/Rabbit](/info/genome/compara/mlss.html?mlss=10081) |  |  |  |  |  |  | 
Horse | [Human/Horse](/info/genome/compara/mlss.html?mlss=10095) |  | [Dog/Horse](/info/genome/compara/mlss.html?mlss=10064) |  | [Cow/Cat](/info/genome/compara/mlss.html?mlss=10079) |  |  | 
Cat | [Human/Cat](/info/genome/compara/mlss.html?mlss=10100) |  | [Dog/Cat](/info/genome/compara/mlss.html?mlss=10078) |  |  |  |  | 
Dog | [Human/Dog](/info/genome/compara/mlss.html?mlss=10099) | [Mouse/Dog](/info/genome/compara/mlss.html?mlss=10063) |  |  |  |  |  | 
Pig | [Human/Pig](/info/genome/compara/mlss.html?mlss=10084) |  |  |  | [Cow/Pig](/info/genome/compara/mlss.html?mlss=10056) |  |  | 
Cow | [Human/Cow](/info/genome/compara/mlss.html?mlss=10098) | [Mouse/Pig](/info/genome/compara/mlss.html?mlss=10059) |  | [Pig/Cow](/info/genome/compara/mlss.html?mlss=10056) |  |  |  | 
Sheep | [Human/Sheep](/info/genome/compara/mlss.html?mlss=10103) | [Mouse/Cow](/info/genome/compara/mlss.html?mlss=10061) |  | [Pig/Sheep](/info/genome/compara/mlss.html?mlss=10076) | [Cow/Sheep](/info/genome/compara/mlss.html?mlss=10075) |  |  | 
Opossum | [Human/Opossum](/info/genome/compara/mlss.html?mlss=10096) | [Mouse/Platypus](/info/genome/compara/mlss.html?mlss=10062) |  |  |  | [Chicken/Opossum](/info/genome/compara/mlss.html?mlss=10132) |  | 
Platypus | [Human/Platypus](/info/genome/compara/mlss.html?mlss=10097) |  |  |  |  |  |  | 
Anole lizard | [Human/Anole lizard](/info/genome/compara/mlss.html?mlss=10086) |  |  |  |  | [Chicken/Anole lizard](/info/genome/compara/mlss.html?mlss=10131) |  | 
Zebra finch | [Human/Zebra finch](/info/genome/compara/mlss.html?mlss=10091) |  |  |  |  | [Chicken/Zebra finch](/info/genome/compara/mlss.html?mlss=10130) |  | 
Turkey | [Human/Turkey](/info/genome/compara/mlss.html?mlss=10092) |  |  |  |  | [Chicken/Turkey](/info/genome/compara/mlss.html?mlss=10129) |  | 
Zebrafish | [Human/Zebrafish](/info/genome/compara/mlss.html?mlss=10112) |  |  |  |  | [Chicken/Zebrafish](/info/genome/compara/mlss.html?mlss=10134) |  | [Medaka/Zebrafish](/info/genome/compara/mlss.html?mlss=10116)
Medaka | [Human/Medaka](/info/genome/compara/mlss.html?mlss=10089) |  |  |  |  |  | [Zebrafish/Medaka](/info/genome/compara/mlss.html?mlss=10116) | 
Tetraodon | [Human/Tetraodon](/info/genome/compara/mlss.html?mlss=10090) |  |  |  |  |  | [Zebrafish/Tetraodon](/info/genome/compara/mlss.html?mlss=10115) | [Medaka/Tetraodon](/info/genome/compara/mlss.html?mlss=10109)
Stickleback | [Human/Stickleback](/info/genome/compara/mlss.html?mlss=10088) |  |  |  |  |  | [Zebrafish/Stickleback](/info/genome/compara/mlss.html?mlss=10114) | [Medaka/Stickleback](/info/genome/compara/mlss.html?mlss=10119)
Spotted gar |  |  |  |  |  |  | [Zebrafish/Spotted gar](/info/genome/compara/mlss.html?mlss=10117) | [Medaka/Spotted](/info/genome/compara/mlss.html?mlss=10121)
