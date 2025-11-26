---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

**Table of contents**

   * [Reorganizing the protein space in UniProtKB](#reorganizing-the-protein-space-in-uniprotkb) - **From October 15, 2025**
   * [ChEBI data model change in UniProt SPARQL endpoint](#chebi-data-model-change-in-uniprot-sparql-endpoint) - **From release 2026_01**

# Reorganizing the protein space in UniProtKB

Starting from the current release 2025_04, we have been refactoring our [Reference Proteome](https://www.uniprot.org/help/reference_proteome) selection pipeline to ensure an improved representation of species biodiversity in the UniProt Knowledgebase (UniProtKB). From release 2026_02 onwards (currently planned for the first half of 2026), we will restrict the protein space in UniProtKB to only those sequences which are part of a Reference Proteome in addition to the expert reviewed UniProtKB/Swiss-Prot section, and also unreviewed entries associated with experimental [Gene Ontology](https://www.uniprot.org/help/gene-ontology) annotations or additional biologically important data such as a 3D structure.

This reorganization, between release 2025_04 and 2026_02, will result in a change in the content and size of the database. The number of Reference Proteomes will increase by 36% (reflecting a 34% increase on species covered), while the number of proteins in UniProtKB can be decreased by 45%.

All deprecated proteomes ([download list](https://ftp.ebi.ac.uk/pub/contrib/UniProt/proteomes/proteomes_losing_UniProtKB_entries.tsv)), plus all proteomes which do not qualify for consideration in the new pipeline, will be available through [UniParc](https://www.uniprot.org/uniparc/). When you search in the [Proteomes](https://www.uniprot.org/proteomes/) portal for these proteomes, you will be directed to UniParc to access your protein set. To download your proteome, we recommend to use the new [UniParc proteomes FASTA format](https://www.uniprot.org/help/fasta-headers#uniparc-proteomes) which contains biological information from the UniParc source database entries that are associated with the requested proteome.

If the annotation provided by UniProtKB is particularly important to your work, or your organism is actively worked on by a research community, but has not been selected as a Reference Proteome, please [contact us](https://www.uniprot.org/contact) and we will consider promoting it to Reference Proteome status.

For more details on our novel workflow and how reference proteomes are changing, check: [Inside UniProt: Capturing the Diversity of Life - Reorganizing the Protein Space in UniProtKB](https://insideuniprot.blogspot.com/2025/06/capturing-diversity-of-life.html)

For a brief summary of the changes to proteomes and subsequent UniProtKB changes please visit our [summary of proteomes](https://www.uniprot.org/help/refprot_only_changes) changes help page.


# ChEBI data model change in UniProt SPARQL endpoint

The [UniProt SPARQL endpoint](https://sparql.uniprot.org/) includes a snapshot of the ChEBI ontology that is in sync with a specific UniProt release. We will adapt our snapshots to match the data model changes in the core [ChEBI ontology provided by the ChEBI team](https://chembl.blogspot.com/2025/07/chebi-20-data-products.html).
