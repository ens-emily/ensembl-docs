# Repeats

Repetitive sequence is found throughout genomes. It is important to mask repeats before gene annotation, as repeats will cause non-specific gene hits. Repeats are also useful for studying evolution and for DNA fingerprinting.

## Types of repeats

| Repeat type | Definition |
| --- | --- |
| Centromere | The region of the chromosome at which the two sister chromatids are joined during mitosis and meiosis, mostly composed of satellite DNA. |
| Low complexity regions | Poly-purine or poly-pyrimidine stretches, or regions of extremely high AT or GC content. |
| RNA repeats | Non-functional copies of RNA genes which have been reintegrated into the genome with the assistance of a reverse transcriptase. |
| Satellite repeats | Multiple copies of the same base sequence on a DNA sequence. The repeated pattern can vary in length from a single base to several thousand bases long. |
| Simple repeats | Duplications of simple sets of DNA bases (typically 1-5bp) such as A, CA, CGG etc.|
| Tandem repeats | Typically found at the centromeres and telomeres of chromosomes these are duplications of more complex 100-200 base sequences. |
| LTRs | Long tandem repeats. |
| Type I Transposons/LINE | Long Interspersed Elements. Retrotransposed elements in the genome containing open reading frames encoding (often inactive) reverse transcription machinery. |
| Type I Transposons/SINE | Short Interspersed Elements. Retrotransposed elements less than 500 bp that contain tRNA, snRNA and rRNA, which require other mobile elements to be transposed. Alu elements are a type of SINE. |
| Type II Transposons | Elements that have been transposed and duplicated around the genome by excision and ligation. |
| Unknown | Repeats that cannot be classified. |

## Masking the repeats

Ensembl mask repeats using [Repeat Masker](http://www.repeatmasker.org/) and [Dust](http://europepmc.org/abstract/MED/16796549).

Repeats can be viewed in the browser and extracted using our APIs. You can also download repeat-masked sequence from our FTP site, either hard-masked (rm) where repeats are replaced with Ns, or soft-masked (sm) where repeats are in lower-case text.
