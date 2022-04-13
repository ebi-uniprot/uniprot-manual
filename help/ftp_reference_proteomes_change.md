
---
title: Changes to the FTP repository for reference proteomes
type: help
categories: changes
---

We currently distribute the UniProt reference proteomes on our [FTP site](ftp://ftp.uniprot.org/pub/databases/uniprot/current%5Frelease/knowledgebase/reference%5Fproteomes/) in four taxonomic division folders (Archaea, Bacteria, Eukaryota and Viruses) and provide for each proteome its sequences in FASTA format and mappings from UniProt identifiers and gene names to those found in other databases. Starting from the next release, we will also publish the full protein records for a proteome in the UniProtKB text and XML format, and we will at the same time introduce a subfolder for each proteome that groups all its files in order to reduce the number of files in the taxonomic division folders.

Example: [UP000005640](https://www.uniprot.org/proteomes/UP000005640)

Current FTP folder and files:

ftp://ftp.uniprot.org/pub/databases/uniprot/current\_release/knowledgebase/reference\_proteomes/**Eukaryota/**

*   UP000005640\_9606.fasta.gz
*   UP000005640\_9606\_additional.fasta.gz
*   UP000005640\_9606\_DNA.fasta.gz
*   UP000005640\_9606\_DNA.miss.gz
*   UP000005640\_9606.idmapping.gz
*   UP000005640\_9606.gene2acc.gz

New FTP folder and files:

ftp://ftp.uniprot.org/pub/databases/uniprot/current\_release/knowledgebase/reference\_proteomes/**Eukaryota/UP000005640/**

*   **UP000005640\_9606.dat.gz** — _UniProtKB text format_
*   **UP000005640\_9606.xml.gz** — _UniProtKB XML format_
*   UP000005640\_9606.fasta.gz
*   UP000005640\_9606\_additional.fasta.gz
*   UP000005640\_9606\_DNA.fasta.gz
*   UP000005640\_9606\_DNA.miss.gz
*   UP000005640\_9606.idmapping.gz
*   UP000005640\_9606.gene2acc.gz
        