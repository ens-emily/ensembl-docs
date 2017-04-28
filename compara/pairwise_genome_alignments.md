# Pairwise whole genome alignments

Pairwise whole genome alignments can be used to determine conservation or differences between pairs of species, or to match up regions between species, so as to study the same genomic region in multiple species.

[LastZ](http://www.bx.psu.edu/~rsharris/lastz/) and its predecessor [Bla](http://europepmc.org/articles/PMC430961)[stZ](http://europepmc.org/articles/PMC208784) are used to align the genome sequences at the DNA level.

Genomes are compared to one another, for comparison between species, and to themselves, to identify paralogous regions. In self-alignment analyses, the trivial alignments (i.e. regions against themselves) are removed, such that only the paralogous regions remain.

The actual whole-genome alignments are the results of post-processing the raw LastZ (or BlastZ) results. In the first step, original blocks are chained according to their location in both genomes. The netting process chooses for the reference species the best sub-chain in each region.

These alignments are used to calculate [synteny](synteny.md) and for [scoring orthologue quality](orthology_quality_controls.md).

## Alignments available

[Table like below with search facets for species]

Species | Human | Mouse | Rat | Dog | Pig | Cow | Opossum | Anole lizard | Chicken | Xenopus | Zebrafish | Medaka | Stickleback | Lamprey | C.intestinalis
--- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
Human | [Human/Human](/info/genome/compara/mlss.html?mlss=739) (self-alignment)| [Mouse/Human](/info/genome/compara/mlss.html?mlss=677) | [Rat/Human](/info/genome/compara/mlss.html?mlss=765) | [Dog/Human](/info/genome/compara/mlss.html?mlss=710) | [Pig/Human](/info/genome/compara/mlss.html?mlss=716) | [Cow/Human](/info/genome/compara/mlss.html?mlss=709) | [Opossum/Human](/info/genome/compara/mlss.html?mlss=707) | [Anole lizard/Human](/info/genome/compara/mlss.html?mlss=722) | [Chicken/Human](/info/genome/compara/mlss.html?mlss=811) | [Xenopus/Human](/info/genome/compara/mlss.html?mlss=735) | [Zebrafish/Human](/info/genome/compara/mlss.html?mlss=767) | [Medaka/Human](/info/genome/compara/mlss.html?mlss=728) | [Stickleback/Human](/info/genome/compara/mlss.html?mlss=725) | [Human/Lamprey](/info/genome/compara/mlss.html?mlss=730) | [C.intestinalis/Human](/info/genome/compara/mlss.html?mlss=723)
Gorilla | [Human/Gorilla](/info/genome/compara/mlss.html?mlss=713) | | | | | | | | | | | | | 
Chimpanzee | [Human/Chimpanzee](/info/genome/compara/mlss.html?mlss=688) | | | | | | | | | | | | | | | 
Orangutan | [Human/Orangutan](/info/genome/compara/mlss.html?mlss=683) | | | | | | | |  | | | | | | | 
Gibbon | [Human/Gibbon](/info/genome/compara/mlss.html?mlss=679) | | | | | | | | | | | | | | | 
Macaque | [Human/Macaque](/info/genome/compara/mlss.html?mlss=820) | | | | | | | | | | | | | | | 
Olive baboon | [Human/Olive baboon](/info/genome/compara/mlss.html?mlss=745) | | | | | | | | | | | | | | | 
Vervet-AGM | [Human/Vervet-AGM](/info/genome/compara/mlss.html?mlss=757) | | | | | | | |  | | | | | | | 
Marmoset | [Human/Marmoset](/info/genome/compara/mlss.html?mlss=711) | | | | | | | | | | | | | | | 
Tarsier | [Human/Tarsier](/info/genome/compara/mlss.html?mlss=699) | | | | | | | | | | | | | | | 
Mouse Lemur | [Human/Mouse Lemur](/info/genome/compara/mlss.html?mlss=821) | | | | | | | | | | | | | | | 
Bushbaby | [Human/Bushbaby](/info/genome/compara/mlss.html?mlss=682) | | | | | | | | | | | | | | | 
Mouse | [Human/Mouse](/info/genome/compara/mlss.html?mlss=677) | | [Rat/Mouse](/info/genome/compara/mlss.html?mlss=766) | [Dog/Mouse](/info/genome/compara/mlss.html?mlss=592) | [Pig/Mouse](/info/genome/compara/mlss.html?mlss=584) | [Cow/Mouse](/info/genome/compara/mlss.html?mlss=586) | | | [Chicken/Mouse](/info/genome/compara/mlss.html?mlss=814) | [Xenopus/Mouse](/info/genome/compara/mlss.html?mlss=796) | [Zebrafish/Mouse](/info/genome/compara/mlss.html?mlss=791) | [Medaka/Mouse](/info/genome/compara/mlss.html?mlss=738) | | | [C.intestinalis/Mouse](/info/genome/compara/mlss.html?mlss=802)
Mouse SPRET/EiJ | [Human/Mouse SPRET/EiJ](/info/genome/compara/mlss.html?mlss=831) | | | | | | | | | | | | | | | 
Rat | [Human/Rat](/info/genome/compara/mlss.html?mlss=765) | [Mouse/Rat](/info/genome/compara/mlss.html?mlss=766) | | | | | | |  | | [Zebrafish/Rat](/info/genome/compara/mlss.html?mlss=792) | | | | |
Kangaroo rat | [Human/Kangaroo rat](/info/genome/compara/mlss.html?mlss=685) | | | | | | | | | | | | | | | 
Squirrel | [Human/Squirrel](/info/genome/compara/mlss.html?mlss=702) | | | | | | | | | | | | | | | 
Guinea Pig | [Human/Guinea Pig](/info/genome/compara/mlss.html?mlss=681) | [Mouse/Guinea Pig](/info/genome/compara/mlss.html?mlss=669) | | | | | | | | | | | | | | 
Pika | [Human/Pika](/info/genome/compara/mlss.html?mlss=694) | | | | | | | | | | | | | | | 
Rabbit | [Human/Rabbit](/info/genome/compara/mlss.html?mlss=680) | | | | | | | | | | | | | | | 
Tree Shrew  | [Human/Tree Shrew](/info/genome/compara/mlss.html?mlss=698) | [Mouse/Tree Shrew](/info/genome/compara/mlss.html?mlss=698) | | | | | | | | | | | | | | 
Hedgehog  | [Human/Hedgehog](/info/genome/compara/mlss.html?mlss=687) | [Mouse/Hedgehog](/info/genome/compara/mlss.html?mlss=687) | | | | | | | | | | | | | | 
Shrew  | [Human/Shrew](/info/genome/compara/mlss.html?mlss=697) | [Mouse/Shrew](/info/genome/compara/mlss.html?mlss=697) | | | | | | | | | | | | | | 
Microbat  | [Human/Microbat](/info/genome/compara/mlss.html?mlss=704) | [Mouse/Microbat](/info/genome/compara/mlss.html?mlss=704) | | | | | | | | | | | | | | 
Megabat  | [Human/Megabat](/info/genome/compara/mlss.html?mlss=696) | [Mouse/Megabat](/info/genome/compara/mlss.html?mlss=696) | | | | [Cow/Megabat](/info/genome/compara/mlss.html?mlss=676) | | | | | | | | | | 
Horse  | [Human/Horse](/info/genome/compara/mlss.html?mlss=706) | | | [Dog/Horse](/info/genome/compara/mlss.html?mlss=593) | | | | | | | | | | | | 
Cat  | [Human/Cat](/info/genome/compara/mlss.html?mlss=712) | | | [Dog/Cat](/info/genome/compara/mlss.html?mlss=670) | | [Cow/Cat](/info/genome/compara/mlss.html?mlss=674) | | | | | | | | | | 
Dog  | [Human/Dog](/info/genome/compara/mlss.html?mlss=710) | [Mouse/Dog](/info/genome/compara/mlss.html?mlss=592) | | | | | | | | | | | | | 
Panda  | [Human/Panda](/info/genome/compara/mlss.html?mlss=705) | | | [Dog/Panda](/info/genome/compara/mlss.html?mlss=594) | | | | | | | | | | | | 
Ferret  | [Human/Ferret](/info/genome/compara/mlss.html?mlss=703) | [Mouse/Ferret](/info/genome/compara/mlss.html?mlss=607) | | [Dog/Ferret](/info/genome/compara/mlss.html?mlss=671) | | [Cow/Ferret](/info/genome/compara/mlss.html?mlss=675) | | | | | | | | | | 
Dolphin  | [Human/Dolphin](/info/genome/compara/mlss.html?mlss=700) | | | | | [Cow/Dolphin](/info/genome/compara/mlss.html?mlss=673) | | | | | | | | | | | 
Pig  | [Human/Pig](/info/genome/compara/mlss.html?mlss=716) | [Mouse/Pig](/info/genome/compara/mlss.html?mlss=584) | | | | [Cow/Pig](/info/genome/compara/mlss.html?mlss=579) | | | | | | | | | | 
Cow  | [Human/Cow](/info/genome/compara/mlss.html?mlss=709) | [Mouse/Cow](/info/genome/compara/mlss.html?mlss=586) | | | [Pig/Cow](/info/genome/compara/mlss.html?mlss=579) | | | | | | | | | | | 
Sheep  | [Human/Sheep](/info/genome/compara/mlss.html?mlss=746) | | | | [Pig/Sheep](/info/genome/compara/mlss.html?mlss=663) | [Cow/Sheep](/info/genome/compara/mlss.html?mlss=666) | | | | | | | | | | 
Alpaca  | [Human/Alpaca](/info/genome/compara/mlss.html?mlss=701) | | | | | | | | | | | | | | | 
Sloth  | [Human/Sloth](/info/genome/compara/mlss.html?mlss=678) | | | | | | | | | | | | | | | 
Armadillo  | [Human/Armadillo](/info/genome/compara/mlss.html?mlss=684) | | | | | | | |  | | | | | | | 
Lesser hedgehog tenrec  | [Human/Lesser hedgehog tenrec](/info/genome/compara/mlss.html?mlss=689) | | | | | | | | | | | | | | | 
Elephant  | [Human/Elephant](/info/genome/compara/mlss.html?mlss=691) | | | | | | | | | | | | | | | 
Hyrax  | [Human/Hyrax](/info/genome/compara/mlss.html?mlss=695) | | | | | | | | | | | | | | | 
Tasmanian devil  | [Human/Tasmanian devil](/info/genome/compara/mlss.html?mlss=715) | | | | | | [Opossum/Tasmanian devil](/info/genome/compara/mlss.html?mlss=544) | | | | | | | | | 
Wallaby  | [Human/Wallaby](/info/genome/compara/mlss.html?mlss=692) | | | | | | [Opossum/Wallaby](/info/genome/compara/mlss.html?mlss=443) | | | | | | | | | 
Opossum  | [Human/Opossum](/info/genome/compara/mlss.html?mlss=707) | | | | | | | | [Chicken/Opossum](/info/genome/compara/mlss.html?mlss=808) | | | | 
Platypus  | [Human/Platypus](/info/genome/compara/mlss.html?mlss=708) | [Mouse/Platypus](/info/genome/compara/mlss.html?mlss=587) | | | | | | | | | | | | | | 
Anole lizard  | [Human/Anole lizard](/info/genome/compara/mlss.html?mlss=722) | | | | | | | | [Chicken/Anole lizard](/info/genome/compara/mlss.html?mlss=809)  | | | | | | 
Zebra Finch  | [Human/Zebra Finch](/info/genome/compara/mlss.html?mlss=731) | | | | | | | | [Chicken/Zebra Finch](/info/genome/compara/mlss.html?mlss=816) | | | | | | 
Flycatcher  | [Human/Flycatcher](/info/genome/compara/mlss.html?mlss=718) | | | | | | | | [Chicken/Flycatcher](/info/genome/compara/mlss.html?mlss=819) | | | | | | 
Duck  | [Human/Duck](/info/genome/compara/mlss.html?mlss=717) | | | | | | | | [Chicken/Duck](/info/genome/compara/mlss.html?mlss=818) | | | | | |  
Chicken  | [Human/Chicken](/info/genome/compara/mlss.html?mlss=811) | [Mouse/Chicken](/info/genome/compara/mlss.html?mlss=814) | | | | | | | | | | | | | | 
Turkey  | [Human/Turkey](/info/genome/compara/mlss.html?mlss=736) | | | | | | | | [Chicken/Turkey](/info/genome/compara/mlss.html?mlss=817) | | | | | | 
Chinese softshell turtle  | [Human/Chinese softshell turtle](/info/genome/compara/mlss.html?mlss=720) | | | | | | | [Anole lizard/Chinese softshell turtle](/info/genome/compara/mlss.html?mlss=596) | [Chicken/Chinese softshell turtle](/info/genome/compara/mlss.html?mlss=810) | | | | | | 
Xenopus  | [Human/Xenopus](/info/genome/compara/mlss.html?mlss=735) | [Mouse/Xenopus](/info/genome/compara/mlss.html?mlss=796) | | | | | | | [Chicken/Xenopus](/info/genome/compara/mlss.html?mlss=813) | | [Zebrafish/Xenopus](/info/genome/compara/mlss.html?mlss=786) | | | | | 
Coelacanth  | [Human/Coelacanth](/info/genome/compara/mlss.html?mlss=727) | | | | | | | | | [Xenopus/Coelacanth](/info/genome/compara/mlss.html?mlss=800) | | | | | | | [Zebrafish/Coelacanth](/info/genome/compara/mlss.html?mlss=783) | | [Stickleback/Coelacanth](/info/genome/compara/mlss.html?mlss=804) | | | 
Zebrafish  | [Human/Zebrafish](/info/genome/compara/mlss.html?mlss=767) | [Mouse/Zebrafish](/info/genome/compara/mlss.html?mlss=791) | [Rat/Zebrafish](/info/genome/compara/mlss.html?mlss=792) | | | | | | [Chicken/Zebrafish](/info/genome/compara/mlss.html?mlss=815) | | | [Medaka/Zebrafish](/info/genome/compara/mlss.html?mlss=772) | [Stickleback/Zebrafish](/info/genome/compara/mlss.html?mlss=770) | [Lamprey/Zebrafish](/info/genome/compara/mlss.html?mlss=785) | [C.intestinalis/Zebrafish](/info/genome/compara/mlss.html?mlss=784)
Cave fish  | [Human/Cave fish](/info/genome/compara/mlss.html?mlss=751) | | | | | | | | | | [Zebrafish/Cave fish](/info/genome/compara/mlss.html?mlss=776) | [Medaka/Cave fish](/info/genome/compara/mlss.html?mlss=649) | | | | 
Cod  | [Human/Cod](/info/genome/compara/mlss.html?mlss=726) | | | | | | | | | | [Zebrafish/Cod](/info/genome/compara/mlss.html?mlss=773) | [Medaka/Cod](/info/genome/compara/mlss.html?mlss=625) | [Stickleback/Cod](/info/genome/compara/mlss.html?mlss=555) | | | 
Tilapia  | [Human/Tilapia](/info/genome/compara/mlss.html?mlss=729) | | | | | | | | | | [Zebrafish/Tilapia](/info/genome/compara/mlss.html?mlss=774) | [Medaka/Tilapia](/info/genome/compara/mlss.html?mlss=626) | | | | 
Medaka  | [Human/Medaka](/info/genome/compara/mlss.html?mlss=728) | [Mouse/Medaka](/info/genome/compara/mlss.html?mlss=738) | | | | | | | | | [Zebrafish/Medaka](/info/genome/compara/mlss.html?mlss=772) | | | | | 
Platyfish  | [Human/Platyfish](/info/genome/compara/mlss.html?mlss=734) | | | | | | | | | | [Zebrafish/Platyfish](/info/genome/compara/mlss.html?mlss=775) | [Medaka/Platyfish](/info/genome/compara/mlss.html?mlss=627) | | | | 
Amazon molly  | [Human/Amazon molly](/info/genome/compara/mlss.html?mlss=747) | | | | | | | | | | [Zebrafish/Amazon molly](/info/genome/compara/mlss.html?mlss=778) | [Medaka/Amazon molly](/info/genome/compara/mlss.html?mlss=748) | | | | 
Fugu  | [Human/Fugu](/info/genome/compara/mlss.html?mlss=733) | | | | | | | | | | [Zebrafish/Fugu](/info/genome/compara/mlss.html?mlss=769) | [Medaka/Fugu](/info/genome/compara/mlss.html?mlss=795) | | | |
Tetraodon  | [Human/Tetraodon](/info/genome/compara/mlss.html?mlss=732) | | | | | | | | | [Xenopus/Tetraodon](/info/genome/compara/mlss.html?mlss=803) | | | | | | | [Zebrafish/Tetraodon](/info/genome/compara/mlss.html?mlss=771) | [Medaka/Tetraodon](/info/genome/compara/mlss.html?mlss=764) | | | | 
Stickleback  | [Human/Stickleback](/info/genome/compara/mlss.html?mlss=725) | | | | | | | | | | [Zebrafish/Stickleback](/info/genome/compara/mlss.html?mlss=770) | [Medaka/Stickleback](/info/genome/compara/mlss.html?mlss=225) | | [Lamprey/Stickleback](/info/genome/compara/mlss.html?mlss=799) |
Spotted gar  | [Human/Spotted gar](/info/genome/compara/mlss.html?mlss=752) | | | | | | | | | | [Zebrafish/Spotted gar](/info/genome/compara/mlss.html?mlss=777) | [Medaka/Spotted gar](/info/genome/compara/mlss.html?mlss=653) | | | | 
Lamprey  | [Human/Lamprey](/info/genome/compara/mlss.html?mlss=730) | | | | | | | | | | [Zebrafish/Lamprey](/info/genome/compara/mlss.html?mlss=785) | | [Stickleback/Lamprey](/info/genome/compara/mlss.html?mlss=799) | | |
C.intestinalis  | [Human/C.intestinalis](/info/genome/compara/mlss.html?mlss=723) | [Mouse/C.intestinalis](/info/genome/compara/mlss.html?mlss=802) | | | | | | | | | [Zebrafish/C.intestinalis](/info/genome/compara/mlss.html?mlss=784) | | | [Lamprey/C.intestinalis](/info/genome/compara/mlss.html?mlss=798) | | | 
C.savignyi  | [Human/C.savignyi](/info/genome/compara/mlss.html?mlss=721) | | | | | | | | [Chicken/C.savignyi](/info/genome/compara/mlss.html?mlss=812) | | [Zebrafish/C.savignyi](/info/genome/compara/mlss.html?mlss=787) | | | | [C.intestinalis/C.savignyi](/info/genome/compara/mlss.html?mlss=569) |
