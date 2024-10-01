---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

# Change of predicate for names of isoform sequences in UniProt RDF

**On November 27th, 2024**

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
# Upcoming changes in UniProt API for retrieving data from the UniParc dataset
**On November 27th, 2024**

**Please note that the following changes are NOT for UniProtKB. They only apply to UniParc.**

In the next release, we will introduce significant changes to the UniParc model to improve scalability of cross-references. Here's an overview of what to expect:

- **Splitting of the UniParc Model**: The UniParc model will be divided into two parts: a core (lighter) version of UniParc and its cross-references.

- **Backward Compatibility**:
    - The existing API for retrieving a single UniParc entry will remain backward compatible.
    - The endpoint `/uniparc/{upi}` will continue to return the full UniParc object along with all cross-references.

- **New Endpoint for core UniParc Entry**:
    - If you wish to retrieve a UniParc entry without cross-references, a new endpoint `/uniparc/{upi}/light` will be introduced.

- **Changes to APIs**:
    - The following APIs responses will no longer include cross-references:
      - `/uniparc/search`
      - `/uniparc/stream` 
      - `/uniparc/upis`
    - To retrieve UniParc core entries, followed by cross-references, you'll need to make two separate calls.
    - All current search fields will still be supported for querying.
    - Get all the cross-references for a single UniParc id via:
      - `/uniparc/{upi}/databases`, or
      - `/uniparc/{upi}/databases/stream`.

These changes are aimed at optimising performance for large-scale cross-references and ensuring future scalability. Please plan accordingly for when these updates are implemented.
