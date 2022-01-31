---
title: Sequence alignments
categories: Website,help
---

<a href="https://www.youtube.com/watch?v=IAYFLfPQ0Gs" class="icon icon-generic namespaceIcons">Tutorial/Video</a>

Select the *Align* tab of the toolbar to align two or more protein sequences with the [Clustal Omega program](http://www.clustal.org/) (cf also this [ClustalO FAQ](http://www.ebi.ac.uk/Tools/msa/clustalo/help/faq.html) ):

1.  Enter either protein sequences in FASTA format or UniProt identifiers into the form field.
2.  Click the *Run Align* button.

![](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/align_form.png)

The following kinds of UniProt identifiers are supported:

|                       |                                  |
|:----------------------|:---------------------------------|
| **P00750**            | UniProtKB entry                  |
| **P00750-2**          | UniProtKB entry isoform sequence |
| **A4\_HUMAN**         | UniProtKB entry name             |
| **UPI0000000001**     | UniParc entry                    |
| **UniRef100\_P00750** | UniRef entry                     |

To limit the range within a sequence, append the range in square brackets to the identifier. For example, P00750\[1-10\] represents the first ten amino acids of P00750.

Instead of entering identifiers into the form, you can collect sequences by clicking into the checkboxes next to them. Once two or more sequences have been marked, the *Run Align* button becomes available:

![](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/align_select.png)

Similarly, you can align the sequences that you have collected into your [basket](http://www.uniprot.org/help/basket) .

After you have submitted your data, a status page is shown. This page is reloaded in regular intervals until the alignment is complete. The final result page shows a colored version of the alignment and allows to download in Clustal format.

An alignment will display the following symbols denoting the degree of conservation observed in each column:

-   An \* (asterisk) indicates positions which have a single, fully conserved residue.
-   A : (colon) indicates conservation between groups of strongly similar properties - scoring &gt; 0.5 in the Gonnet PAM 250 matrix.
-   A . (period) indicates conservation between groups of weakly similar properties - scoring =&lt; 0.5 in the Gonnet PAM 250 matrix.

Jobs have unique identifiers, which (depending on the job type) can be used in queries (e.g. to get the intersection of two sequence similarity searches). Job identifiers and the related data are kept for 7 days, and are then deleted.

To add sequences to your alignment, a text box just after the alignment results allows you to do so, in FASTA format:

![](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/align_results2.png)

To rerun the alignment with fewer sequences, check the box for "Result info" under "Display", and scroll down to the bottom of the page. Use the checkboxes to select the sequences you want to realign:

![](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/align_results.png)

If you want to use another sequence alignment service, click on the *Download* instead of the *Align* button to download the sequences, or copy the sequences from the form in the result page.

'Annotation' and 'Amino acid properties' highlighting options are available on the left column. This allows to highlight key regions in the sequence alignment.

#### Related services

<table><colgroup><col style="width: 100%" /></colgroup><tbody><tr class="odd"><td><p><strong><a href="http://pir.georgetown.edu/pirwww/search/multaln.html">ClustalW</a> (PIR)</strong></p><p>Multiple sequence alignment</p></td></tr><tr class="even"><td><p><strong><a href="http://www.ebi.ac.uk/clustalw/index.html">ClustalW</a> (EBI)</strong></p><p>Multiple sequence alignment</p></td></tr><tr class="odd"><td><p><strong><a href="http://pir.georgetown.edu/pirwww/search/pairwise.html">SSEARCH</a> (PIR)</strong></p><p>Align two sequences using the Smith-Waterman algorithm</p></td></tr></tbody></table>
