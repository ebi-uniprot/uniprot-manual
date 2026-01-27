---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

**Table of contents**

   * [UniParc changes](#uniparc-changes) - **With release 2026_02**
   * [ChEBI data model change in UniProt SPARQL endpoint](#chebi-data-model-change-in-uniprot-sparql-endpoint) - **From release 2026_02**


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
