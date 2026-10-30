---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

**Table of contents**

   * [Simplification of UniParc XML root tag](#simplification-of-uniparc-xml-root-tag) - **From November 4, 2026**
   * [Change to the cross-references to MaizeGDB](#change-to-the-cross-references-to-maizegdb) - **From January 13, 2027**
   
# Simplification of UniParc XML root tag

Due to a technical limitation of the high-performance data processing framework used to generate UniParc XML, we have to simplify the root tag of the UniParc XML format by removing all attributes except the namespace:

```xml
<uniparc xmlns="http://uniprot.org/uniparc">
```

**Impact:** Any code that parses the root tag and expects attributes other than the namespace must be updated to not rely on them.

# Change to the cross-references to MaizeGDB

We will introduce an additional field in the cross-references to the "Maize Genetics and Genomics Database":https://www.maizegdb.org/. This will allow us to provide the gene name or the gene symbol curated by MaizeGDB curators, in addition to the gene identifier.

### Text format

Example: [P24067]:(https://rest.uniprot.org/uniprotkb/P24067.txt)

Current format:
```
DR   MaizeGDB; 66083; -.
```

New format:

```
DR   MaizeGDB; Zm00001eb229930; bip1.
```

### XML format

Example: {P24067]:(https://rest.uniprot.org/uniprotkb/P24067.xml)

Current format:

```
<dbReference type="MaizeGDB" id="66083"/>
```

New format:

```
<dbReference type="MaizeGDB" id="Zm00001eb229930"/>
 <property type="gene designation" value="bip1"/>
</dbReference>
```

This change does not affect the XSD, but may nevertheless require code changes.

### RDF format

Example: [P24067]:(https://rest.uniprot.org/uniprotkb/P24067.ttl)

Current format

```
uniprot:P24067
 rdfs:seeAlso <http://purl.uniprot.org/maizegdb/66083> .
<http://purl.uniprot.org/maizegdb/66083>
 rdf:type up:Resource ;
 up:database <http://purl.uniprot.org/database/MaizeGDB> .
```

New format:

```
uniprot:P24067
 rdfs:seeAlso <http://purl.uniprot.org/maizegdb/Zm00001eb229930> .
<http://purl.uniprot.org/maizegdb/Zm00001eb229930>
 rdf:type up:Resource ;
 up:database <http://purl.uniprot.org/database/MaizeGDB> .
 rdfs:comment "bip1" . 
```
