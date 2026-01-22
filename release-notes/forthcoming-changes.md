---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

**Table of contents**

   * [UniParc changes](#uniparc-changes) - **With release 2026_02**
   * [ChEBI data model change in UniProt SPARQL endpoint](#chebi-data-model-change-in-uniprot-sparql-endpoint) - **From release 2026_02**


# UniParc changes

_below to be rewritten according to usual editorial style_
_check with Rizwan and Supun_

Removed proteome_id & component properties (types)
introduce new property type proteomeid_component value of which would be ProteomeId & Component joined by :
same property type can appear multiple times with different values
e-g
```
<property type="NCBI_taxonomy_id" value="3816"/>
<property type="NCBI_taxonomy_id" value="3817"/>
```

Also, change in the way to query for components through the API (only proteome + components together)

# ChEBI data model change in UniProt SPARQL endpoint

The [UniProt SPARQL endpoint](https://sparql.uniprot.org/) includes a snapshot of the ChEBI ontology that is in sync with a specific UniProt release. We will adapt our snapshots to match the data model changes in the core [ChEBI ontology provided by the ChEBI team](https://chembl.blogspot.com/2025/07/chebi-20-data-products.html).
