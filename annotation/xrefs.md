# External references

Ensembl pulls in links from other gene, transcript, protein and RNA databases to the same features in Ensembl, allowing you to easily navigate to see your genes of interest elsewhere.

We have four methods of mapping between databases. We employ them according to the following priorty:
1. **Direct** We use a third party to agree the mapping between the Ensembl feature and the external feature.
2. **Location overlap** We match up the genomic location of the feature between Ensembl and the external database.
3. **Perfect matches** We compare sequences to find perfect matches between databases. This is not done using the sequences themselves, rather using a checksum, which is a shortened code that represents the sequence. The checksum will only match if the sequence match is perfect.
4. **Alignment** We use Exonerate to align the sequences between the Ensembl features and the external features. We select the top hit or hits that meet a minimum threshold of identity. The alignment and the percentage identity is maintained.

We also use indirect links, using other databases as an intermediary. For example, we use direct links and alignment to map to [Uniprot proteins](http://www.uniprot.org/), then use their links out to [PDBe protein structures](https://www.ebi.ac.uk/pdbe/).

## External references sources

eg
[human icon] Human

| Database name | Website | Date of last data freeze | Database release |
| --- | --- | --- | --- |
| Uniprot | http://www.uniprot.org/ | some date in 2016 | ## |