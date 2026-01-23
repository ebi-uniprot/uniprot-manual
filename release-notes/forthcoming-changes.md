---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

**Table of contents**

   * [UniParc changes](#uniparc-changes) - **With release 2026_02**
   * [ChEBI data model change in UniProt SPARQL endpoint](#chebi-data-model-change-in-uniprot-sparql-endpoint) - **From release 2026_02**


# UniParc XML changes

In uniparc XML, the ```proteome_id``` and ```component``` properties have been retired. In their place, a new property type, ```proteomeid_component``` has been introduced. Its value is a concatenation of the ProteomeID and Component, joined by a colon. 
This property type is multi-valued and can appear multiple times with distinct entries.
e-g
```
<property type="proteomeid_component" value="UP000179299:Segment"/>
<property type="proteomeid_component" value="UP000179429:Genome"/>
```

** Supun to update on API related changes - separate section --- Also, change in the way to query for components through the API (only proteome + components together)

# ChEBI data model change in UniProt SPARQL endpoint

The [UniProt SPARQL endpoint](https://sparql.uniprot.org/) includes a snapshot of the ChEBI ontology that is in sync with a specific UniProt release. We will adapt our snapshots to match the data model changes in the core [ChEBI ontology provided by the ChEBI team](https://chembl.blogspot.com/2025/07/chebi-20-data-products.html).
