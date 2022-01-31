---
title: Does UniProtKB contain all protein sequences?
categories: UniProtKB,UniParc,Sequence,faq
---

The two sections of UniProtKB - UniProtKB/Swiss-Prot and UniProtKB/TrEMBL - give access to [most protein sequences which are available to the public](http://www.uniprot.org/help/sequence%5Forigin). However, UniProtKB excludes the following protein sequences:

1.  Most non-germline [immunoglobulins](http://www.uniprot.org/help/immunoglobulins) and T-cell receptors
2.  Synthetic sequences
3.  Most patent application sequences
4.  Small fragments encoded from nucleotide sequence (&lt;8 amino acids)
5.  Pseudogenes
6.  Sequences from [redundant proteomes](http://www.uniprot.org/help/proteome%5Fredundancy)
7.  Sequences from proteomes that NCBI genomes/RefSeq considers to be [low quality assemblies](https://www.ncbi.nlm.nih.gov/assembly/help/anomnotrefseq/), i.e. [excluded proteomes](http://www.uniprot.org/help/proteome%5Fexclusion%5Freasons)
8.  Fusion/truncated proteins
9.  Not real proteins

The first 5 are identified automatically by the UniProtKB/TrEMBL creation program and never enter UniProtKB. However some proteins belonging to these classes are also identified during the UniProtKB/Swiss-Prot annotation process by the curators and then removed from UniProtKB.

Protein sequences originating from proteomes that are considered [redundant](http://www.uniprot.org/help/proteome%5Fredundancy) or [low quality](https://www.ncbi.nlm.nih.gov/assembly/help/anomnotrefseq/) are identified automatically at every release, and are either removed from UniProtKB/TrEMBL, or never enter UniProtKB but stay in [UniParc](http://www.uniprot.org/help/uniparc) .

Fusion/truncated proteins and those classified as not real proteins are only manually identified by the curators and removed from UniProtKB/TrEMBL or UniProtKB/Swiss-Prot. All these excluded sequences are available at [UniParc](http://www.uniprot.org/help/uniparc). The corresponding UniParc entries have been flagged with the reason for the absence of that sequence from UniProtKB.

See also:

-   [Where do the UniProtKB protein sequences come from?](http://www.uniprot.org/help/sequence%5Forigin)
-   [What are UniProtKB's criteria for defining a CDS as a protein?](http://www.uniprot.org/help/cds%5Fprotein%5Fdefinition)
-   [Why have some UniProtKB accession numbers been deleted? How can I track them?](http://www.uniprot.org/help/deleted%5Faccessions)
-   [Why do we keep dubious sequences in UniProtKB? How to discard them from a protein set?](http://www.uniprot.org/help/dubious%5Fsequences)
-   [Sequences](https://www.uniprot.org/help/sequences)
