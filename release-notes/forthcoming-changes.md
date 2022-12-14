---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

## Change of the UniParc files distribution

**On February 22, 2023**

The UniParc database is distributed on the [UniProt FTP site](https://ftp.uniprot.org/pub/databases/uniprot/current_release/uniparc/) in FASTA and XML format as one gzip-compressed file for each format. The size of these files has grown over the years to now more that 100 and 200 Gigabytes, respectively, which makes them difficult to download. We will therefore split these files into sets of 128 smaller files each. The partitioned files will be available in the following subdirectories:

|https://ftp.uniprot.org/pub/databases/uniprot/current_release/uniparc/xml/all | all sequences in XML format|
|https://ftp.uniprot.org/pub/databases/uniprot/current_release/uniparc/fasta/active | all active sequences in FASTA format|

For release 2023_01, we will provide each format as one file and partitioned into 128 smaller files. From release 2023_02 onwards, only the partitioned files will be provided.
