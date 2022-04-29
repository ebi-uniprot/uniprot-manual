---
title: What is UniProt's human proteome?
type: help
categories: Proteomes,Download,UniProtKB,Keywords,Sequence,Human,faq
---

In 2008, a draft of the complete human proteome was released from UniProtKB/Swiss-Prot: the approximately 20,000 putative human protein-coding genes were represented by one UniProtKB/Swiss-Prot entry each, tagged with the keyword 'Complete proteome' (now obsolete) and later linked to [proteome identifier](https://www.uniprot.org/help/proteome_id) [UP000005640](https://www.uniprot.org/proteomes/UP000005640).

The **UniProtKB/Swiss-Prot _Homo sapiens_ proteome** contains one representative ( [canonical](https://www.uniprot.org/help/canonical_and_isoforms) ) protein sequence for each known protein-coding gene. Close to 40% of these 20,000 protein sequence records also contain manually annotated alternative isoforms representing over 22'000 additional sequences (see [What is the canonical sequence? Are all isoforms described in one entry?](https://www.uniprot.org/help/canonical_and_isoforms) ).

- Query: [proteome:up000005640 AND reviewed:true](https://www.uniprot.org/uniprotkb?query=reviewed%3Atrue+AND+proteome%3Aup000005640)

In 2011, a complementary pipeline for import of predicted human protein sequences in UniProtKB/TrEMBL has been developed in collaboration with [Ensembl](http://www.ensembl.org/) to complete the set of human isoform sequences produced by genes present in UniProtKB/Swiss-Prot.

This pipeline works in the following way:

1.  Ensembl sequences are first mapped to their UniProtKB counterparts under stringent conditions, requiring 100% identity over 100% of the length of the two sequences. The thus identified UniProtKB entries are flagged as part of the proteome (via a link to [UP000005640](https://www.uniprot.org/proteomes/up000005640) ) and obtain a cross-reference to the mapped Ensembl record.
2.  Ensembl sequences that are absent from UniProtKB are imported into UniProtKB/TrEMBL. These entries are flagged as part of the proteome and have an Ensembl cross-reference.

This **UniProtKB _H. sapiens_ proteome** includes thus both the reviewed sequences from UniProtKB/Swiss-Prot (equivalent to an updated version of the _H. sapiens_ proteome completed in 2008), supplemented by unreviewed sequences from UniProtKB/TrEMBL, which may represent additional predicted isoform sequences, but which may potentially also add redundancy.

Query:

- [proteome:up000005640](https://www.uniprot.org/uniprotkb?query=proteome%3Aup000005640)

Remark: The number of entries in the human proteome may vary from one release to the other, especially the manually reviewed set. This is due to our continuous manual updates thanks to the availability of new information. On a regular basis, we have to merge entries that were originally thought to be encoded by two separate genes, but later appeared to be actually a single gene. An entry can also be deleted when there is increasing evidence that it is an erroneous translation derived from a pseudogene. We keep dubious sequences in UniProtKB until there is enough evidence to decide whether we should delete them (see [Why do we keep dubious sequences in UniProtKB? How to discard them from a protein set?](https://www.uniprot.org/help/dubious_sequences) ).

# Access to human sequence sets

Our [FTP server](https://www.uniprot.org/downloads) allows to download expanded FASTA sets, containing both the canonical and manually reviewed isoform sequences, for a selection of the most widely used proteomes, including human.

Below are queries to retrieve different human sequence sets. In order to download the query results, please read [How to retrieve sets of UniProtKB protein sequences?](https://www.uniprot.org/help/retrieve_sets)

You can retrieve:

1\) <u>approximately 20,000 human protein-coding genes represented by the canonical protein sequence</u> in UniProtKB/Swiss-Prot:

- Query: [proteome:up000005640 AND reviewed:true](https://www.uniprot.org/uniprotkb?query=reviewed%3Atrue+AND+proteome%3Aup000005640)

Note: Some of the human entries in UniProtKB/Swiss-Prot are not included in the proteome because their protein sequences do not map to the reference genome:

- Query: [organism_id:9606 AND reviewed:true NOT proteome:up000005640](https://www.uniprot.org/uniprotkb?query=organism_id%3A9606+AND+reviewed%3Atrue+NOT+proteome%3Aup000005640)

2\) <u>additional manually reviewed isoform sequences</u> produced by the protein-coding genes described in UniProtKB/Swiss-Prot. There are currently around 22,000 such additional isoform sequences. These are **downloadable in FASTA format** together with the canonical sequences, if you click on "Download" and then select 'FASTA (canonical and isoform)':

- Query: [proteome:up000005640 AND reviewed:true](https://rest.uniprot.org/uniprotkb/stream?format=fasta&includeIsoform=true&query=organism_id%3A9606%20AND%20reviewed%3Atrue%20NOT%20proteome%3Aup000005640)

3\) <u>additional predicted and unreviewed sequences in UniProtKB/TrEMBL</u>, flagged to be part of the proteome, which may correspond to novel isoform sequences for genes present in UniProtKB/Swiss-Prot (derived from the Ensembl pipeline):

- Query: [proteome:up000005640 AND reviewed:false](https://www.uniprot.org/uniprotkb?query=proteome:up000005640+AND+reviewed%3Afalse)

Note: Additional human sequences in UniProtKB/TrEMBL are not flagged to be part of the proteome. The vast majority of these additional UniProtKB/TrEMBL entries contain sequences which are not identical to any isoform sequences predicted by Ensembl. They might represent other alternative isoforms. The system is not perfect, but it is the best we can provide for the time being.

- Query: [organism_id:9606 AND reviewed:false NOT proteome:up000005640](https://www.uniprot.org/uniprotkb?query=organism_id%3A9606+AND+reviewed%3Afalse+NOT+proteome:up000005640)

# See also

- [What are proteomes?](https://www.uniprot.org/help/proteome)
- [What are reference proteomes?](https://www.uniprot.org/help/reference_proteome)
- [How to retrieve sets of UniProtKB protein sequences?](https://www.uniprot.org/help/retrieve_sets)
- [Alternative products](https://www.uniprot.org/help/alternative_products)
- [Alternative sequence](https://www.uniprot.org/help/var_seq)
