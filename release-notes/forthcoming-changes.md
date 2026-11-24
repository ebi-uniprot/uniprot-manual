---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

**Table of contents**

   * [Change to the cross-references to MaizeGDB](#change-to-the-cross-references-to-maizegdb) - **From January 13, 2027**
   * [Pan-Proteome FASTA header changes](#pan-proteome-fasta-header-changes) - **2027_02**

# Change to the cross-references to MaizeGDB

We will introduce an additional field in the cross-references to the [Maize Genetics and Genomics Database](https://www.maizegdb.org/). This will allow us to provide the gene name or the gene symbol curated by MaizeGDB curators, in addition to the gene identifier.

### Text format

Example: [P24067](https://rest.uniprot.org/uniprotkb/P24067.txt)

Current format:
```
DR   MaizeGDB; 66083; -.
```

New format:

```
DR   MaizeGDB; Zm00001eb229930; bip1.
```

### XML format

Example: [P24067](https://rest.uniprot.org/uniprotkb/P24067.xml)

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

Example: [P24067](https://rest.uniprot.org/uniprotkb/P24067.ttl)

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

# Pan-Proteome FASTA header changes
The fasta headers will include protein names from UniParc as well and the order of the ProteinName and GeneName are changed, 

```
ProteinName: the recommended name of the UniProtKB entry or the submitted name
             from the source of a UniParc entry
             (https://www.uniprot.org/help/protein_names)

GN (GeneName): the first gene name of the UniProtKB entry or the gene name from
               the source of a UniParc entry
               (https://www.uniprot.org/help/gene_name)
```
               

Current format
```
>ppIdentifier|UniparcIdentifier ProteinFrequency ProteomeIdentifier SourceIdentifier OX=OrganismIdentifier OS=OrganismName [ ; db|EntryAccession|EntryName ProteinName GN=GeneName PE=ProteinExistence SV=SequenceVersion ]
```

Example:
```
>pp562|UPI0000138ECA 79% UP000000625 AAC75106 OX=83333 OS=Escherichia coli str. K-12 sub str. MG1655 ; sp|P71242|WCAK_ECOLI Colanic acid biosynthesis protein WcaK GN=wcaK PE=3 SV=2
```


New format
```
>ppIdentifier|UniparcIdentifier ProteinFrequency ProteomeIdentifier SourceIdentifier ProteinName GN=GeneName OX=OrganismIdentifier OS=OrganismName [ ; db|EntryAccession|EntryName PE=ProteinExistence SV=SequenceVersion ]
```

Example:
```
>pp562|UPI0000138ECA 79% UP000000625 AAC75106 Colanic acid biosynthesis protein WcaK GN=wcaK OX=83333 OS=Escherichia coli str. K-12 sub str. MG1655 ; sp|P71242|WCAK_ECOLI PE=3 SV=2
```
