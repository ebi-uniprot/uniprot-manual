---
title: Change of the RDF representation of our cross-references to RefSeq
type: help
categories: RDF,UniProtKB,changes
---

We will modify the RDF description of our cross-references to protein resources in the RefSeq database to provide explicit links to their corresponding RefSeq nucleotide sequences.

Currently, our cross-references show the identifier of a RefSeq nucleotide sequence through an `rdfs:comment` property with a string literal value. We will replace this by a `translatedFrom` property that will link the RefSeq protein to a resource that corresponds to its coding sequence (CDS) and, similarly to the description of EMBL-CDS resources, this CDS will be linked through a `locatedOn` property to the transcript or genomic sequence that contains it.

Note that the `translatedFrom` property is not the inverse of the `translatedTo` property that is used, for instance, in the description of Ensembl cross-references. The latter is used to link mature transcripts (whose sequence includes untranslated regions in addition to the CDS) to proteins.

Example: [Q00266](https://www.uniprot.org/uniprotkb/Q00266.ttl)

Current format:

    uniprot:Q00266
      rdfs:seeAlso  .


      rdf:type up:Resource ;
      up:database  ;
      rdfs:comment "NM_000429.2" .

Future format:

    uniprot:Q00266
      rdfs:seeAlso  .


      rdf:type up:Resource ;
      up:database  ;
      up:translatedFrom  .


      up:locatedOn  .
