---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

# Change of predicate for names of isoform sequences in UniProt RDF

**On July 24th, 2024**

In the UniProt RDF format, all names of an isoform sequence are currently listed with the [`up:name`](http://purl.uniprot.org/core/name) predicate. We will change this to use the predicate [`skos:prefLabel`](http://www.w3.org/2004/02/skos/core#prefLabel) to designate the preferred name selected by UniProtKB/Swiss-Prot curators and the predicate [`skos:altLabel`](http://www.w3.org/2004/02/skos/core#altLabel) for the other synonyms.

Example: [P05067](https://rest.uniprot.org/uniprotkb/P05067.ttl)

Current format:

```turtle
<http://purl.uniprot.org/isoforms/P05067-1> 
  a up:Simple_Sequence ;
  up:name "APP770" ;
  up:name "PreA4 770" .
```

New format:

```turtle
<http://purl.uniprot.org/isoforms/P05067-1> 
  a up:Simple_Sequence ;
  skos:prefLabel "APP770" ;
  skos:altLabel "PreA4 770" .
```

This change can be undone with the following SPARQL update query:

```sparql
insert { ?sequence up:name ?name }
# delete { ?sequence ?pred ?name } # optional: to remove the new style of naming
where { 
 values (?pred) {(skos:prefLabel) (skos:altLabel)}
  ?protein a up:Protein ;
           up:sequence ?sequence .
  ?sequence ?pred ?name .
}
```
