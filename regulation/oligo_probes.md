# Oligo probes

Ensembl stores microarray probe mappings for several species and technologies, including:

* Affymetrix: IVT and ST gene expression arrays
* Codelink: gene expression array
* Agilent: whole genome, CGH and SurePrint arrays
* Illumina: whole genome and Infinium methylation arrays
* Phalanx: OneArray

[View the arrays available in Ensembl](arrays.md).

## Method

Ensembl annotates expression microarrays on the genome sequences if manufacturers disclose probe sequences for a given microarray. The mapping process is a two-step procedure.

### Step One: Genome/Transcript Sequence Alignment

In the first step individual probes (oligonucleotides) are mapped to both the genome sequence and the cDNA sequence. Transcript alignments are performed to capture probes which span introns. All alignments are stored with reference to the genome sequence ie transcript alignments are reconstituted as gapped alignments against the genome. Alignments are stored as ProbeFeatures using the extended cigar format as defined by the [SAMTools group](http://samtools.github.io/hts-specs/SAMv1.pdf). Alignments are performed using the Ensembl analysis pipeline, implementing the [Exonerate](http://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-6-31) sequence comparison and alignment tool. A default 1 bp mismatch is permitted between the probe and the genome sequence assembly. Probes that match at 100 or more locations (eg suspected Alu repeats) are discarded and not stored in the database.

The resultant mappings are known as ProbeFeatures.

### Step Two: Ensembl Transcript Annotation

In the second step, we aim to associate microarray probes or probe sets with Ensembl transcript predictions (ENST...) using the ProbeFeatures generated from step one. For arrays with probe sets (eg Affymetrix®) it is normally required that more than 50% of the probes in a probe set hit a given transcript sequence. Probe set sizes are determined dynamically on a per probe set basis, rather than taking the array-wide value documented by the manufacturer. Arrays which do not contain probesets as part of their design have transcript annotations assigned directly to individual probes.

A ProbeFeature is matched to a transcript if it overlaps with an exon or UTR region with a minimum of 1bp mismatch. To account for conservative UTR estimation, transcript cDNA sequences are extended by the length of the UTR. Where annotated UTRs are absent a default UTR length is used, calculated for both five and three prime UTRs as the highest of either the mean or the median of all annotated UTRs for a given species.

## Data Access

In the Ensembl browser, individual probe alignments from step one can be displayed in the 'Region in detail' view. Probes that match to a transcript can be seen in the '[Oligo probes](http://www.ensembl.org/Homo_sapiens/Transcript/Oligos?t=ENST00000393489)' view, accessible via the transcript page.

The transcript annotations generated from the Ensembl array mapping pipeline are also available in BioMart. These data are currently incorporated into the main Ensembl genes mart, see the 'Microarray' section in the 'Attributes' panel.

Probe and ProbeSet level transcript annotations are stored in the funcgen databases, along with information on individual ProbeFeatures and objects which fail the mapping criterion are stored as UnmappedObjects. Programatic access requires the use of the [ensembl-funcgen API](http://www.ensembl.org/info/docs/api/funcgen/index.html). POD documentation is available here:

[Bio::EnsEMBL::Funcgen::Array](http://www.ensembl.org/info/docs/Doxygen/funcgen-api/classBio_1_1EnsEMBL_1_1Funcgen_1_1Array.html)
[Bio::EnsEMBL::Funcgen::Probe](http://www.ensembl.org/info/docs/Doxygen/funcgen-api/classBio_1_1EnsEMBL_1_1Funcgen_1_1Probe.html)
[Bio::EnsEMBL::Funcgen::ProbeSet](http://www.ensembl.org/info/docs/Doxygen/funcgen-api/classBio_1_1EnsEMBL_1_1Funcgen_1_1ProbeSet.html)
[Bio::EnsEMBL::Funcgen::ProbeFeature](http://www.ensembl.org/info/docs/Doxygen/funcgen-api/classBio_1_1EnsEMBL_1_1Funcgen_1_1ProbeFeature.html)

[An example script for access to these data is available here](https://raw.githubusercontent.com/Ensembl/ensembl-funcgen/release/87/scripts/examples/microarray_annotation_example.pl).

## Running The Pipeline

Fancy running your own custom array array through the Ensembl array mapping pipeline? [Further documentation about the efg array mapping environment can be found here](https://raw.githubusercontent.com/Ensembl/ensembl-funcgen/release/87/docs/array_mapping.txt).