---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

**Table of contents**

   * [Finalizing the reorganization of the protein space in UniProtKB](#finalizing-the-reorganization-of-the-protein-space-in-uniprotkb) - **With release 2026_02**
   * [UniParc XML changes](#uniparc-xml-changes) - **With release 2026_02**
   * [UniParc API changes](#uniparc-api-changes) - **With release 2026_02**
   * [ChEBI data model change in UniProt SPARQL endpoint](#chebi-data-model-change-in-uniprot-sparql-endpoint) - **From release 2026_02**
   * [Planned automatic annotation service developments](#planned-automatic-annotation-service-developments) - **From release 2026_02**

# Finalizing the reorganization of the protein space in UniProtKB

Release 2026_02 will see the completion of our proteomes changes that have been in progress since release 2026_04 (15th Oct 2025). 
Key changes you will see in 2026_02 release will include:
- The protein space in UniProtKB will be restricted to only those sequences which are part of a Reference Proteome. It will also contain additional proteins that are expertly reviewed/Swiss-Prot entries, or unreviewed entries associated with experimental [Gene Ontology](https://www.uniprot.org/help/gene-ontology) annotations or additional biologically important data, such as proteins with an experimental 3D structure;
- New pan proteome dataset created for all species with at least 3 proteomes. One representative sequence for each protein cluster, including both reference and non reference proteomes;
- Deprecation of proteome redundancy. We now have a new method for selecting reference proteomes that encompasses redundancy;
- Deprecation of protein redundancy. We will provide unique UniProtKB accessions for each protein sequence;
- Update of proteomes categories. As a result of proteome redundancy deprecation, the proteome category “redundant proteomes” will be removed. UniProt is now categorizing proteomes as either ‘reference’, ‘non-reference’ or ‘excluded’;
- Update of proteome exclusion reasons. New exclusion reasons from RefSeq or UniProt have been added to the list of exclusion reasons;
- Similarity (in percentage) of non-reference proteomes against the reference proteomes for that species will be available.

Since release 2026_04 the number of Reference Proteomes will have increased by 36% (reflecting a 34% increase on species covered), while the number of proteins in UniProtKB will have decreased by 45%.

For more details on our novel workflow and how reference proteomes are changing, check: Inside UniProt: [Capturing the Diversity of Life - Reorganizing the Protein Space in UniProtKB](https://insideuniprot.blogspot.com/2025/06/capturing-diversity-of-life.html)

For a brief summary of the changes to proteomes and subsequent UniProtKB changes please visit our [summary of proteomes](https://www.uniprot.org/help/refprot_only_changes) changes help page.


# UniParc XML changes

In Uniparc XML, the ```proteome_id``` and ```component``` properties have been retired. In their place, a new property type, ```proteomeid_component``` has been introduced. Its value is a concatenation of the ProteomeID and Component, joined by a colon. 
This property type is multi-valued and can appear multiple times with distinct entries.
e.g
```
<property type="proteomeid_component" value="UP000179299:Segment"/>
<property type="proteomeid_component" value="UP000179429:Genome"/>
```

# UniParc API changes
## Consolidation of ```proteomeId``` and ```component``` fields in the UniParc databases endpoint.

In the UniParc databases endpoint response for the two existing fields ```proteomeId``` and ```component``` will be removed and replaced with ```list of proteomes``` each proteome in the response will have the fields ```id``` and ```component```.
e.g
```
{
  "proteomes": [
    {
      "id": "proteome1",
      "component": "component1"
    },
    {
      "id": "proteome2",
      "component": "component2"
    }
  ]
}
```
## Searching UniParc using the proteomes component
Users searching UniParc for a proteome component using the API will need to enter the fully qualified name of the proteome component in the form of <proteome_id>:<component_name> when submitting the query.
User using the website advanced search functionality will be able to carry out the same query using the search fields ```proteome_id``` and ```component_name```.

```proteomecomponent:'UP000008269:Segment'```


# ChEBI data model change in UniProt SPARQL endpoint

The [UniProt SPARQL endpoint](https://sparql.uniprot.org/) includes a snapshot of the ChEBI ontology that is in sync with a specific UniProt release. We will adapt our snapshots to match the data model changes in the core [ChEBI ontology provided by the ChEBI team](https://chembl.blogspot.com/2025/07/chebi-20-data-products.html).

# Planned automatic annotation service developments
We aim to provide a better automatic annotation service, both in UniParc and as a downloadable tool, through [UniFIRE](https://gitlab.ebi.ac.uk/uniprot-public/unifire).
