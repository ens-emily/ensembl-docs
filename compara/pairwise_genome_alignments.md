Genomic alignments

Pairwise alignments and Synteny

LastZ and its predecessor BlastZ (Schwartz S et al., Genome Res.;13(1):103-7, Kent WJ et al., Proc Natl Acad Sci U S A., 2003;100(20):11484-9) are used to align the genome sequences at the DNA level. The actual whole-genome alignments are the results of post-processing the raw LastZ (or BlastZ) results. In the first step, original blocks are chained according to their location in both genomes. The netting process chooses for the reference species the best sub-chain in each region.

Translated blat (Kent W, Genome Res., 2002;12(4):656-64) can be used to look for homologous regions between more distantly related pairs of species. The rationale is that we expect to find homologies mainly in coding regions. The raw results are passed through a chain and netting procedure similar to that used for the LastZ-net analyses to produce the best sub-chain for the reference species. There are no Translated Blat Net alignments in this release of Ensembl: we use (B)LastZ for all our pairs of species.

In self-alignment analyses, the trivial alignments (i.e. regions against themselves) are removed, such that only the paralogous regions remain.

When both species have a chromosome-level assembly, we summarize the LastZ-net alignment blocks into syntenic regions. We look for stretches where the alignment blocks are in synteny. The search is run in two phases. In the first one, syntenic alignments that are closer than 200 kbp are grouped. In the second phase, the groups that are in synteny are linked provided that no more than 2 non-syntenic groups are found between them and they are less than 3Mbp apart.

Here is the list of all the pairwise comparisons that are available, grouped by reference species:

Human (Homo sapiens)

Human (Homo sapiens) [self-alignment]
Gorilla (Gorilla gorilla gorilla) with synteny analysis
Chimpanzee (Pan troglodytes) with synteny analysis
Orangutan (Pongo abelii) with synteny analysis
Gibbon (Nomascus leucogenys)
Macaque (Macaca mulatta) with synteny analysis
Olive baboon (Papio anubis) with synteny analysis
Vervet-AGM (Chlorocebus sabaeus) with synteny analysis
Marmoset (Callithrix jacchus) with synteny analysis
Tarsier (Tarsius syrichta)
Mouse Lemur (Microcebus murinus)
Bushbaby (Otolemur garnettii)
Mouse (Mus musculus) with synteny analysis
Mouse SPRET/EiJ (Mus spretus) with synteny analysis
Rat (Rattus norvegicus) with synteny analysis
Kangaroo rat (Dipodomys ordii)
Squirrel (Ictidomys tridecemlineatus)
Guinea Pig (Cavia porcellus)
Pika (Ochotona princeps)
Rabbit (Oryctolagus cuniculus) with synteny analysis
Tree Shrew (Tupaia belangeri)
Hedgehog (Erinaceus europaeus)
Shrew (Sorex araneus)
Microbat (Myotis lucifugus)
Megabat (Pteropus vampyrus)
Horse (Equus caballus) with synteny analysis
Cat (Felis catus) with synteny analysis
Dog (Canis lupus familiaris) with synteny analysis
Panda (Ailuropoda melanoleuca)
Ferret (Mustela putorius furo)
Dolphin (Tursiops truncatus)
Pig (Sus scrofa) with synteny analysis
Cow (Bos taurus) with synteny analysis
Sheep (Ovis aries) with synteny analysis
Alpaca (Vicugna pacos)
Sloth (Choloepus hoffmanni)
Armadillo (Dasypus novemcinctus)
Lesser hedgehog tenrec (Echinops telfairi)
Elephant (Loxodonta africana)
Hyrax (Procavia capensis)
Tasmanian devil (Sarcophilus harrisii)
Wallaby (Macropus eugenii)
Opossum (Monodelphis domestica) with synteny analysis
Platypus (Ornithorhynchus anatinus) with synteny analysis
Anole lizard (Anolis carolinensis) with synteny analysis
Zebra Finch (Taeniopygia guttata) with synteny analysis
Flycatcher (Ficedula albicollis)
Duck (Anas platyrhynchos)
Chicken (Gallus gallus)
Turkey (Meleagris gallopavo) with synteny analysis
Chinese softshell turtle (Pelodiscus sinensis)
Xenopus (Xenopus tropicalis)
Coelacanth (Latimeria chalumnae)
Zebrafish (Danio rerio) with synteny analysis
Cave fish (Astyanax mexicanus)
Cod (Gadus morhua)
Tilapia (Oreochromis niloticus)
Medaka (Oryzias latipes) with synteny analysis
Platyfish (Xiphophorus maculatus)
Amazon molly (Poecilia formosa)
Fugu (Takifugu rubripes)
Tetraodon (Tetraodon nigroviridis) with synteny analysis
Stickleback (Gasterosteus aculeatus) with synteny analysis
Spotted gar (Lepisosteus oculatus)
Lamprey (Petromyzon marinus)
C.intestinalis (Ciona intestinalis)
C.savignyi (Ciona savignyi)
Mouse (Mus musculus)

