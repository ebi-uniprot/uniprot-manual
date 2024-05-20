---
title: Genomic coordinates tab
type: help
categories: UniProtKB,manual
---

(note: this article is working in progress)

# Genomic coordinates tab
This tab on some UniProtKB entries displays genomic coordinates information related to the corresponding UniProtKB entry.

## Origin of the data
UniProtKB entries are mainly imported from four resources: INSDC, ENSEMBL/Ensembl Genome, Reference and Wormbase parasite. Genomic coordinates of UniProtKB proteins are imported from the corresponding nucleotide sequence. For Ensembl, Ensembl genome, Wormbase parasite, We import the genomic coordinates of protein  from Ensembl, Ensembl genome, and Wormbase parasite database. All the nucleotide sequences of all these Ensembl, Ensembl genome and wormbase parasites are deposited into INSDC. For UniProtKB entries imported from INSDC CDS, the genomic coordinates of these proteins are from INSDC nucleotide sequences. 

For the UniProtKB entries imported from RefSeq, the genomic coordinates are imported from RefSeq nucleotide sequences.

All UniProtKB proteins imported from Ensembl, Ensembl Genome and Wormbase parasites have genomic coordinates. All UniProtKB proteins imported from RefSeq have genomic coordinates. For UniProtKB proteins imported from INSDC, we started to provide the genomic coordinates for reference proteomes.

This data is available from the genomic coordinates endpoint of the Proteins REST API which is one of the [programmatic interfaces offered by UniProt](https://www.uniprot.org/help/programmatic_access).

## Sections of the tab
This tab presents the data described above grouped by gene and showing some basic information for each gene like the chromosome and strand.

For each gene, the isoforms covering it are listed with their corresponding genomic location and number of exons, and a table shows for each coordinates corresponding to the different exons which isoforms include it and at which protein coordinate.