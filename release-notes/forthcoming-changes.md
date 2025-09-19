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

In the current UniParc format, a `dbReference` proteome information is currently split into 2 different `property`, leading to possible confusion when a `dbReference` is linked to multiple proteomes.

The new format will group this information into 1 `property` of type `proteomeid_component` per pair of proteome and component, joined together by a colon sign `:`.

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

# Introduction of explicit links between citations and their retraction notice in UniProt RDF

In the UniProt RDF format, a rectracted citation is currently flagged as such by the presence of a [`up:scope`](http://purl.uniprot.org/core/scope) statement with a "RETRACTED" literal value on the reified [`up:citation`](http://purl.uniprot.org/core/citation) statement that links the UniProtKB entry to that citation. Similarly, a [`up:scope`](http://purl.uniprot.org/core/scope) statement with a literal value starting with "RETRACTION NOTICE OF PUBMED:" is currently found on the reified [`up:citation`](http://purl.uniprot.org/core/citation) statement that links the UniProtKB entry to the corresponding rectraction notice.

In order to represent the relationship between retracted citations and their retraction notices in a clearer way, we will remove those [`up:scope`](http://purl.uniprot.org/core/scope) statements, and directly link a retracted citation to its rectraction notice using a new `up:retractionNotice` predicate.

Example: [P21457](https://rest.uniprot.org/uniprotkb/P21457.ttl)

Current format:

```
<P21457>
  up:citation citation:8430337 ;
  up:citation citation:8097896 .

citation:8430337
  a up:Journal_Citation ;
  up:title "Role of the acylated amino terminus of recoverin in Ca(2+)-dependent membrane interaction." ;
  skos:exactMatch pubmed:8430337 .

<#_P21457-citation-8430337>
  a rdf:Statement ;
  rdf:subject <P21457> ;
  rdf:predicate up:citation ;
  rdf:object citation:8430337 ;
  up:scope "ROLE OF MYRISTOYLATION" , "RETRACTED PAPER" .

citation:8097896
  a up:Journal_Citation ;
  up:title "Recoverin's role: conclusion withdrawn." ;
  skos:exactMatch pubmed:8097896 .

<#_P21457-citation-8097896>
  a rdf:Statement ;
  rdf:subject <P21457> ;
  rdf:predicate up:citation ;
  rdf:object citation:8097896 ;
  up:scope "RETRACTION NOTICE OF PUBMED:8430337" .
```

New format:

```
<P21457>
  up:citation citation:8430337 ;
  up:citation citation:8097896 .

citation:8430337
  a up:Journal_Citation ;
  up:title "Role of the acylated amino terminus of recoverin in Ca(2+)-dependent membrane interaction." ;
  skos:exactMatch pubmed:8430337 ;
  up:retractionNotice citation:8097896 .

<#_P21457-citation-8430337>
  a rdf:Statement ;
  rdf:subject <P21457> ;
  rdf:predicate up:citation ;
  rdf:object citation:8430337 ;
  up:scope "ROLE OF MYRISTOYLATION" .

citation:8097896
  a up:Journal_Citation ;
  up:title "Recoverin's role: conclusion withdrawn." ;
  skos:exactMatch pubmed:8097896 .
```
