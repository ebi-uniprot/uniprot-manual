---
title: Genomic coordinates tab
type: help
categories: UniProtKB,manual
---

This tab on some UniProtKB entries displays genomic coordinates information related to the corresponding UniProtKB entry.

## Data sources

UniProtKB entries are mainly imported from four sources: INSDC, Ensembl/Ensembl Genome, Reference, and WormBase ParaSite. Genomic coordinates of UniProtKB proteins are imported from the corresponding nucleotide sequences. For Ensembl/Ensembl Genome and WormBase ParaSite databases, we import the genomic coordinates of proteins directly from the respective database. All of the nucleotide sequences from Ensembl/Ensembl Genome and WormBase ParaSite are deposited into INSDC. For UniProtKB entries imported from INSDC CDS, the genomic coordinates of these proteins are from INSDC nucleotide sequences.

For the UniProtKB entries imported from RefSeq, the genomic coordinates are imported from RefSeq nucleotide sequences.

All UniProtKB proteins imported from Ensembl/Ensembl Genome and WormBase ParaSite have genomic coordinates. All UniProtKB proteins imported from RefSeq have genomic coordinates. For UniProtKB proteins imported from INSDC, we have now started to provide the genomic coordinates for reference proteomes.

This data is available from the genomic coordinates endpoint of the Proteins REST API, which is one of the [programmatic interfaces offered by UniProt](https://www.uniprot.org/help/programmatic_access).

## Tab sections

The Genomic coordinates tab presents the data described above, grouped by gene, and displays basic information for each gene, such as the chromosome and strand.

For each gene, the isoforms covering it are listed with their corresponding genomic location and number of exons. A table shows shows the coordinates corresponding to the different exons, which isoforms include it, and at which protein coordinate.
