---
title: Why have some UniProtKB accession numbers been deleted? How can I track them?
type: help
categories: UniProtKB,Entry_information,UniParc,Release,faq
---

An accession number (AC) is assigned to each protein sequence upon inclusion into UniProtKB. Accession numbers are stable from release to release ([What is the difference between an accession number (AC) and the entry name?](https://www.uniprot.org/help/difference_accession_entryname)). It can however happen that a protein sequence (and its corresponding accession number) is deleted from UniProtKB.

The full list of reasons for deleted accessions can be found here:

| Deletion reason                       |
| ------------------------------------- |
| Deleted from sequence source (EMBL)   |
| Deleted from sequence source (ENSEMBL)|
| Deleted from sequence source (PDB)    |
| Deleted from sequence source (RefSeq) |
| Deleted from Swiss-Prot               |
| Redundant proteome                    |
| Excluded proteome                     |
| Redundant sequence                    |
| Over-represented sequence             |

Most **UniProtKB/TrEMBL** deletions are due to the deletion of the corresponding coding sequence (CDS) in the source nucleotide sequence databases EMBL-Bank/DDBJ/GenBank as requested by the original submitters, or due to the deletion of the sequence prediction from Ensembl or RefSeq. It occasionally happens that the same data is resubmitted at a later date, and UniProt works closely with EMBL-Bank/DDBJ/GenBank and Ensembl to ensure appropriate tracking of deletions and updates. However this is not always possible. In addition, some protein sequences are recognized by curators to be Open Reading frames (ORFs) that have been wrongly predicted to code for proteins or to be pseudogenes. When there is enough evidence that these hypothetical proteins are not real, we take the decision to remove them from UniProtKB/TrEMBL.

Deleted entries in **UniProtKB/Swiss-Prot** are mostly Open Reading Frames (ORFs) or pseudogenes that have been wrongly predicted to code for proteins.

Another frequent deletion reason in UniProtKB/TrEMBL is [proteome redundancy reduction](https://www.uniprot.org/help/proteome_redundancy) and [proteome exclusion](https://www.uniprot.org/help/proteome_exclusion_reasons).

Redundant sequences and over-represented sequences mean that we have too many accessions, or instances, of a protein. One example would be COVID-2 proteins. In the case of COVID-2, we have initially created UniProtKB entries for any COVID-2 sequence. This has caused an over-representation, and thus most of the redundant proteins have been deleted.

All deleted protein sequences can be found in UniParc. Example: [O00597](https://www.uniprot.org/uniprotkb/O00597) can be found in [UniParc](https://www.uniprot.org/uniparc/UPI000013C29B) (with the tag 'Active=No').

The history of a deleted entry can be tracked (example: [O00597](https://www.uniprot.org/uniprotkb/O00597?version=%2A)), and previous entry and sequence versions displayed.

Two documents list the deleted accession numbers:

- [delac_sp.txt](https://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/docs/delac_sp.txt) for deleted ACs in UniProtKB/Swiss-Prot
- [delac_tr.txt.gz](https://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/docs/delac_tr.txt.gz) for deleted ACs in UniProtKB/TrEMBL

# See also

- [What are UniProtKB's criteria for defining a CDS as a protein?](https://www.uniprot.org/help/cds_protein_definition)
- [Does UniProtKB contain all protein sequences?](https://www.uniprot.org/help/uniprotkb_coverage)
- [Why do we keep dubious sequences in UniProtKB? How to discard them from a protein set?](https://www.uniprot.org/help/dubious_sequences)
- [How frequently is UniProt released? What is the synchronization delay with other databases?](https://www.uniprot.org/help/synchronization)
- [Accession number](https://www.uniprot.org/help/accession_numbers)
