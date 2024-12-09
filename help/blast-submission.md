---
title: BLAST Submissions
type: help
categories: Website, Help
---

## Overview

**BLAST (Basic Local Alignment Search Tool)** is a widely used algorithm in bioinformatics that identifies regions of similarity between biological sequences (like DNA, RNA, or proteins). BLAST compares a query sequence to a database of sequences and finds matching segments, which can help researchers inferhomologous genes, determine protein functions, or classify organisms based on genetic material.

BLAST uses a heuristic approach, which makes it faster than traditional alignment methods by finding high-scoring “seed” matches, then expanding and refining them.

BLAST then assigns a score to each match and calculates an E-value to indicate the likelihood of finding that match by chance. A lower E-value suggests a more significant match.

BLAST tool search results are saved in your tools dashboard for a maximum of 7 days. After 7 days the job can be resubmitted from the tools dashboard with the same parameters.

## Where to Find the BLAST Tool

You can access the BLAST tool directly from various sections of the UniProt website:

- **Main toolbar**: Easily accessible in the top left of the navigation.
- **Basket**: Align multiple sequences stored in your basket.
- **UniProtKB, UniRef and UniParc results pages**: directly from search results by selecting the results of interest and then selecting BLAST in the ‘tools’ dropdown menu.
- **UniProtKB entry page**: in the sequences section you can BLAST isoforms of a specific protein entry.

## Job Submission Form

### Input Sequences

You can submit sequences in multiple ways:

- **Prepopulated** e.g. from selections made in your search results or your basket.
- **UniProt identifiers** entered manually.
- **FASTA text input**: Paste your sequence(s) in FASTA format.
- **FASTA file upload**: Upload a text file containing the sequences to align.

Supported UniProt identifiers include:

| **Identifier**         | **Description**                       |
|------------------------|---------------------------------------|
| **P00750**             | UniProtKB entry                       |
| **P00750-2**           | UniProtKB entry isoform sequence      |
| **A4_HUMAN**           | UniProtKB entry name                  |
| **UPI0000000001**      | UniParc entry                         |
| **UniRef100_P00750**   | UniRef entry                          |

You may submit up to a maximum of 5 sequences at a time.  

You can also submit **subsequences** when using the FASTA format.  
> >sp|P01308|25-54
> FVNQHLCGSHLVEALYLVCGERGFFYTPKT

### Choosing the Right Target Database

Choose the correct target database for your use case, this will determine the search space for your BLAST search and significantly affect the results that are returned to you.

Target Database Descriptions

| **Option**             | **Description**                       |
|------------------------|---------------------------------------|
| **UniProtKB reference proteomes + Swiss-Prot** | This option is the default selection for BLAST searches.  [Swiss-Prot](https://www.uniprot.org/help/uniprotkb) includes manually reviewed protein sequences with high-quality annotations. Swiss-Prot gives the most reliable and well-annotated entries, this is useful if you’re looking for functional information, conserved domains, or known characterized protein families.  

[Reference proteomes](https://www.uniprot.org/help/reference_proteome) are high-quality, representative sets of protein sequences selected to represent the proteomes of species across the tree of life. These reference proteomes are designed to serve as benchmarks for comparative genomics, evolutionary studies, and functional annotation. <br>

Swiss-Prot data undergoes expert manual curation, so it contains high-quality data  but is smaller in scope compared to unreviewed data. Reference proteomes are included in the search to provide wider coverage to supplement Swiss-Prot entries. |
| **UniProtKB (TrEMBL)**           | TrEMBL contains computationally analyzed protein sequences that have not been manually reviewed. It is much larger than Swiss-Prot and encompasses more species, however these protein entries are not manually annotated.      |
| **UniProtKB with 3D structure (PDB)**           | This option includes PDB 3D structures and UniProtKB (TrEMBL)                  |
| **UniProtKB with 3D structure predictions (AlphaFold)**      | This option includes AlphaFold 3D structure predictions and UniProtKB (TrEMBL)                         |
| **UniProtKB reference proteomes**   | [Reference proteomes](https://www.uniprot.org/help/reference_proteome) are high-quality, representative sets of protein sequences selected to represent the proteomes of species across the tree of life. These reference proteomes are designed to serve as benchmarks for comparative genomics, evolutionary studies, and functional annotation.                          |
| **UniProtKB Swiss-Prot**  |   [Swiss-Prot](https://www.uniprot.org/help/uniprotkb) includes manually reviewed protein sequences with high-quality annotations. Swiss-Prot gives the most reliable and well-annotated entries, this is useful if you’re looking for functional information, conserved domains, or known characterized protein families.    |
| **UniRef100**  | UniRef100 contains all UniProt Knowledgebase records plus selected UniParc records. In UniRef100, all identical sequences and subfragments with 11 or more residues are placed into a single record.  |
| **UniRef90**  | UniRef90 is generated by clustered UniRef100 sequences with 11 or more residues, such that each cluster is composed of sequences that have at least 90% sequence identity to and 90% overlap with the [seed sequence](https://www.uniprot.org/help/uniref_seed).  |
| **UniRef50**  | UniRef50 is built by clustering UniRef90 seed sequences that have at least 50% sequence identity to and 80% overlap with the longest sequence in the cluster.  |
| **UniParc**  | [UniParc (UniProt Archive)](https://www.uniprot.org/help/uniparc) is a comprehensive non-redundant protein sequence archive that includes sequences from multiple sources, like GenBank, PDB, and EMBL, updated frequently to capture all known protein sequences.  |

### Restrict by Taxonomy

Whenever possible limit your search to specific taxonomic groups by using this option, specifying taxonomy will reduce BLAST search time and focus your results on a taxonomy or taxonomic group of interest.

It is possible to focus on matches within a specific clade or species, and is useful for narrowing results to homologs from certain lineages, e.g., mammals, bacteria, or plants.
Use the text input box to search and select taxonomic groups.

### Job Name

By default, the job name is auto-generated based on the submitted sequences. Customising the name will allow you to find your BLAST results quickly in your tools dashboard.

### Advanced Parameters

| **Option**             | **Description**                       |
|------------------------|---------------------------------------|
| **Sequence type**      | |
| **Program**  |   |
| **E-Threshold**  |   |
| **Matrix**  |   |
| **Filter**  |   |
| **Gapped**  |   |
| **Hits**  |   |
| **HSPs per hit**  |   |
