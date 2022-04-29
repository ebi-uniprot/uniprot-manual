---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

Planned changes for UniProt

# Ensembl cross-references in UniProtKB: adding version numbers to Ensembl identifiers

In UniProtKB entries, we are going to include version numbers in cross-referenced Ensembl identifiers wherever possible.

Example: [A6NEM1](https://www.uniprot.org/uniprotkb/A6NEM1)

## Current format

### Text format

Example: [A6NEM1](https://rest.uniprot.org/uniprotkb/A6NEM1?format=txt)

```
DR   Ensembl; ENST00000618348; ENSP00000481078; ENSG00000197978.
DR   Ensembl; ENST00000620574; ENSP00000479589; ENSG00000274320.
```

### XML format

Example: [A6NEM1](https://rest.uniprot.org/uniprotkb/A6NEM1?format=xml)

```
<dbReference type="Ensembl" id="ENST00000618348">
  <property type="protein sequence ID" value="ENSP00000481078"/>
  <property type="gene ID" value="ENSG00000197978"/>
</dbReference>
<dbReference type="Ensembl" id="ENST00000620574">
  <property type="protein sequence ID" value="ENSP00000479589"/>
  <property type="gene ID" value="ENSG00000274320"/>
</dbReference>
```

### RDF format

Example: [A6NEM1](https://rest.uniprot.org/uniprotkb/A6NEM1?format=rdf)

```
uniprot:A6NEM1
rdfs:seeAlso  <http://rdf.ebi.ac.uk/resource/ensembl.transcript/ENST00000618348>, <http://rdf.ebi.ac.uk/resource/ensembl.transcript/ENST00000620574> .
<http://rdf.ebi.ac.uk/resource/ensembl.transcript/ENST00000618348> rdf:type up:Transcript_Resource ;
  up:database <http://purl.uniprot.org/database/Ensembl> ;
  up:translatedTo <http://rdf.ebi.ac.uk/resource/ensembl.protein/ENSP00000481078> ;
  up:transcribedFrom <http://rdf.ebi.ac.uk/resource/ensembl/ENSG00000197978> .
<http://rdf.ebi.ac.uk/resource/ensembl.transcript/ENST00000620574> rdf:type up:Transcript_Resource ;
  up:database <http://purl.uniprot.org/database/Ensembl> ;
  up:translatedTo <http://rdf.ebi.ac.uk/resource/ensembl.protein/ENSP00000479589> ;
  up:transcribedFrom <http://rdf.ebi.ac.uk/resource/ensembl/ENSG00000274320> .
```

## New format

### Text format

```
DR   Ensembl; ENST00000618348.2; ENSP00000481078.1; ENSG00000197978.10.
DR   Ensembl; ENST00000620574.2; ENSP00000479589.1; ENSG00000274320.2.
```

### XML format

```
<dbReference type="Ensembl" id="ENST00000618348.2">
  <property type="protein sequence ID" value="ENSP00000481078.1"/>
  <property type="gene ID" value="ENSG00000197978.10"/>
</dbReference>
<dbReference type="Ensembl" id="ENST00000620574.2">
  <property type="protein sequence ID" value="ENSP00000479589.1"/>
  <property type="gene ID" value="ENSG00000274320.2"/>
</dbReference>
```

### RDF format

```
uniprot:A6NEM1
rdfs:seeAlso  <http://rdf.ebi.ac.uk/resource/ensembl.transcript/ENST00000618348.2>, <http://rdf.ebi.ac.uk/resource/ensembl.transcript/ENST00000620574.2> .
<http://rdf.ebi.ac.uk/resource/ensembl.transcript/ENST00000618348.2> rdf:type up:Transcript_Resource ;
  up:database <http://purl.uniprot.org/database/Ensembl> ;
  up:translatedTo <http://rdf.ebi.ac.uk/resource/ensembl.protein/ENSP00000481078.1> ;
  up:transcribedFrom <http://rdf.ebi.ac.uk/resource/ensembl/ENSG00000197978.10> .
<http://rdf.ebi.ac.uk/resource/ensembl.transcript/ENST00000620574.2> rdf:type up:Transcript_Resource ;
  up:database <http://purl.uniprot.org/database/Ensembl> ;
  up:translatedTo <http://rdf.ebi.ac.uk/resource/ensembl.protein/ENSP00000479589.1> ;
  up:transcribedFrom <http://rdf.ebi.ac.uk/resource/ensembl/ENSG00000274320.2> .
```

# Ensembl cross-references in UniParc: adding version numbers to Ensembl identifiers

In UniParc cross-references to Ensembl, we are going to introduce version numbers to Ensembl identifiers, similarly to what will be done for UniProtKB.

Example: [UPI000442D01A](https://www.uniprot.org/uniparc/UPI000442D01A)

## Current format

### XML format

Example: [UPI000442D01A](https://rest.uniprot.org/uniparc/UPI000442D01A?format=xml)

```
<dbReference type="Ensembl" id="ENSP00000481078" version_i="1" active="Y" created="2014-07-21" last="2021-10-18">
   <property type="NCBI_taxonomy_id" value="9606"/>
   <property type="gene_name" value="GOLGA6L9"/>
   <property type="proteome_id" value="UP000005640"/>
   <property type="component" value="Chromosome 15"/>
</dbReference>
```

### RDF format

Example: [UPI000442D01A](https://rest.uniprot.org/uniparc/UPI000442D01A?format=rdf)

```
uniparc:UPI000442D01A
  rdf:type up:Sequence ;
  up:sequenceFor uniprot:A6NEM1, isoform:A6NEM1-1, ensembl:ENSP00000481078 .
ensembl:ENSP00000481078
  up:database <http://purl.uniprot.org/database/Ensembl> ;
  up:version 1 .
```

## New format

### XML format

```
<dbReference type="Ensembl" id="ENSP00000481078" version_i="1" active="Y" version="1" created="2014-07-21" last="2021-10-18">
   <property type="NCBI_taxonomy_id" value="9606"/>
   <property type="gene_name" value="GOLGA6L9"/>
   <property type="proteome_id" value="UP000005640"/>
   <property type="component" value="Chromosome 15"/>
</dbReference>
```

### RDF format

```
uniparc:UPI000442D01A
  rdf:type up:Sequence ;
  up:sequenceFor uniprot:A6NEM1, isoform:A6NEM1-1, ensembl:ENSP00000481078.1 .
ensembl:ENSP00000481078
  up:database <http://purl.uniprot.org/database/Ensembl> ;
  up:version 1 ;
  up:reportedVersion 1 .
```
