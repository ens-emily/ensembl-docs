## Variant classes

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

| Type | Description | Example (Reference / Alternative) |
| --- | --- | --- |
| CNV | Copy Number Variation: increases or decreases the copy number of a given region | Reference: "Gain" of one copy: "Loss" of one copy: |
| Inversion | A continuous nucleotide sequence is inverted in the same position | Reference: Alternative:  |
| Translocation | A region of nucleotide sequence that has translocated to a new position | Reference: Alternative: |

## Variant classes

We call the class of a variant according to its component alleles and its mapping to the reference genome, and then display this information on the website. Internally we use [Sequence Ontology](http://www.sequenceontology.org/) terms, but we map these to our own 'display' terms where common usage differs from the SO definition (e.g. our term SNP is closer to the SO term SNV). All the classes we call, along with their equivalent SO term are shown in the table below. We also differentiate somatic mutations from germline variants in the display term, prefixing the term with 'somatic'. API users can fetch either the SO term or the display term.

<table id="variation_classes" class="ss">

<tbody>

<tr>

<th style="width:8px;padding-left:0px;padding-right:0px;text-align:center">*</th>

<th>SO term</th>

<th>SO description</th>

<th>SO accession</th>

<th colspan="2">Called for (e.g.)</th>

</tr>

<tr>

<td style="padding:0px;margin:0px;"></td>

<td style="font-weight:bold">SNV</td>

<td>SNVs are single nucleotide positions in genomic DNA at which different sequence alternatives exist.</td>

<td>[SO:0001483](http://www.sequenceontology.org/miso/current_release/term/SO:0001483)</td>

<td>

*   Variant

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/Variation/Explore?v=rs3 "See a variant example")</div>

</td>

</tr>

<tr class="bg2">

<td style="padding:0px;margin:0px;"></td>

<td style="font-weight:bold">genetic_marker</td>

<td>A measurable sequence feature that varies within a population.</td>

<td>[SO:0001645](http://www.sequenceontology.org/miso/current_release/term/SO:0001645)</td>

<td>

*   Variant

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/Variation/Explore?v=rs111226187 "See a variant example")</div>

</td>

</tr>

<tr>

<td style="padding:0px;margin:0px;"></td>

<td style="font-weight:bold">substitution</td>

<td>A sequence alteration where the length of the change in the variant is the same as that of the reference.</td>

<td>[SO:1000002](http://www.sequenceontology.org/miso/current_release/term/SO:1000002)</td>

<td>

*   Variant

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/Variation/Explore?v=rs1800995 "See a variant example")</div>

</td>

</tr>

<tr class="bg2">

<td style="padding:0px;margin:0px;"></td>

<td style="font-weight:bold">tandem_repeat</td>

<td>Two or more adjacent copies of a region (of length greater than 1).</td>

<td>[SO:0000705](http://www.sequenceontology.org/miso/current_release/term/SO:0000705)</td>

<td>

*   Variant

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/Variation/Explore?v=rs1805180 "See a variant example")</div>

</td>

</tr>

<tr>

<td style="padding:0px;margin:0px;;background-color:#000080;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">Alu_insertion</td>

<td>An insertion of sequence from the Alu family of mobile elements.</td>

<td>[SO:0002063](http://www.sequenceontology.org/miso/current_release/term/SO:0002063)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=nsv1162620 "See a structural variant example")</div>

</td>

</tr>

<tr class="bg2">

<td style="padding:0px;margin:0px;;background-color:#007FFF;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">complex_structural_alteration</td>

<td>A structural sequence alteration or rearrangement encompassing one or more genome fragments, with 4 or more breakpoints.</td>

<td>[SO:0001784](http://www.sequenceontology.org/miso/current_release/term/SO:0001784)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv275549 "See a structural variant example")</div>

</td>

</tr>

<tr>

<td style="padding:0px;margin:0px;;background-color:#007FFF;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">complex_substitution</td>

<td>When no simple or well defined DNA mutation event describes the observed DNA change, the keyword \"complex\" should be used. Usually there are multiple equally plausible explanations for the change.</td>

<td>[SO:1000005](http://www.sequenceontology.org/miso/current_release/term/SO:1000005)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=nsv511117 "See a structural variant example")</div>

</td>

</tr>

<tr class="bg2">

<td style="padding:0px;margin:0px;;background-color:#0000CC;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">copy_number_gain</td>

<td>A sequence alteration whereby the copy number of a given regions is greater than the reference sequence.</td>

<td>[SO:0001742](http://www.sequenceontology.org/miso/current_release/term/SO:0001742)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv1004360 "See a structural variant example")</div>

</td>

</tr>

<tr>

<td style="padding:0px;margin:0px;;background-color:#CC0000;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">copy_number_loss</td>

<td>A sequence alteration whereby the copy number of a given region is less than the reference sequence.</td>

<td>[SO:0001743](http://www.sequenceontology.org/miso/current_release/term/SO:0001743)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv991724 "See a structural variant example")</div>

</td>

</tr>

<tr class="bg2">

<td style="padding:0px;margin:0px;;background-color:#8601AF;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">copy_number_variation</td>

<td>A variation that increases or decreases the copy number of a given region.</td>

<td>[SO:0001019](http://www.sequenceontology.org/miso/current_release/term/SO:0001019)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv275461 "See a structural variant example")</div>

</td>

</tr>

<tr>

<td style="padding:0px;margin:0px;;background-color:#0000CC;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">duplication</td>

<td>An insertion which derives from, or is identical in sequence to, nucleotides present at a known location in the genome.</td>

<td>[SO:1000035](http://www.sequenceontology.org/miso/current_release/term/SO:1000035)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv2830426 "See a structural variant example")</div>

</td>

</tr>

<tr class="bg2">

<td style="padding:0px;margin:0px;;background-color:#000000;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">interchromosomal_breakpoint</td>

<td>A rearrangement breakpoint between two different chromosomes.</td>

<td>[SO:0001873](http://www.sequenceontology.org/miso/current_release/term/SO:0001873)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv2713382 "See a structural variant example")</div>

</td>

</tr>

<tr>

<td style="padding:0px;margin:0px;;background-color:#C3A4FF;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">interchromosomal_translocation</td>

<td>A translocation where the regions involved are from different chromosomes.</td>

<td>[SO:0002060](http://www.sequenceontology.org/miso/current_release/term/SO:0002060)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=nsv1150170 "See a structural variant example")</div>

</td>

</tr>

<tr class="bg2">

<td style="padding:0px;margin:0px;;background-color:#000000;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">intrachromosomal_breakpoint</td>

<td>A rearrangement breakpoint within the same chromosome.</td>

<td>[SO:0001874](http://www.sequenceontology.org/miso/current_release/term/SO:0001874)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv1914887 "See a structural variant example")</div>

</td>

</tr>

<tr>

<td style="padding:0px;margin:0px;;background-color:#C3A4FF;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">intrachromosomal_translocation</td>

<td>A translocation where the regions involved are from the same chromosome.</td>

<td>[SO:0002061](http://www.sequenceontology.org/miso/current_release/term/SO:0002061)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=nsv1152656 "See a structural variant example")</div>

</td>

</tr>

<tr class="bg2">

<td style="padding:0px;margin:0px;;background-color:#C530FF;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">inversion</td>

<td>A continuous nucleotide sequence is inverted in the same position.</td>

<td>[SO:1000036](http://www.sequenceontology.org/miso/current_release/term/SO:1000036)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv996586 "See a structural variant example")</div>

</td>

</tr>

<tr>

<td style="padding:0px;margin:0px;;background-color:#8601AF;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">loss_of_heterozygosity</td>

<td>A functional variant whereby the sequence alteration causes a loss of function of one allele of a gene.</td>

<td>[SO:0001786](http://www.sequenceontology.org/miso/current_release/term/SO:0001786)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=nsv2768232 "See a structural variant example")</div>

</td>

</tr>

<tr class="bg2">

<td style="padding:0px;margin:0px;;background-color:#CC0000;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">mobile_element_deletion</td>

<td>A deletion of a mobile element when comparing a reference sequence (has mobile element) to a individual sequence (does not have mobile element).</td>

<td>[SO:0002066](http://www.sequenceontology.org/miso/current_release/term/SO:0002066)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=nsv3077686 "See a structural variant example")</div>

</td>

</tr>

<tr>

<td style="padding:0px;margin:0px;;background-color:#000080;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">mobile_element_insertion</td>

<td>A kind of insertion where the inserted sequence is a mobile element.</td>

<td>[SO:0001837](http://www.sequenceontology.org/miso/current_release/term/SO:0001837)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv3309266 "See a structural variant example")</div>

</td>

</tr>

<tr class="bg2">

<td style="padding:0px;margin:0px;;background-color:#000080;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">novel_sequence_insertion</td>

<td>An insertion the sequence of which cannot be mapped to the reference genome.</td>

<td>[SO:0001838](http://www.sequenceontology.org/miso/current_release/term/SO:0001838)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv3310477 "See a structural variant example")</div>

</td>

</tr>

<tr>

<td style="padding:0px;margin:0px;;background-color:#732E00;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">short_tandem_repeat_variation</td>

<td>A variation that expands or contracts a tandem repeat with regard to a reference.</td>

<td>[SO:0002096](http://www.sequenceontology.org/miso/current_release/term/SO:0002096)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=nsv2726918 "See a structural variant example")</div>

</td>

</tr>

<tr class="bg2">

<td style="padding:0px;margin:0px;;background-color:#732E00;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">tandem_duplication</td>

<td>A duplication consisting of 2 identical adjacent regions.</td>

<td>[SO:1000173](http://www.sequenceontology.org/miso/current_release/term/SO:1000173)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv3302857 "See a structural variant example")</div>

</td>

</tr>

<tr>

<td style="padding:0px;margin:0px;;background-color:#C3A4FF;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">translocation</td>

<td>A region of nucleotide sequence that has translocated to a new position. The observed adjacency of two previously separated regions.</td>

<td>[SO:0000199](http://www.sequenceontology.org/miso/current_release/term/SO:0000199)</td>

<td>

*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=nsv1157267 "See a structural variant example")</div>

</td>

</tr>

<tr class="bg2">

<td style="padding:0px;margin:0px;;background-color:#CC0000;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">deletion</td>

<td>The point at which one or more contiguous nucleotides were excised.</td>

<td>[SO:0000159](http://www.sequenceontology.org/miso/current_release/term/SO:0000159)</td>

<td>

*   Variant
*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/Variation/Explore?v=rs9 "See a variant example")</div>

<div style="padding-top:1px">[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv989436 "See a structural variant example")</div>

</td>

</tr>

<tr>

<td style="padding:0px;margin:0px;;background-color:gold;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">indel</td>

<td>A sequence alteration which included an insertion and a deletion, affecting 2 or more bases.</td>

<td>[SO:1000032](http://www.sequenceontology.org/miso/current_release/term/SO:1000032)</td>

<td>

*   Variant
*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/Variation/Explore?v=rs3906 "See a variant example")</div>

<div style="padding-top:1px">[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv3627597 "See a structural variant example")</div>

</td>

</tr>

<tr class="bg2">

<td style="padding:0px;margin:0px;;background-color:#000099;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">insertion</td>

<td>The sequence of one or more nucleotides added between two adjacent nucleotides in the sequence.</td>

<td>[SO:0000667](http://www.sequenceontology.org/miso/current_release/term/SO:0000667)</td>

<td>

*   Variant
*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/Variation/Explore?v=rs109 "See a variant example")</div>

<div style="padding-top:1px">[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv991325 "See a structural variant example")</div>

</td>

</tr>

<tr>

<td style="padding:0px;margin:0px;;background-color:#000000;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">sequence_alteration</td>

<td>A sequence_alteration is a sequence_feature whose extent is the deviation from another sequence.</td>

<td>[SO:0001059](http://www.sequenceontology.org/miso/current_release/term/SO:0001059)</td>

<td>

*   Variant
*   <span class="_ht ht" title="Structural variant">SV</span>

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/Variation/Explore?v=rs4340 "See a variant example")</div>

<div style="padding-top:1px">[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=esv24160 "See a structural variant example")</div>

</td>

</tr>

<tr class="bg2">

<td style="padding:0px;margin:0px;;background-color:#4682B4;border-top:1px solid #FFF"></td>

<td style="font-weight:bold">probe</td>

<td>A DNA sequence used experimentally to detect the presence or absence of a complementary nucleic acid.</td>

<td>[SO:0000051](http://www.sequenceontology.org/miso/current_release/term/SO:0000051)</td>

<td>

*   CNV probe

</td>

<td style="padding-left:0px;width:16px">

<div>[![Link](/i/16/internal_link.png)](/Homo_sapiens/StructuralVariation/Explore?sv=cnvi0111251 "See a structural variant example")</div>

</td>

</tr>

</tbody>

</table>

***** Corresponding colours for the Ensembl web displays (only for Structural variants). The colours were originally based on the [dbVar](http://www.ncbi.nlm.nih.gov/dbvar/content/overview/) displays.

<div class="js_panel" id="pie_chart_panel" style="margin-top:15px;margin-bottom:20px"><input class="panel_type" type="hidden" value="Piechart"> <input class="graph_config" type="hidden" name="legendpos" value="'east'"> <input class="graph_dimensions" type="hidden" value="[90,80,80]"> <input type="hidden" class="graph_data" value="[[309685982,'SNV'],[11908423,'deletion'],[7019011,'insertion'],[847848,'sequence_alteration'],[228404,'substitution'],[178101,'indel'],[6808,'genetic_marker'],[4623,'tandem_repeat']]">

<div class="pie_chart_classes" title="classes" style="width:400px;height:220px;border:1px solid #CCC;border-radius:8px;box-shadow:0 1px 3px #666">

### Human variant class distribution - Ensembl 92

</div>

</div>
