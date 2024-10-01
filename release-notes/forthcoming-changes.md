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

# Changes in UniProt website REST API for UniParc

**On November 27th, 2024**

UniParc entries may contain ten thousands of cross-references. This information is not relevant for all users and can make data downloads slow. For these reasons we will make the following changes to our API:

- **New endpoint for UniParc core data** (sequence and InterPro matches):
  - `/uniparc/{upi}/light`

- **New endpoints for UniParc cross-references**:
  - `/uniparc/{upi}/databases`
  - `/uniparc/{upi}/databases/stream`

- **Changes to existing endpoints**:  
  The responses of the following endpoints will no longer include cross-references:
  - `/uniparc/search` (all current search fields will be supported)
  - `/uniparc/stream`
  - `/uniparc/upis`

- **Backward compatibility**:
  - `/uniparc/{upi}` will continue to return the full UniParc entry, including all cross-references.

If you have questions about these changes, please do not hesitate to contact our [our helpdesk](https://www.uniprot.org/contact).
