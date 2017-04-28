The EPO pipeline is split into 3 parts

1). Anchor generation

The anchors represent short regions of conservation, typically about 100 bases in length, from a phylogenetically representative subset of the species we wish to align. The anchor set is generated from pairwise alignments (LastZ-Net / BlastZ-Net) of a non-reference species to a reference species (human is the reference in our case), so all the species chosen to generate the anchors must have a pairwise alignment with the reference species. 
We then use the alignment coordinates from the reference genome to find sets of overlapping sequences from the chosen pairwise alignments.
See a list of the pairwise alignments in Ensembl

2). Anchor mapping

The anchor set is mapped (currently we use exonerate) against all the genomes we wish to include in the final alignment.
Overlapping anchor mappings are filtered so that any particular genomic location is associated with, at most, one anchor.

3). Graph generation using Enredo followed by Alignment using Pecan/Ortheus

Enredo produces a list of homologous genomic regions from the positions where the anchors have mapped.
These homologous regions are then aligned with Pecan or Ortheus (Ortheus uses Pecan to do the aligning and also generates a sequence for each ancestral node in a tree which it predicts for each region).

Notes

Not all parts of the pipeline may be run for each Ensembl release, for instance we may only have to generate a new set of anchors infrequently.

Mapping of the anchors to the genomes takes the most time, however, it is a cumulative process (for each new genome, we need only map the anchors to it and add these mappings to the set of mappings which were done in previous releases).

Aligning the sequences is done anew with each release (assuming there is a new species added or an updated assembly)

The following pipeconfig files (~/ensembl-compara/modules/Bio/EnsEMBL/Compara/PipeConfig)
are used for setting up the eHive for running the 3 pipeline stages:
1) anchor generation : EPO_pt1_conf.pm
2) anchor mapping : EPO_pt2_conf.pm
3) graph generation followed by aligning : EPO_pt3_conf.pm
For the current release the following set of species were used to generate the anchor set used for the mammalian and primate EPO alignments :

Bos taurus
Canis familiaris
Equus caballus
Homo sapiens
Mus musculus
Oryctolagus cuniculus
Rattus norvegicus
Sus scrofa
Felis catus
