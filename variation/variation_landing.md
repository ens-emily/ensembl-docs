# Ensembl Variation

The Ensembl Variation database stores areas of the genome that differ between individual genomes ("variants") and, where available, associated disease and phenotype information.  
There are different types of variants for several [species](data_description.html#source):

*   single nucleotide polymorphisms (SNPs)
*   short nucleotide insertions and/or deletions
*   longer variants classified as structural variants (including CNVs)

Below is a list of the most common types of variants stored in the Ensembl Variation databases:

## Sequence variants

| Type | Description | Example (Reference / Alternative) |
| --- | --- | --- |
| SNP | Single Nucleotide Polymorphism | Ref: ...TTG<span style="color:blue">**A**</span>CGTA... Alt: ...TTG<span style="red">**G**</span>CGTA... |
| Insertion | Insertion of one or more nucleotides | Ref: ...TTGACGTA... Alt: ...TTGA<span style="color:red">**TG**</span>CGTA... |
| Deletion | Deletion of one or more nucleotides | Ref: ...TTG<span style="color:blue">**AC**</span>GTA... Alt: ...TTGGTA... |
| Indel | An insertion and a deletion, affecting two or more nucleotides | Ref: ...TTG<span style="color:blue">**A**</span>CGTA... Alt: ...TTG<span style="color:red">**GCT**</span>CGTA... |
| Substitution | A sequence alteration where the length of the change in the variant is the same as that of the reference. | Ref: ...TTG<span style="color:blue">**AC**</span>GTA... Alt: ...TTG<span style="color:red">**TA**</span>GTA... |

## Structural variants

<table id="var_desc" class="ss" style="width:750px;border-radius:5px">

<tbody>

<tr>

<th style="background-color:#8b9bc1;color:#FFF;border-top-left-radius:4px">Type</th>

<th style="background-color:#8b9bc1;color:#FFF">Description</th>

<th colspan="2" style=" background-color:#8b9bc1;color:#FFF;width:50%;border-top-right-radius:4px">Example (Reference / Alternative)</th>

</tr>

<tr>

<td style="font-weight:bold">CNV</td>

<td>Copy Number Variation: increases or decreases the copy number of a given region</td>

<td>Reference:  
</td>

<td>"Gain" of one copy:  

"Loss" of one copy:</td>

</tr>

<tr class="bg2">

<td class="bg2" style="font-weight:bold">Inversion</td>

<td class="bg2">A continuous nucleotide sequence is inverted in the same position</td>

<td class="bg2">Reference:  
</td>

<td class="bg2">Alternative:  
</td>

</tr>

<tr>

<td style="font-weight:bold">Translocation</td>

<td>A region of nucleotide sequence that has translocated to a new position</td>

<td>Reference:  
</td>

<td>Alternative:  
</td>

</tr>

</tbody>

</table>

These are only some example of variant types you can find in Ensembl. The full list is available [here](/info/genome/variation/data_description.html#classes).

We predict the effects of variants on the Ensembl transcripts and regulatory features for each species. You can run the same analysis on your own data using the [Variant Effect Predictor](/info/docs/tools/vep/index.html).  
These data are integrated with other data sources in Ensembl, and can be accessed using the API (see links on the right handside menu) or website.
