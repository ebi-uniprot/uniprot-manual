---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---


**Table of contents**

   * Change of URIs for taxonomic ranks in RDF - **On June 04, 2025**

### Change of URIs for taxonomic ranks in RDF

The NCBI [replaced the taxonomic rank 'Superkingdom' by the new ranks 'Domain' and 'Realm'](https://ncbiinsights.ncbi.nlm.nih.gov/2025/02/27/new-ranks-ncbi-taxonomy/). We use this opportunity to change the URIs of all ranks by adding the prefix ```Taxonomic_Rank_``` to add context to terms like 'Domain' that can have several meanings in the context of UniProt. For instance,

```<owl:Thing rdf:about="http://purl.uniprot.org/core/Species">```

will be changed to:

```<owl:Thing rdf:about="http://purl.uniprot.org/core/Taxonomic_Rank_Species">```
