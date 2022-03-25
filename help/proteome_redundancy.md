---
title: Reducing proteome redundancy
categories: Proteomes,UniProtKB,UniParc,help
---

The UniProt Knowledgebase (UniProtKB) has witnessed exponential growth in the last few years with a two-fold increase in the number of entries in 2014. This follows the vastly increased submission of multiple genomes for the same or closely related organisms. This increase was accompanied by a high level of redundancy in unreviewed UniProtKB (TrEMBL), and many sequences were over-represented in the database. This was especially true for bacterial species where different strains of the same species have been sequenced and submitted (e.g. 1,692 strains of Mycobacterium tuberculosis, corresponding to 5.97 million entries). High redundancy led to an increase in the size of UniProtKB, and thus to the amount of data to be processed internally and by our users, but also to repetitive results in BLAST searches for over-represented sequences.

To reduce this redundancy, we have developed a procedure to identify highly redundant [proteomes](https://www.uniprot.org/help/proteome) within species groups using a combination of manual and automatic methods. We applied this procedure to bacterial proteomes (which constituted 82% of UniProtKB/TrEMBL as of release 2015\_02) beginning in the 2015\_04 release. Sequences corresponding to redundant proteomes (46.9 million entries) were removed from UniProtKB. From release 2015\_04 on, we no longer create new UniProtKB/TrEMBL records for proteomes identified as redundant. The redundant sequences removed from UniProtKB (in 2015\_04) or never added to UniProtKB (from 2015\_05) are still available in the [UniParc](https://www.uniprot.org/help/uniparc) sequence archive dataset.

All proteomes remain searchable through the [Proteomes](https://www.uniprot.org/proteomes) pages. Sequences corresponding to redundant proteomes are available for download from [UniParc](https://www.uniprot.org/help/uniparc) and queries are directed to alternate non-redundant proteome(s) available for the same species. The history (i.e. previous versions) of redundant UniProtKB records remains available.

### How does this procedure work?

In order to solve the issue of rising redundancy, UniProt designed a Proteome Redundancy Detector. This algorithm detects redundant proteomes, which are then either **skipped** or **deleted** from UniProtKB/TrEMBL. The algorithm first creates clusters of proteomes at the species level, based on taxonomy. Then within each cluster of proteomes, it computes proteome similarity using pairwise alignment, calculates redundancy and plots these values onto a directed weighted graph. So a cluster is now a graph where nodes are proteomes and edges are the redundancy values. By using graph reduction methods, the graph is reduced until it only consists of non-redundant proteome nodes.

See also: [Elimination of redundant proteomes (UniProt blog)](https://insideuniprot.blogspot.com/2015/05/)

### What is the impact on UniProtKB?

Since UniProt [release 2015\_04](https://www.uniprot.org/news/2015/04/01/release), we have been using the Proteome Redundancy Detector to discard entries belonging to redundant proteomes of bacterial, and later also archaeal and fungal species in the unreviewed UniProtKB (TrEMBL) set. Redundant proteomes are flagged as redundant in the UniProt [Proteomes](https://www.uniprot.org/proteomes) portal (example: [UP000008521](https://www.uniprot.org/proteomes/UP000008521) is redundant to [UP000008520](https://www.uniprot.org/proteomes/UP000008520) ) and are labelled with a specific icon

.

The Proteomes advanced search allows searching within redundant proteomes by selecting the option "Redundant" from the dropdown and setting it to "Yes". Proteins of redundant proteomes are available in UniParc only (and not in UniProtKB). Redundant proteome pages link to UniParc for the entire proteome and each proteome component (chromosomes, plasmids, etc.). They also allow directly downloading of the proteome sequences (coming from UniParc) through the "Download" button. Obsolete UniProtKB accessions from redundant proteomes remain as cross-references in UniParc.

See also:

-   [What is a redundant proteome? Can reference proteomes become redundant? Can reviewed entries be deleted because of the proteome redundancy reduction?](https://www.uniprot.org/help/proteome%5Fredundancy%5Ffaq)
