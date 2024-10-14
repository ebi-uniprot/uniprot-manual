---
title: Sequence alignments
type: help
categories: Website,help
---

---
title: Sequence alignments
type: help
categories: Website,help
---

The Align tool is used to align two or more protein or nucleotide sequences with the [Clustal Omega program](http://www.clustal.org/omega/) using the EBI's [Multiple Sequence Alignment Job Dispatcher](https://www.ebi.ac.uk/jdispatcher/msa/clustalo) ([FAQs](https://www.ebi.ac.uk/jdispatcher/docs/faqs/bioinformatics/))

The Align tool is available from within the website at the following locations:

- Main toolbar
- [Basket](https://www.uniprot.org/help/basket)
- UniProtKB and UniParc results pages
- UniProtKB entry page to align isoforms

# Align job submission form

## Sequences

Sequences can be:

- Prepopulated eg from basket
- UniProt identifiers
- FASTA text input
- FASTA file upload

The following kinds of UniProt identifiers are supported:

|                      |                                  |
| :------------------- | :------------------------------- |
| **P00750**           | UniProtKB entry                  |
| **P00750-2**         | UniProtKB entry isoform sequence |
| **A4_HUMAN**         | UniProtKB entry name             |
| **UPI0000000001**    | UniParc entry                    |
| **UniRef100_P00750** | UniRef entry                     |

To limit the range within a sequence, append the range in square brackets to the identifier. For example, P00750\[1-10\] represents the first ten amino acids of P00750.

## Number of sequneces per job

|         | Number of sequences |
| :------ | :------------------ |
| Minimum | 2                   |
| Maximum | 50                  |

## Job name

The job name will be pre-populated based on the provided sequences but if desired it can be set to a specific value of your choosing.

## Advanced parameters

|                       |                                                                           |
| :-------------------- | :------------------------------------------------------------------------ |
| Output sequence order | Determines the order in which the sequences appear in the final alignment |
| Iterations            | Number of (combined guide-tree/HMM) iterations.                           |

# Align results

Upon submission the job will appear in the [tool results](https://www.uniprot.org/tool-dashboard). Once complete the final result page has multiple tabs described below.

## Overview

This view shows a colored version of the alignment and allows to download in Clustal format. An alignment will display the following symbols denoting the degree of conservation observed in each column:

- An \* (asterisk) indicates positions which have a single, fully conserved residue.
- A : (colon) indicates conservation between groups of strongly similar properties - scoring &gt; 0.5 in the Gonnet PAM 250 matrix.
- A. (period) indicates conservation between groups of weakly similar properties - scoring =&lt; 0.5 in the Gonnet PAM 250 matrix.

'Amino acid properties' and 'Annotation' highlighting options are available on the left column. This allows to highlight key regions in the sequence alignment.

## Trees

This view visualizes the evolutionary relationships between the sequences in the alignment. It displays a phylogenetic tree, which helps to understand how closely related different sequences are, based on the alignment results.

Key Features:

1. Branches: The lines that connect the nodes, representing the evolutionary distance between sequences.
2. Nodes: The points where branches meet. They represent the common ancestors of sequences.
3. Leaf Nodes: The outermost nodes, each representing one of the aligned sequences.
4. Distances: The lengths of the branches reflect how similar or divergent the sequences are. Shorter branches indicate closer relationships, while longer branches suggest more distant relationships.

### Tree type

- Phylogenetic Tree: Shows evolutionary relationships between sequences, illustrating how sequences have diverged from a common ancestor.
- Guide Tree: Used to display the order of sequence alignments during progressive multiple sequence alignment, rather than showing evolutionary distances.

### Layout

- Horizontal: the tree is displayed with branches extending horizontally from left to right. This is the default layout used in many evolutionary studies as it allows for a more straightforward interpretation of sequence relationships.
- Circular: the tree is displayed as a circle with branches radiating out from a central point. This layout can make it easier to visualize relationships between many sequences.

### Branch length

| **Branch Length Option**          | **Definition**                                                                      | **Use Case**                                                                         |
| --------------------------------- | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| **Phylogram with Aligned Labels** | Branch lengths represent evolutionary distance, with labels aligned for comparison. | Best for comparing evolutionary relationships and branch lengths clearly.            |
| **Phylogram**                     | Branch lengths are proportional to evolutionary distances between sequences.        | Ideal for analyzing evolutionary distance in detail.                                 |
| **Cladogram**                     | Only shows relationships without considering branch lengths.                        | Suitable for focusing on the order of divergence rather than evolutionary distances. |

## Percent Identify Matrix

The Percent Identity Matrix provides a quantitative measure of how similar two or more sequences are in a multiple sequence alignment. Specifically, it calculates the percentage of identical amino acids or nucleotides at corresponding positions between each pair of sequences in the alignment.

For example:

- If two sequences have 80% identity, it means that 80% of their positions contain the same amino acid or nucleotide.
- The matrix itself is a table where the rows and columns represent the aligned sequences, and the cells contain the percent identity values between the corresponding sequences.

This matrix is useful for understanding how closely related the aligned sequences are, which can give insights into evolutionary relationships or functional similarities between proteins.

## Text Output

The raw text output of the CLUSTAL Omega multiple sequence alignment program.

## Input Parameters

The input parameters for the submitted job.

## API Request

The API request inlcuding all of the input parameters that was sent to the Job Dispatcher API.

# Related services

<table><colgroup><col style="width: 100%" /></colgroup><tbody><tr class="odd"><td><p><strong><a href="http://pir.georgetown.edu/pirwww/search/multaln.html">ClustalW</a> (PIR)</strong></p><p>Multiple sequence alignment</p></td></tr><tr class="even"><td><p><strong><a href="https://www.ebi.ac.uk/clustalw/index.html">ClustalW</a> (EBI)</strong></p><p>Multiple sequence alignment</p></td></tr><tr class="odd"><td><p><strong><a href="http://pir.georgetown.edu/pirwww/search/pairwise.html">SSEARCH</a> (PIR)</strong></p><p>Align two sequences using the Smith-Waterman algorithm</p></td></tr></tbody></table>
