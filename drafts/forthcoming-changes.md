---
title: Forthcoming changes
type: releaseNotes
date: 2026-09-02
---

**Table of contents**

* [UniParc and UniProtKB RDF changes: regarding IRIs of InterPro matching regions](#uniparc-and-uniprotkb-rdf-changes:-regarding-iris-of-interpro-matching-regions)  * - **With release 2026_03**

UniProtKB and UniParc files both contain information regarding InterPro sequence matches.
The UniParc data contains the sequence regions that are matching, while the UniProtKB only contains the count of how many times an InterPro sequence matches the canonical isoform sequences.

We are now standardising how the concept of an InterPro signature match is identified in both the UniParc and UniProtKB RDF. This will make it easier to combine the richer InterPro match data in UniParc with queries on UniProtKB.

The new IRI pattern is `http://purl.uniprot.org/signatureSequenceMatch/D1BC406BBAEAECFD8C4400DA32ABAA75_PROSITE_PS00926_match_1`
while it used to be `http://purl.uniprot.org/isoforms/D0PNI2-1#PROSITE_PS00926_match_1` in UniProtKB and `http://purl.uniprot.org/signatureSequenceMatch/D1BC406BBAEAECFD8C4400DA32ABAA75_PROSITE_PS00926_286_299`.

This change will make it easier and faster to ask questions such as "Find UniProtKB entries with a match to ProSite:PS00926 within the first 100 residues of the start of the sequence".

```sparql
PREFIX up: <http://purl.uniprot.org/core/>
PREFIX faldo: <http://biohackathon.org/resource/faldo#>
PREFIX signatureSequenceMatch:<http://purl.uniprot.org/signatureSequenceMatch/>
PREFIX prosite:<https://purl.expasy.org/prosite/signature/>
SELECT *
WHERE {
  BIND(prosite:PS00926 AS ?prosite)
  GRAPH <http://sparql.uniprot.org/uniparc>{
    ?prosite up:signatureSequenceMatch ?ssm .
    ?ssm a faldo:Region ;
           faldo:begin ?begin .
    ?begin faldo:position ?beginPos ;
           faldo:reference ?uniparc .
  }
  GRAPH <http://sparql.uniprot.org/uniprot>{
    ?uniprot a up:Protein ;
            rdfs:seeAlso ?prosite .
    ?prosite up:signatureSequenceMatch ?ssm .
  }
  FILTER(?beginPos <= 100)
}
```
