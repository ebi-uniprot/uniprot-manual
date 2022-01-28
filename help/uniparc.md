
---
title: UniParc
categories: About_UniProt,UniParc,Sequence,Cross-references,help
---

The UniProt Archive (UniParc) is a comprehensive and non-redundant database that contains most of the publicly available protein sequences in the world. Proteins may exist in different source databases and in multiple copies in the same database. UniParc avoided such redundancy by storing each unique sequence only once and giving it a stable and unique identifier (UPI) making it possible to identify the same protein from different source databases. A UPI is never removed, changed or reassigned. UniParc contains only protein sequences. All other information about the protein must be retrieved from the source databases using the database cross-references. UniParc tracks sequence changes in the source databases and archives the history of all changes. UniParc has combined many databases into one at the sequence level and searching UniParc is equivalent to searching many databases simultaneously.

#### Content of an entry

The basic information stored within each UniParc entry is the identifier, the sequence, cyclic redundancy check number, source database(s) with accession and version numbers, and a time stamp. If a UniParc entry does not have a cross-reference to a UniProtKB entry, the reason for the exclusion of that sequence from UniProtKB is provided (eg. pseudogene). In addition, each source database accession number is tagged with its status in that database, indicating if the sequence still exists or has been deleted in the source database and cross-references to NCBI GI and taxonomic identifier (TaxID) if appropriate.

#### Sequence comparison

Sequences are compared when entering UniParc with all existing sequences. The CRC64 check sum is first calculated and then compared for each sequence. If two sequences have the same CRC64 value, the sequences themselves will then be compared as strings before considering them as identical.

#### Sequence versions

Sequence changes in the source database can be tracked by sequence versions. Some source database provide their own versions while others don't. UniParc does its own internal versioning. Each time a sequence is changed the internal version is incremented by one, making it possible to track sequence changes in all source databases. Sequence versions are kept as part of cross-reference and the history of all changes are kept.

#### Database cross-references

A database cross-reference links a protein sequence to its origin database. It contains a source database identifier, a sequence identifier from the source database, a sequence version from source database if any, a UniParc sequence version and whether or not the cross-reference is still active. A new cross-reference is created when a new or updated protein enters UniParc. When a sequence is changed or deleted from a source database, its corresponding cross-reference is marked as deleted. Active cross-reference can be used to directly access the source databases but inactive cross-references can only be used to access sequences archives, such as the [EMBL nucleotide sequence database sequence version archive](http://www.ebi.ac.uk/cgi-bin/sva/sva.pl), the EMBL nucleotide sequence database stores of its entries in a searchable manner.

#### Data sources

Currently UniParc contains protein sequences from the following publicly available databases:

*   [EMBL-Bank](http://www.ebi.ac.uk/embl/)/[DDBJ](http://www.ddbj.nig.ac.jp/)/[GenBank](http://www.ncbi.nlm.nih.gov/Genbank/) nucleotide sequence databases
*   [Ensembl](http://www.ensembl.org/)
*   [EnsemblGenomes](http://www.ensemblgenomes.org/)
*   [European Patent Office (EPO)](http://www.european-patent-office.org/)
*   [FlyBase](http://flybase.bio.indiana.edu/)
*   [H-Invitational Database (H-InvDB)](http://www.h-invitational.jp/)
*   [International Protein Index (IPI)](http://www.ebi.ac.uk/IPI/)
*   [Japan Patent Office (JPO)](http://www.jpo.go.jp/)
*   [Korean Intellectual Property Office (KIPO)](http://www.kipo.go.kr/)
*   [Pathosystems Resource Integration Center (PATRIC)](http://patricbrc.org/)
*   [Protein Data Bank (PDB)](http://www.pdb.org/)
*   [Protein Research Foundation (PRF)](http://www.prf.or.jp/index-e.html)
*   [RefSeq](http://www.ncbi.nlm.nih.gov/RefSeq/)
*   [Saccharomyces Genome database (SGD)](http://www.yeastgenome.org/)
*   [TAIR Arabidopsis thaliana Information Resource](http://www.arabidopsis.org/)
*   [The Seed (SEED)](http://theseed.org/)
*   [TROME](ftp://ftp.isrec.isb-sib.ch/pub/databases/trome)
*   [USA Patent Office (USPTO)](http://www.uspto.gov/)
*   [UniProtKB/Swiss-Prot, UniProtKB/Swiss-Prot protein isoforms, UniProtKB/TrEMBL](http://www.uniprot.org/uniprot)
*   [Vertebrate Genome Annotation database (VEGA)](http://vega.sanger.ac.uk/)
*   [WormBase](http://www.wormbase.org/)
*   [WormBase ParaSite (WBParaSite)](http://parasite.wormbase.org/)

UniParc also contains and will continue to keep cross-references to the following discontinued databases:

*   IPI
*   PIR
*   PIRARC
*   REMTREMBL
*   UniMES
*   TREMBLNEW
*   TrEMBL\_varsplic
        