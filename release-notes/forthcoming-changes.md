---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

**Table of contents**

   * Change of URIs for taxonomic ranks in RDF - **On June 18, 2025**
   * Change of URIs for the PROSITE database - **On June 18, 2025**
   * Introduction of explicit links between citations and their retraction notice in UniProt RDF - **On June 18, 2025**

### Change of URIs for taxonomic ranks in RDF

The NCBI [replaced the taxonomic rank 'Superkingdom' by the new ranks 'Domain' and 'Realm'](https://ncbiinsights.ncbi.nlm.nih.gov/2025/02/27/new-ranks-ncbi-taxonomy/). We use this opportunity to change the URIs of all ranks by adding the prefix ```Taxonomic_Rank_``` to add context to terms like 'Domain' that can have several meanings in the context of UniProt. For instance,

```<owl:Thing rdf:about="http://purl.uniprot.org/core/Species">```

will be changed to:

```<owl:Thing rdf:about="http://purl.uniprot.org/core/Taxonomic_Rank_Species">```

### Change of URIs for the PROSITE database

For historic reasons, UniProt had to generate URIs to cross-reference databases that did not have an RDF representation or did not provide stable URIs such as [PURLs](https://en.wikipedia.org/wiki/Persistent_uniform_resource_locator) (permanent uniform resource locators). The SIB Swiss Institute of Bioinformatics has now committed to provide stable URIs for the resources that it supports. [PROSITE](https://prosite.expasy.org/) is now also using this service, therefore we will change the PROSITE URIs accordingly:

The links to PROSITE signatures (used in UniProtKB cross-references and in UniParc) will change from:

```
http://purl.uniprot.org/prosite/PS50835
```
to:
```
https://purl.expasy.org/prosite/signature/PS50835
```

The links to PROSITE annotation rules (aka: ProRule as used in UniProtKB attributions) will change from:
```
http://purl.uniprot.org/prosite-prorule/PRU00114
```
to:
```
https://purl.expasy.org/prosite/rule/PRU00114
```

### Introduction of explicit links between citations and their retraction notice in UniProt RDF

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
