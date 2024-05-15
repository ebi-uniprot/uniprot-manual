---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01

---

# Change of predicates used in UniProt RDF for names of isoform sequences

**On July 24th, 2024**

In the UniProt RDF: Names of isoforms, where all marked up using the [`up:name`](http://purl.uniprot.org/core/name) predicate. We will change this to use the predicate [`skos:prefLabel`](http://www.w3.org/2004/02/skos/core#prefLabel) for designating the preferred name as selected by Swiss-Prot curators, and the predicate [`skos:altLabel`](http://www.w3.org/2004/02/skos/core#altLabel) for the other synonyms.

```turtle
<http://purl.uniprot.org/isoforms/P05067-1> 
  a up:Simple_Sequence .
 up:name "APP770" ;
 up:name "PreA4 770" .
```

will become

```turtle

<http://purl.uniprot.org/isoforms/P05067-1> 
  a up:Simple_Sequence .
 skos:prefLabel "APP770" ;
 skos:altLabel "PreA4 770" .
```

This change one can be undone with the following SPARQL update query.

```sparql
insert { ?sequence up:name ?name}
# delete { ?sequence ?pred ?name } #optional to remove the new style of naming
where { 
 values (?pred) {(skos:prefLabel) (skos:altLabel)}
  ?protein a up:Protein ;
    up:sequence ?sequence .
  ?sequence  ?pred ?name .
}
```
