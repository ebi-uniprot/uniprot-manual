---
title: Why have some UniProtKB accession numbers been deleted?
type: help
categories: UniProtKB,Entry_information,UniParc,Release,faq
---

An accession number (AC) is assigned to each protein sequence upon inclusion into UniProtKB. Accession numbers are stable from release to release ([What is the difference between an accession number (AC) and the entry name?](https://www.uniprot.org/help/difference_accession_entryname)). It can however happen that a protein sequence (and its corresponding accession number) is deleted from UniProtKB.

Deleted entries in **UniProtKB/Swiss-Prot** are mostly Open Reading Frames (ORFs) or pseudogenes that have been wrongly predicted to code for proteins.

Most **UniProtKB/TrEMBL** deletions are due to the deletion of the corresponding coding sequence (CDS) in the source nucleotide sequence databases EMBL-Bank/DDBJ/GenBank as requested by the original submitters, or due to the deletion of the sequence prediction from Ensembl or RefSeq. It occasionally happens that the same data is resubmitted at a later date, and UniProt works closely with EMBL-Bank/DDBJ/GenBank and Ensembl to ensure appropriate tracking of deletions and updates. However this is not always possible. In addition, some protein sequences are recognized by curators to be Open Reading frames (ORFs) that have been wrongly predicted to code for proteins or to be pseudogenes. When there is enough evidence that these hypothetical proteins are not real, we take the decision to remove them from UniProtKB/TrEMBL.

For UniProtKB/TrEMBL entries from [proteomes](https://www.uniprot.org), there are two additional common deletion reasons: [proteome redundancy reduction](https://www.uniprot.org/help/proteome_redundancy) and [proteome exclusion](https://www.uniprot.org/help/proteome_exclusion_reasons).

Redundant sequences and over-represented sequences mean that we have too many instances of a protein in UniProtKB. One example would be SARS-CoV-2, where we initially, after the outbreak of the pandemic, created UniProtKB entries for all submitted SARS-CoV-2 sequences. This has caused an over-representation, and thus most of the redundant proteins have later been deleted.

# How can I track UniProtKB accessions that have been deleted?

Like all UniProtKB sequences, all protein sequences deleted from UniProtKB can be found in [UniParc](https://www.uniprot.org/help/uniparc). Example: [O00597](https://www.uniprot.org/uniprotkb/O00597) can be found in UniParc, under [UPI000013C29B](https://www.uniprot.org/uniparc/UPI000013C29B) (with the tag 'Active=No').

The history of a deleted entry can be tracked (example: [O00597](https://www.uniprot.org/uniprotkb/O00597?version=%2A)), and previous entry and sequence versions displayed.

Two documents list the deleted accession numbers:

- [delac_sp.txt](https://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/docs/delac_sp.txt) for deleted ACs in UniProtKB/Swiss-Prot
- [delac_tr.txt.gz](https://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/docs/delac_tr.txt.gz) for deleted ACs in UniProtKB/TrEMBL

# Deletion reasons

The full list of reasons for UniProtKB/TrEMBL entry deletion can be found here:

| Deletion reason                                                                     |
| ----------------------------------------------------------------------------------- |
| [Deleted from sequence source (EMBL)](deleted_accessions#deleted_source_embl)       |
| [Deleted from sequence source (TAIR)](deleted_accessions#deleted_source_tair)       |
| [Deleted from sequence source (SGD)](deleted_accessions#deleted_source_sgd)         |
| [Deleted from sequence source (ENSEMBL)](deleted_accessions#deleted_source_ensembl) |
| [Deleted from sequence source (PDB)](deleted_accessions#deleted_source_pdb)         |
| [Deleted from sequence source (RefSeq)](deleted_accessions#deleted_source_refseq)   |
| [Deleted from Swiss-Prot](deleted_accessions#deleted_swiss-prot)                    |
| [Redundant sequence](deleted_accessions#redundant_sequence)                         |
| [Redundant proteome](deleted_accessions#redundant_proteome)                         |
| [Excluded proteome](deleted_accessions#excluded_proteome)                           |
| [Over-represented sequence](deleted_accessions#over-represented_sequence)           |
| [Not part of a reference proteome](deleted_accessions#not-part-of-a-reference-proteome)           |

<h2 id="deleted_source_embl">Deleted from sequence source (EMBL)</h2>

The sequence has been deleted from its source, in this case EMBL.

<h2 id="deleted_source_tair">Deleted from sequence source (TAIR)</h2>

The sequence has been deleted from its source, in this case TAIR.

<h2 id="deleted_source_sgd">Deleted from sequence source (SGD)</h2>

The sequence has been deleted from its source, in this case SGD.

<h2 id="deleted_source_ensembl">Deleted from sequence source (ENSEMBL)</h2>

The sequence has been deleted from its source, in this case ENSEMBL.

<h2 id="deleted_source_pdb">Deleted from sequence source (PDB)</h2>

The sequence has been deleted from its source, in this case PDB.

<h2 id="deleted_source_refseq">Deleted from sequence source (RefSeq)</h2>

The sequence has been deleted from its source, in this case RefSeq.

<h2 id="deleted_swiss-prot">Deleted from Swiss-Prot</h2>

The entry has been deleted from UniProtKB reviewed / Swiss-Prot

<h2 id="redundant_sequence">Redundant sequence</h2>

The entry has been deleted because its sequence is redundant. Redundant sequences and over-represented sequences mean that we have too many instances of a protein in UniProtKB. One example would be SARS-CoV-2, where we initially, after the outbreak of the pandemic, created UniProtKB entries for all submitted SARS-CoV-2 sequences. This has caused an over-representation, and thus most of the redundant proteins have later been deleted.

<h2 id="redundant_proteome">Redundant proteome</h2>

A [redundant proteome](https://www.uniprot.org/help/proteome_redundancy_faq) is one in which there is another highly similar proteome available for the same species. The proteins from the redundant proteomes have been removed from UniProtKB to manage the size of the database.

<h2 id="excluded_proteome">Excluded proteome</h2>

An excluded proteome is deemed unsuitable to be retained in UniProtKB, and its entries are deleted. Further details can be found in the [help page about excluded proteome help](https://www.uniprot.org/help/proteome_exclusion_reasons).

<h2 id="over-represented_sequence">Over-represented sequence</h2>

The entry has been deleted because its sequence is redundant. Redundant sequences and over-represented sequences mean that we have too many instances of a protein in UniProtKB. One example would be SARS-CoV-2, where we initially, after the outbreak of the pandemic, created UniProtKB entries for all submitted SARS-CoV-2 sequences. This has caused an over-representation, and thus most of the redundant proteins have later been deleted.

<h2 id="Not-part-of-a-reference-proteome">Not part of a reference-proteome</h2>
The entry has been deleted because it is not part of a reference proteome. UniProtKB is undergoing a change where it will be composed of entries from reference proteomes, and other proteins of biological interest.

# See also

- [What are UniProtKB's criteria for defining a CDS as a protein?](https://www.uniprot.org/help/cds_protein_definition)
- [Does UniProtKB contain all protein sequences?](https://www.uniprot.org/help/uniprotkb_coverage)
- [Why do we keep dubious sequences in UniProtKB? How to discard them from a protein set?](https://www.uniprot.org/help/dubious_sequences)
- [How frequently is UniProt released? What is the synchronization delay with other databases?](https://www.uniprot.org/help/synchronization)
- [Accession number](https://www.uniprot.org/help/accession_numbers)