Rat (Rattus norvegicus) with synteny analysis
Guinea Pig (Cavia porcellus)
Shrew (Sorex araneus)
Dog (Canis lupus familiaris) with synteny analysis
Ferret (Mustela putorius furo)
Pig (Sus scrofa) with synteny analysis
Cow (Bos taurus) with synteny analysis
Platypus (Ornithorhynchus anatinus) with synteny analysis
Chicken (Gallus gallus)
Xenopus (Xenopus tropicalis)
Zebrafish (Danio rerio)
C.intestinalis (Ciona intestinalis)
Rat (Rattus norvegicus)

Zebrafish (Danio rerio)
Dog (Canis lupus familiaris)

Horse (Equus caballus) with synteny analysis
Cat (Felis catus) with synteny analysis
Panda (Ailuropoda melanoleuca)
Ferret (Mustela putorius furo)
Pig (Sus scrofa)

Cow (Bos taurus) with synteny analysis
Sheep (Ovis aries) with synteny analysis
Cow (Bos taurus)

Megabat (Pteropus vampyrus)
Cat (Felis catus) with synteny analysis
Ferret (Mustela putorius furo)
Dolphin (Tursiops truncatus)
Sheep (Ovis aries) with synteny analysis
Opossum (Monodelphis domestica)

Tasmanian devil (Sarcophilus harrisii)
Wallaby (Macropus eugenii)
Anole lizard (Anolis carolinensis)

Chinese softshell turtle (Pelodiscus sinensis)
Chicken (Gallus gallus)

Opossum (Monodelphis domestica) with synteny analysis
Anole lizard (Anolis carolinensis) with synteny analysis
Zebra Finch (Taeniopygia guttata) with synteny analysis
Flycatcher (Ficedula albicollis)
Duck (Anas platyrhynchos)
Turkey (Meleagris gallopavo) with synteny analysis
Chinese softshell turtle (Pelodiscus sinensis)
Xenopus (Xenopus tropicalis)
Zebrafish (Danio rerio) with synteny analysis
C.savignyi (Ciona savignyi)
Xenopus (Xenopus tropicalis)

Coelacanth (Latimeria chalumnae)
Tetraodon (Tetraodon nigroviridis)
Zebrafish (Danio rerio)

Xenopus (Xenopus tropicalis)
Coelacanth (Latimeria chalumnae)
Cave fish (Astyanax mexicanus)
Cod (Gadus morhua)
Tilapia (Oreochromis niloticus)
Medaka (Oryzias latipes) with synteny analysis
Platyfish (Xiphophorus maculatus)
Amazon molly (Poecilia formosa)
Fugu (Takifugu rubripes)
Tetraodon (Tetraodon nigroviridis) with synteny analysis
Stickleback (Gasterosteus aculeatus) with synteny analysis
Spotted gar (Lepisosteus oculatus) with synteny analysis
Lamprey (Petromyzon marinus)
C.intestinalis (Ciona intestinalis)
C.savignyi (Ciona savignyi)
Medaka (Oryzias latipes)

Mouse (Mus musculus) with synteny analysis
Cave fish (Astyanax mexicanus)
Cod (Gadus morhua)
Tilapia (Oreochromis niloticus)
Platyfish (Xiphophorus maculatus)
Amazon molly (Poecilia formosa)
Fugu (Takifugu rubripes)
Tetraodon (Tetraodon nigroviridis) with synteny analysis
Stickleback (Gasterosteus aculeatus) with synteny analysis
Spotted gar (Lepisosteus oculatus) with synteny analysis
Stickleback (Gasterosteus aculeatus)

Coelacanth (Latimeria chalumnae)
Cod (Gadus morhua)
Lamprey (Petromyzon marinus)
Lamprey (Petromyzon marinus)

C.intestinalis (Ciona intestinalis)
C.intestinalis (Ciona intestinalis)

C.savignyi (Ciona savignyi)

