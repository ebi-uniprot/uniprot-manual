---
title: What is a redundant proteome? Can reference proteomes become redundant? Can reviewed UniProtKB (Swiss-Prot) entries be deleted when a proteome becomes redundant?
categories: Proteomes,UniProtKB,UniParc,faq
---

### What is a redundant proteome?

A redundant proteome is one in which all or nearly all protein sequences are highly similar or identical to an existing proteome from the same species.

To reduce redundancy in proteomes and subsequently UniProtKB/TrEMBL, we have developed a procedure to identify highly redundant proteomes within species groups, using a combination of manual and automatic methods.

-   Proteomes can only be redundant to other proteomes of the same taxonomy branch at species level or below (sub-species, strains, etc.).
-   We use the CD-Hit 2D program for pairwise comparison of proteomes within each taxonomic group. Based on the results, we calculate the level of similarity between pairs of proteomes within the groups.
-   Proteomes that rank lowest are the most redundant. These are marked as "redundant" on the UniProt [proteomes portal](http://www.uniprot.org/proteomes) (example: [UP000008521](http://www.uniprot.org/proteomes/UP000008521), redundant to [UP000008520](http://www.uniprot.org/proteomes/UP000008520) ), and are labelled with a specific icon. Protein entries belonging to these redundant proteomes are either removed from UniProtKB/TrEMBL, or, for new sequences, no corresponding UniProtKB/TrEMBL entries are created. The sequences from redundant proteomes are available for download from the UniProt sequence archive [UniParc](http://www.uniprot.org/uniparc) via the [proteomes portal](http://www.uniprot.org/proteomes).

See also:

-   [Reducing proteome redundancy](http://www.uniprot.org/help/proteome%5Fredundancy)
-   [Elimination of redundant proteomes (UniProt blog)](https://insideuniprot.blogspot.com/2015/05/)

### Can a reference proteome be made redundant?

No, [reference proteomes](http://www.uniprot.org/help/reference%5Fproteome) have a special status that protects them from becoming redundant. Reference proteomes are carefully chosen based on stringent criteria and represent important organisms covering the tree of life with a high level of annotation.

### Can reviewed UniProtKB (Swiss-Prot) entries be deleted when a proteome becomes redundant?

No. While it can happen that a proteome containing reviewed UniProtKB (Swiss-Prot) entries becomes redundant, its reviewed, manually curated members are not deleted as a consequence.

### Can entries that were deleted as members of redundant proteomes come back at a later stage?

Yes, this is possible: It may happen that proteomes that were identified as redundant are later reinstated as non-redundant, e.g. a proteome for a strain used as a model by a significant community or with proteins that have been crystallized. In the past, it has also happened on rare occasions that entries were deleted but later reinstated for other reasons. In such cases, the UniProtKB entries are created anew, with **new accession numbers**.

To help users to link deleted to subsequently reinstated entries, we provide a [file that maps old to new accession numbers](https://ftp.uniprot.org/pub/databases/uniprot/current%5Frelease/knowledgebase/complete/docs/reinstated%5Fmap.txt.gz) via their [protein\_ids](http://www.uniprot.org/help/sequence%5Forigin).
