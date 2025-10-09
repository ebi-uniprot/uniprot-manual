---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

**Table of contents**

   * [Reorganizing the protein space in UniProtKB](#reorganizing-the-protein-space-in-uniprotkb) - **From October 8, 2025**
   * [Change in UniParc XML format to associate proteome IDs and components](#change-in-uniparc-xml-format-to-associate-proteome-ids-and-components) - **From January 21, 2026**


# Reorganizing the protein space in UniProtKB

Starting from the current release 2025_04, we have been refactoring our [Reference Proteome](https://www.uniprot.org/help/reference_proteome) selection pipeline to ensure an improved representation of species biodiversity in the UniProt Knowledgebase (UniProtKB). From release 2026_02 onwards (currently planned for the first half of 2026), we will restrict the protein space in UniProtKB to only those sequences which are part of a Reference Proteome in addition to the expert reviewed UniProtKB/Swiss-Prot section, and also unreviewed entries associated with experimental [Gene Ontology](https://www.uniprot.org/help/gene-ontology) annotations or additional biologically important data such as a 3D structure.

This reorganization, between release 2025_04 and 2026_02, will result in a change in the content and size of the database. The number of Reference Proteomes will increase by 36% (reflecting a 34% increase on species covered), while the number of proteins in UniProtKB can be decreased by 43%.

All deprecated proteomes ([download list](https://ftp.ebi.ac.uk/pub/contrib/UniProt/proteomes/proteomes_to_be_removed_from_UPKB.tsv)), plus all proteomes which do not qualify for consideration in the new pipeline, will be available through [UniParc](https://www.uniprot.org/uniparc/). When you search in the [Proteomes](https://www.uniprot.org/proteomes/) portal for these proteomes, you will be directed to UniParc to access your protein set. To download your proteome, we recommend to use the new [UniParc proteomes FASTA format](https://www.uniprot.org/help/fasta-headers#uniparc-proteomes) which contains biological information from the UniParc source database entries that are associated with the requested proteome.

If the annotation provided by UniProtKB is particularly important to your work, or your organism is actively worked on by a research community, but has not been selected as a Reference Proteome, please [contact us](https://www.uniprot.org/contact) and we will consider promoting it to Reference Proteome status.

Please go to the [UniProt blog](https://insideuniprot.blogspot.com/2025/06/capturing-diversity-of-life.html) for further information.

# Change in UniParc XML format to associate proteome IDs and components

In the current UniParc format, the proteome information that is provided for some `dbReference` types is given with the two `property` types `proteome_id` and `component`. In the future we will provide proteome information for new `dbReference` types that may be linked to more than one proteome. For this reason we have to group the proteome information in a single new `property` type `proteomeid_component` whose value is the proteome ID and component, joined together by a colon sign `:`.

Example: [UPI0000000239](https://rest.uniprot.org/uniparc/UPI0000000239.xml)

Current format:

```
<dbReference type="Ensembl" id="ENSP00000251595" version_i="1" active="Y" version="6" created="2003-04-01" last="2024-08-23">
  <property type="gene_name" value="HBA2"/>
  <property type="proteome_id" value="UP000005640"/>
  <property type="component" value="Chromosome 16"/>
  <property type="NCBI_taxonomy_id" value="9606"/>
</dbReference>
```

New format:

```
<dbReference type="Ensembl" id="ENSP00000251595" version_i="1" active="Y" version="6" created="2003-04-01" last="2024-08-23">
  <property type="gene_name" value="HBA2"/>
  <property type="proteomeid_component" value="UP000005640:Chromosome 16"/>
  <property type="NCBI_taxonomy_id" value="9606"/>
</dbReference>
```
