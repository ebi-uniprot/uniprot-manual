---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

## Annotation of biologically relevant ligands in UniProtKB using ChEBI

**On August 3, 2022**

UniProtKB provides descriptions of the nature and binding sites of biologically relevant ligands that are essential for protein function, such as activators, inhibitors, cofactors, and substrates. We are going to replace the existing textual descriptions of these ligands with their equivalents from the [ChEBI](https://www.ebi.ac.uk/chebi) (Chemical Entities of Biological Interest) ontology to provide high quality computationally tractable annotation of biologically relevant ligands and their binding sites in proteins in UniProtKB. This enhanced dataset will provide improved support for efforts to study and predict functionally relevant interactions between proteins and small molecule ligands.

The impact of this change on the UniProtKB data model is described in the following subsections.

### Deprecation of 'Calcium binding', 'Metal' and 'Nucleotide binding' annotation types

Historically, UniProtKB has described a few classes of ligand binding sites with dedicated annotation types to make it easier to query them. This has been the case for ['Calcium binding'](https://www.uniprot.org/help/ca_bind), ['Metal binding'](https://www.uniprot.org/help/metal) and ['Nucleotide binding'](https://www.uniprot.org/help/np_bind). With the switch to the ChEBI ontology for ligand classification, this is no longer necessary, and we will deprecate these annotation types and convert the existing data to ['Binding site'](https://www.uniprot.org/help/binding) annotations.

### Structuring of 'Binding site' annotations

We are going to structure ['Binding site'](https://www.uniprot.org/help/binding) annotations in a way that allows us to standardize the description of a ligand, and optionally the bound part of the ligand, with the ChEBI ontology. The vast majority of ligands that are curated in UniProKB are small molecules that can be represented by a ChEBI entity. A minority of curated ligands are macromolecules. These are not within the scope of ChEBI, but ChEBI contains a limited set of high-level terms (such as DNA or RNA) that we will use to curate such ligands. For macromolecules and chelating structures, we will sometimes (if known and of interest) also describe the bound part of the ligand with a separate ChEBI entity.

In the subsections that describe the new representation of 'Binding site' annotations in different UniProtKB formats we use the following placeholders for annotation values:

<ins>Ligand:</ins>

Placeholders for values that describe the molecule (small or macro), ion or chelating structure that is bound by the protein:

* _LigandName_: The UniProt ChEBI name of the ligand, or the word "substrate". Mandatory.
* _LigandId_: The ChEBI identifier of the ligand. Mandatory, except when the _LigandName_ is "substrate".
* _LigandLabel_: A label used to distinguish individual instances of a ligand when a protein binds multiple ligands of the same chemical nature. Optional.
* _LigandNote_: A free text note that provides further details about the ligand. Optional.

<ins>Ligand part:</ins>

Placeholders for values that describe the specific part of the ligand that is bound by the protein (e.g. the iron atom in a heme, a specific type of amino-acid residue in a protein, the 3'-CCA end of a tRNA molecule):

* _LigandPartName_: The UniProt ChEBI name of the ligand part. Optional.
* _LigandPartId_: The ChEBI identifier of the ligand part. Optional.
* _LigandPartLabel_: A label used to distinguish individual instances of a ligand part when a protein binds multiple parts of the same chemical nature that are part of the same ligand. Optional.
* _LigandPartNote_: A free text note that provides further details about the ligand part. Optional.

<ins>Additional information:</ins>

Placeholders for values that provide additional information:

* _Note_: Free text note about the binding residue(s). Optional.
* _Evidences_: List of evidences that support the annotation. Optional.

Note also that 'Binding site' annotations will continue to be used primarily to describe individual amino acid residues that bind a ligand, but in order to standardize the existing ligand binding descriptions of the annotation types that will be deprecated, as well those of some ['Region'](https://www.uniprot.org/help/region) annotations, 'Binding site' annotations may also describe a range of amino acids when the exact ligand binding residues are unknown or where adjacent ligand binding residues had been grouped in the past.


#### Text format

We are going to make the following changes to the UniProtKB text format to standardize the description of a ligand, and optionally the bound part of the ligand, with the ChEBI ontology.

* We will deprecate the feature types `CA_BIND`, `METAL` and `NP_BIND`.
* We will introduce eight new qualifiers for the `BINDING` feature type to describe a ligand (`/ligand`, `/ligand_id`, `/ligand_label`, `/ligand_note`) and a ligand part (`/ligand_part`, `/ligand_part_id`, `/ligand_part_label`, `/ligand_part_note`).
* The representation of the annotation _Note_ and the _Evidences_ remains unchanged.

<pre>
FT   BINDING         <code style="font-style: italic">x</code>[..<code style="font-style: italic">y</code>]
FT                   /ligand="<code style="font-style: italic">LigandName</code>"
FT                   /ligand_id="ChEBI:<code style="font-style: italic">LigandId</code>"
FT                   /ligand_label="<code style="font-style: italic">LigandLabel</code>"
FT                   /ligand_note="<code style="font-style: italic">LigandNote</code>"
FT                   /ligand_part="<code style="font-style: italic">LigandPartName</code>"
FT                   /ligand_part_id="ChEBI:<code style="font-style: italic">LigandPartId</code>"
FT                   /ligand_part_label="<code style="font-style: italic">LigandPartLabel</code>"
FT                   /ligand_part_note="<code style="font-style: italic">LigandPartNote</code>"
FT                   /note="<code style="font-style: italic">Note</code>"
FT                   /evidence="<code style="font-style: italic">Evidences</code>"
</pre>

Example: [Q9H5X1](https://rest.uniprot.org/uniprotkb/Q9H5X1.txt)

Current format:

```
FT   METAL           89
FT                   /note="Zinc 1; shared with dimeric partner"
FT   METAL           89
FT                   /note="Zinc 2; shared with dimeric partner"
FT   METAL           123
FT                   /note="Zinc 1; shared with dimeric partner"
FT   METAL           123
FT                   /note="Zinc 2; shared with dimeric partner"
```

New format:

```
FT   BINDING         89
FT                   /ligand="Zn(2+)"
FT                   /ligand_id="ChEBI:CHEBI:29105"
FT                   /ligand_label="1"
FT                   /ligand_note="ligand shared between dimeric partners"
FT   BINDING         89
FT                   /ligand="Zn(2+)"
FT                   /ligand_id="ChEBI:CHEBI:29105"
FT                   /ligand_label="2"
FT                   /ligand_note="ligand shared between dimeric partners"
FT   BINDING         123
FT                   /ligand="Zn(2+)"
FT                   /ligand_id="ChEBI:CHEBI:29105"
FT                   /ligand_label="1"
FT                   /ligand_note="ligand shared between dimeric partners"
FT   BINDING         123
FT                   /ligand="Zn(2+)"
FT                   /ligand_id="ChEBI:CHEBI:29105"
FT                   /ligand_label="2"
FT                   /ligand_note="ligand shared between dimeric partners"
```

Example: [P39186](https://rest.uniprot.org/uniprotkb/P39186.txt)

Current format:

```
FT   METAL           79
FT                   /note="Iron (heme C 1 axial ligand); via tele nitrogen"
FT   METAL           97
FT                   /note="Iron (heme C 1 axial ligand); via tele nitrogen"
FT   METAL           114
FT                   /note="Iron (heme C 2 axial ligand); via tele nitrogen"
FT   METAL           137
FT                   /note="Iron (heme C 2 axial ligand); via tele nitrogen"
FT   BINDING         93
FT                   /note="Heme C 1; covalent"
FT                   /evidence="ECO:0000269|PubMed:21419779"
FT   BINDING         96
FT                   /note="Heme C 1; covalent"
FT                   /evidence="ECO:0000269|PubMed:21419779"
FT   BINDING         133
FT                   /note="Heme C 2; covalent"
FT                   /evidence="ECO:0000269|PubMed:21419779"
FT   BINDING         136
FT                   /note="Heme C 2; covalent"
FT                   /evidence="ECO:0000269|PubMed:21419779"
```

New format:

```
FT   BINDING         79
FT                   /ligand="heme c"
FT                   /ligand_id="ChEBI:CHEBI:61717"
FT                   /ligand_label="1"
FT                   /ligand_part="Fe"
FT                   /ligand_part_id="ChEBI:CHEBI:18248"
FT                   /note="axial binding residue"
FT                   /evidence="ECO:0000269|PubMed:21419779,
FT                   ECO:0007744|PDB:3ML1"
FT   BINDING         93
FT                   /ligand="heme c"
FT                   /ligand_id="ChEBI:CHEBI:61717"
FT                   /ligand_label="1"
FT                   /note="covalent"
FT                   /evidence="ECO:0000269|PubMed:21419779,
FT                   ECO:0007744|PDB:3ML1"
FT   BINDING         96
FT                   /ligand="heme c"
FT                   /ligand_id="ChEBI:CHEBI:61717"
FT                   /ligand_label="1"
FT                   /note="covalent"
FT                   /evidence="ECO:0000269|PubMed:21419779,
FT                   ECO:0007744|PDB:3ML1"
FT   BINDING         97
FT                   /ligand="heme c"
FT                   /ligand_id="ChEBI:CHEBI:61717"
FT                   /ligand_label="1"
FT                   /ligand_part="Fe"
FT                   /ligand_part_id="ChEBI:CHEBI:18248"
FT                   /note="axial binding residue"
FT                   /evidence="ECO:0000269|PubMed:21419779,
FT                   ECO:0007744|PDB:3ML1"
FT   BINDING         114
FT                   /ligand="heme c"
FT                   /ligand_id="ChEBI:CHEBI:61717"
FT                   /ligand_label="2"
FT                   /ligand_part="Fe"
FT                   /ligand_part_id="ChEBI:CHEBI:18248"
FT                   /note="axial binding residue"
FT                   /evidence="ECO:0000269|PubMed:21419779,
FT                   ECO:0007744|PDB:3ML1"
FT   BINDING         133
FT                   /ligand="heme c"
FT                   /ligand_id="ChEBI:CHEBI:61717"
FT                   /ligand_label="2"
FT                   /note="covalent"
FT                   /evidence="ECO:0000269|PubMed:21419779,
FT                   ECO:0007744|PDB:3ML1"
FT   BINDING         136
FT                   /ligand="heme c"
FT                   /ligand_id="ChEBI:CHEBI:61717"
FT                   /ligand_label="2"
FT                   /note="covalent"
FT                   /evidence="ECO:0000269|PubMed:21419779,
FT                   ECO:0007744|PDB:3ML1"
FT   BINDING         137
FT                   /ligand="heme c"
FT                   /ligand_id="ChEBI:CHEBI:61717"
FT                   /ligand_label="2"
FT                   /ligand_part="Fe"
FT                   /ligand_part_id="ChEBI:CHEBI:18248"
FT                   /note="axial binding residue"
FT                   /evidence="ECO:0000269|PubMed:21419779,
FT                   ECO:0007744|PDB:3ML1"
```

Example: [Q9H6S0](https://rest.uniprot.org/uniprotkb/Q9H6S0.txt)

Current format:

```
FT   REGION          1294..1296
FT                   /note="N6-methyladenosine residue binding"
FT                   /evidence="ECO:0000250|UniProtKB:Q9Y5A9"
...
FT   BINDING         1310
FT                   /note="N6-methyladenosine residue"
FT                   /evidence="ECO:0000250|UniProtKB:Q96MU7"
FT   BINDING         1360
FT                   /note="N6-methyladenosine residue"
FT                   /evidence="ECO:0000250|UniProtKB:Q96MU7"
```

New format:

```
FT   BINDING         1294..1296
FT                   /ligand="RNA"
FT                   /ligand_id="ChEBI:CHEBI:33697"
FT                   /ligand_part="N(6)-methyladenosine 5'-phosphate residue"
FT                   /ligand_part_id="ChEBI:CHEBI:74449"
FT                   /evidence="ECO:0000250|UniProtKB:Q9Y5A9"
FT   BINDING         1310
FT                   /ligand="RNA"
FT                   /ligand_id="ChEBI:CHEBI:33697"
FT                   /ligand_part="N(6)-methyladenosine 5'-phosphate residue"
FT                   /ligand_part_id="ChEBI:CHEBI:74449"
FT                   /evidence="ECO:0000250|UniProtKB:Q96MU7"
FT   BINDING         1360
FT                   /ligand="RNA"
FT                   /ligand_id="ChEBI:CHEBI:33697"
FT                   /ligand_part="N(6)-methyladenosine 5'-phosphate residue"
FT                   /ligand_part_id="ChEBI:CHEBI:74449"
FT                   /evidence="ECO:0000250|UniProtKB:Q96MU7"
```



#### XML format

We are going to make the following changes to the [UniProtKB XSD](https://www.uniprot.org/docs/uniprot.xsd) to standardize the description of a ligand, and optionally the bound part of the ligand, with the ChEBI ontology.

* We will deprecate the feature types `calcium-binding region`, `metal ion-binding site` and `nucleotide phosphate-binding region`.
* We will introduce two new elements, `ligand` and `ligandPart`, and corresponding types, `ligandType` and `ligandPartType`. The two types have the same structure that consists of the following four elements:
  * `name` for the value _LigandName_ / _LigandPartName_
  * `dbReference` for a cross-reference to a ChEBI record (_LigandId_ / _LigandPartId_)
  * `label` for the value _LigandLabel_ / _LigandPartLabel_
  * `note` for the value _LigandNote_ / _LigandPartNote_
* The representation of the annotation _Note_ and the _Evidences_ remains unchanged.

<pre>
    &lt;feature type="binding site" description="<code style="font-style: italic">Note</code>" evidence="<code style="font-style: italic">Evidences</code>"&gt;
      &lt;location&gt;
        ...
      &lt;/location&gt;
      &lt;ligand&gt;
        &lt;name&gt;<code style="font-style: italic">LigandName</code>&lt;/name&gt;
        &lt;dbReference type="ChEBI" id="<code style="font-style: italic">LigandId</code>"/&gt;
        &lt;label&gt;<code style="font-style: italic">LigandLabel</code>&lt;/label&gt;
        &lt;note&gt;<code style="font-style: italic">LigandNote</code>&lt;/note&gt;
      &lt;/ligand&gt;
      &lt;ligandPart&gt;
        &lt;name&gt;<code style="font-style: italic">LigandPartName</code>&lt;/name&gt;
        &lt;dbReference type="ChEBI" id="<code style="font-style: italic">LigandPartId</code>"/&gt;
        &lt;label&gt;<code style="font-style: italic">LigandPartLabel</code>&lt;/label&gt;
        &lt;note&gt;<code style="font-style: italic">LigandPartNote</code>&lt;/note&gt;
      &lt;/ligandPart&gt;
    &lt;/feature&gt;
</pre>

The XSD changes are highlighted in red color below:

<pre>
    &lt;!-- Feature definition begins --&gt;
    &lt;xs:complexType name="featureType"&gt;
    ...
        &lt;xs:sequence&gt;
        ...
            &lt;xs:element name="location" type="locationType"&gt;
                &lt;xs:annotation&gt;
                    &lt;xs:documentation&gt;Describes the sequence coordinates of the annotation.&lt;/xs:documentation&gt;
                &lt;/xs:annotation&gt;
            &lt;/xs:element&gt;
            <code style="color:red">&lt;xs:element name="ligand" type="ligandType" minOccurs="0"&gt;
                &lt;xs:annotation&gt;
                    &lt;xs:documentation&gt;Describes the chemical entity that is bound in annotations that describe binding sites.&lt;/xs:documentation&gt;
                &lt;/xs:annotation&gt;
            &lt;/xs:element&gt;
            &lt;xs:element name="ligandPart" type="ligandPartType" minOccurs="0"&gt;
                &lt;xs:annotation&gt;
                    &lt;xs:documentation&gt;Describes the specific part of a molecule that is bound in annotations that describe binding sites.&lt;/xs:documentation&gt;
                &lt;/xs:annotation&gt;
            &lt;/xs:element&gt;</code>
        &lt;/xs:sequence&gt;
        &lt;xs:attribute name="type" use="required"&gt;
        ...
            &lt;xs:simpleType&gt;
                &lt;xs:restriction base="xs:string"&gt;
                    &lt;xs:enumeration value="active site"/&gt;
                    &lt;xs:enumeration value="binding site"/&gt;
                    <code style="color:red">&lt;!-- &lt;xs:enumeration value="calcium-binding region"/&gt; --&gt;</code>
                    ...
                    <code style="color:red">&lt;!-- &lt;xs:enumeration value="metal ion-binding site"/&gt; --&gt;</code>
                    ...
                    <code style="color:red">&lt;!-- &lt;xs:enumeration value="nucleotide phosphate-binding region"/&gt; --&gt;</code>
                    ...
                &lt;/xs:restriction&gt;
            &lt;/xs:simpleType&gt;
        &lt;/xs:attribute&gt;
    ...
    &lt;/xs:complexType&gt;
    ...
    <code style="color:red">&lt;xs:complexType name="ligandType"&gt;
        &lt;xs:annotation&gt;
            &lt;xs:documentation&gt;Describes a ligand.&lt;/xs:documentation&gt;
        &lt;/xs:annotation&gt;
        &lt;xs:sequence&gt;
            &lt;xs:element name="name" type="xs:string"/&gt;
            &lt;xs:element name="dbReference" type="dbReferenceType" minOccurs="0"/&gt;
            &lt;xs:element name="label" type="xs:string" minOccurs="0"/&gt;
            &lt;xs:element name="note" type="xs:string" minOccurs="0"/&gt;
        &lt;/xs:sequence&gt;
    &lt;/xs:complexType&gt;

    &lt;xs:complexType name="ligandPartType"&gt;
        &lt;xs:annotation&gt;
            &lt;xs:documentation&gt;Describes a ligand part.&lt;/xs:documentation&gt;
        &lt;/xs:annotation&gt;
        &lt;xs:sequence&gt;
            &lt;xs:element name="name" type="xs:string"/&gt;
            &lt;xs:element name="dbReference" type="dbReferenceType" minOccurs="0"/&gt;
            &lt;xs:element name="label" type="xs:string" minOccurs="0"/&gt;
            &lt;xs:element name="note" type="xs:string" minOccurs="0"/&gt;
        &lt;/xs:sequence&gt;
    &lt;/xs:complexType&gt;</code>
</pre>

Example: [Q9H5X1](https://rest.uniprot.org/uniprotkb/Q9H5X1.xml)

Current format:

```
    <feature type="metal ion-binding site" description="Zinc 1; shared with dimeric partner">
      <location>
        <position position="89"/>
      </location>
    </feature>
    <feature type="metal ion-binding site" description="Zinc 2; shared with dimeric partner">
      <location>
        <position position="89"/>
      </location>
    </feature>
    <feature type="metal ion-binding site" description="Zinc 1; shared with dimeric partner">
      <location>
        <position position="123"/>
      </location>
    </feature>
    <feature type="metal ion-binding site" description="Zinc 2; shared with dimeric partner">
      <location>
        <position position="123"/>
      </location>
    </feature>
```

New format:

```
    <feature type="binding site">
      <location>
        <position position="89"/>
      </location>
      <ligand>
        <name>Zn(2+)</name>
        <dbReference type="ChEBI" id="CHEBI:29105"/>
        <label>1</label>
        <note>ligand shared between dimeric partners</note>
      </ligand>
    </feature>
    <feature type="binding site">
      <location>
        <position position="89"/>
      </location>
      <ligand>
        <name>Zn(2+)</name>
        <dbReference type="ChEBI" id="CHEBI:29105"/>
        <label>2</label>
        <note>ligand shared between dimeric partners</note>
      </ligand>
    </feature>
    <feature type="binding site">
      <location>
        <position position="123"/>
      </location>
      <ligand>
        <name>Zn(2+)</name>
        <dbReference type="ChEBI" id="CHEBI:29105"/>
        <label>1</label>
        <note>ligand shared between dimeric partners</note>
      </ligand>
    </feature>
    <feature type="binding site">
      <location>
        <position position="123"/>
      </location>
      <ligand>
        <name>Zn(2+)</name>
        <dbReference type="ChEBI" id="CHEBI:29105"/>
        <label>2</label>
        <note>ligand shared between dimeric partners</note>
      </ligand>
    </feature>
```

Example: [P39186](https://rest.uniprot.org/uniprotkb/P39186.xml)

Current format:

```
    <feature type="metal ion-binding site" description="Iron (heme C 1 axial ligand); via tele nitrogen">
      <location>
        <position position="79"/>
      </location>
    </feature>
    <feature type="metal ion-binding site" description="Iron (heme C 1 axial ligand); via tele nitrogen">
      <location>
        <position position="97"/>
      </location>
    </feature>
    <feature type="metal ion-binding site" description="Iron (heme C 2 axial ligand); via tele nitrogen">
      <location>
        <position position="114"/>
      </location>
    </feature>
    <feature type="metal ion-binding site" description="Iron (heme C 2 axial ligand); via tele nitrogen">
      <location>
        <position position="137"/>
      </location>
    </feature>
    <feature type="binding site" description="Heme C 1; covalent" evidence="2">
      <location>
        <position position="93"/>
      </location>
    </feature>
    <feature type="binding site" description="Heme C 1; covalent" evidence="2">
      <location>
        <position position="96"/>
      </location>
    </feature>
    <feature type="binding site" description="Heme C 2; covalent" evidence="2">
      <location>
        <position position="133"/>
      </location>
    </feature>
    <feature type="binding site" description="Heme C 2; covalent" evidence="2">
      <location>
        <position position="136"/>
      </location>
    </feature>
```

New format:

```
    <feature type="binding site" description="axial binding residue" evidence="2 5">
      <location>
        <position position="79"/>
      </location>
      <ligand>
        <name>heme c</name>
        <dbReference type="ChEBI" id="CHEBI:61717"/>
        <label>1</label>
      </ligand>
      <ligandPart>
        <name>Fe</name>
        <dbReference type="ChEBI" id="CHEBI:18248"/>
      </ligandPart>
    </feature>
    <feature type="binding site" description="covalent" evidence="2 5">
      <location>
        <position position="93"/>
      </location>
      <ligand>
        <name>heme c</name>
        <dbReference type="ChEBI" id="CHEBI:61717"/>
        <label>1</label>
      </ligand>
    </feature>
    <feature type="binding site" description="covalent" evidence="2 5">
      <location>
        <position position="96"/>
      </location>
      <ligand>
        <name>heme c</name>
        <dbReference type="ChEBI" id="CHEBI:61717"/>
        <label>1</label>
      </ligand>
    </feature>
    <feature type="binding site" description="axial binding residue" evidence="2 5">
      <location>
        <position position="97"/>
      </location>
      <ligand>
        <name>heme c</name>
        <dbReference type="ChEBI" id="CHEBI:61717"/>
        <label>1</label>
      </ligand>
      <ligandPart>
        <name>Fe</name>
        <dbReference type="ChEBI" id="CHEBI:18248"/>
      </ligandPart>
    </feature>
    <feature type="binding site" description="axial binding residue" evidence="2 5">
      <location>
        <position position="114"/>
      </location>
      <ligand>
        <name>heme c</name>
        <dbReference type="ChEBI" id="CHEBI:61717"/>
        <label>2</label>
      </ligand>
      <ligandPart>
        <name>Fe</name>
        <dbReference type="ChEBI" id="CHEBI:18248"/>
      </ligandPart>
    </feature>
    <feature type="binding site" description="covalent" evidence="2 5">
      <location>
        <position position="133"/>
      </location>
      <ligand>
        <name>heme c</name>
        <dbReference type="ChEBI" id="CHEBI:61717"/>
        <label>2</label>
      </ligand>
    </feature>
    <feature type="binding site" description="covalent" evidence="2 5">
      <location>
        <position position="136"/>
      </location>
      <ligand>
        <name>heme c</name>
        <dbReference type="ChEBI" id="CHEBI:61717"/>
        <label>2</label>
      </ligand>
    </feature>
    <feature type="binding site" description="axial binding residue" evidence="2 5">
      <location>
        <position position="137"/>
      </location>
      <ligand>
        <name>heme c</name>
        <dbReference type="ChEBI" id="CHEBI:61717"/>
        <label>2</label>
      </ligand>
      <ligandPart>
        <name>Fe</name>
        <dbReference type="ChEBI" id="CHEBI:18248"/>
      </ligandPart>
    </feature>
```

Example: [Q9H6S0](https://rest.uniprot.org/uniprotkb/Q9H6S0.xml)

Current format:

```
    <feature type="region of interest" description="N6-methyladenosine residue binding" evidence="3">
      <location>
        <begin position="1294"/>
        <end position="1296"/>
      </location>
    </feature>
    ...
    <feature type="binding site" description="N6-methyladenosine residue" evidence="2">
      <location>
        <position position="1310"/>
      </location>
    </feature>
    <feature type="binding site" description="N6-methyladenosine residue" evidence="2">
      <location>
        <position position="1360"/>
      </location>
    </feature>
```

New format:

```
    <feature type="binding site" evidence="3">
      <location>
        <begin position="1294"/>
        <end position="1296"/>
      </location>
      <ligand>
        <name>RNA</name>
        <dbReference type="ChEBI" id="CHEBI:33697"/>
      </ligand>
      <ligandPart>
        <name>N(6)-methyladenosine 5'-phosphate residue</name>
        <dbReference type="ChEBI" id="CHEBI:74449"/>
      </ligandPart>
    </feature>
    <feature type="binding site" evidence="2">
      <location>
        <position position="1310"/>
      </location>
      <ligand>
        <name>RNA</name>
        <dbReference type="ChEBI" id="CHEBI:33697"/>
      </ligand>
      <ligandPart>
        <name>N(6)-methyladenosine 5'-phosphate residue</name>
        <dbReference type="ChEBI" id="CHEBI:74449"/>
      </ligandPart>
    </feature>
    <feature type="binding site" evidence="2">
      <location>
        <position position="1360"/>
      </location>
      <ligand>
        <name>RNA</name>
        <dbReference type="ChEBI" id="CHEBI:33697"/>
      </ligand>
      <ligandPart>
        <name>N(6)-methyladenosine 5'-phosphate residue</name>
        <dbReference type="ChEBI" id="CHEBI:74449"/>
      </ligandPart>
    </feature>
```



#### RDF format

We are going to make the following changes to the [UniProt RDF schema ontology](https://ftp.uniprot.org/pub/databases/uniprotkb/current_release/rdf/core.owl) to standardize the description of a ligand, and optionally the bound part of the ligand, with the ChEBI ontology.

* We will deprecate the classes `Calcium_Binding_Annotation`, `Metal_Binding_Annotation` and `NP_Binding_Annotation`.
* We will introduce two new properties, `ligand` and `ligandPart`, whose `rdfs:domain` is the [`Binding_Site_Annotation`](http://purl.uniprot.org/core/Binding_Site_Annotation) class. The nature of a ligand or ligand part is described as one of:
  * an `rdfs:subClassOf` of the corresponding ChEBI class (when a ChEBI identifier is available)
  * a class identified by an entry URI fragment whose identifier is generated from the ligand (part) name (when no ChEBI identifier is available)
* A `partOf` statement is used to link a ligand part class to the ligand class that contains the part. As a consequence, the [`partOf`](http://purl.uniprot.org/core/partOf) property will loose its `rdfs:domain` and `rdfs:range`.
* The label and note of a ligand (_LigandLabel_, _LigandNote_) or ligand part (_LigandPartLabel_, _LigandPartNote_) are described at the corresponding class level with `rdfs:label` and `rdfs:comment` statements, respectively.
* The representation of the annotation _Note_ and the _Evidences_ remains unchanged.

In the examples below, the parts of the annotation whose structure has not changed (details of sequence range, evidences) are omitted.

Example: [Q9H5X1](https://rest.uniprot.org/uniprotkb/Q9H5X1.ttl)

Current format:

```
<Q9H5X1> rdf:type up:Protein ;
...
  up:annotation ...
    <Q9H5X1#SIP205C589B1B82C19D> ,
    <Q9H5X1#SIP0FDA08578DA645F1> ,
    <Q9H5X1#SIPF931DC9BFE3EE1EA> ,
    <Q9H5X1#SIP9FE49AAED1489740> ,
...
<Q9H5X1#SIP205C589B1B82C19D>
  rdf:type up:Metal_Binding_Annotation ;
  rdfs:comment "Zinc 1; shared with dimeric partner" ;
  up:range range:22862455408963886tt89tt89 .
...
<Q9H5X1#SIP0FDA08578DA645F1>
  rdf:type up:Metal_Binding_Annotation ;
  rdfs:comment "Zinc 2; shared with dimeric partner" ;
  up:range range:22862455408963886tt89tt89 .
<Q9H5X1#SIPF931DC9BFE3EE1EA>
  rdf:type up:Metal_Binding_Annotation ;
  rdfs:comment "Zinc 1; shared with dimeric partner" ;
  up:range range:22862455408963886tt123tt123 .
...
<Q9H5X1#SIP9FE49AAED1489740>
  rdf:type up:Metal_Binding_Annotation ;
  rdfs:comment "Zinc 2; shared with dimeric partner" ;
  up:range range:22862455408963886tt123tt123 .
```

New format:

```
<Q9H5X1> rdf:type up:Protein ;
...
  up:annotation ...
    <Q9H5X1#SIPEF929039F510ECEF> ,
    <Q9H5X1#SIP920EDE1AF7D0C789> ,
    <Q9H5X1#SIP72E42A3FB2BD4B9A> ,
    <Q9H5X1#SIP34635D3021CE14FA> ,
...
<Q9H5X1#SIPEF929039F510ECEF>
  rdf:type up:Binding_Site_Annotation ;
  up:ligand <Q9H5X1#SIPA9D42F70EC978DA2> ;
  up:range range:22862455408963886tt89tt89 .
...
<Q9H5X1#SIP920EDE1AF7D0C789>
  rdf:type up:Binding_Site_Annotation ;
  up:ligand <Q9H5X1#SIP2113E97BF945072A> ;
  up:range range:22862455408963886tt89tt89 .
<Q9H5X1#SIP72E42A3FB2BD4B9A>
  rdf:type up:Binding_Site_Annotation ;
  up:ligand <Q9H5X1#SIPA9D42F70EC978DA2> ;
  up:range range:22862455408963886tt123tt123 .
...
<Q9H5X1#SIP34635D3021CE14FA>
  rdf:type up:Binding_Site_Annotation ;
  up:ligand <Q9H5X1#SIP2113E97BF945072A> ;
  up:range range:22862455408963886tt123tt123 .
...
<Q9H5X1#SIPA9D42F70EC978DA2>
  rdfs:subClassOf <http://purl.obolibrary.org/obo/CHEBI_29105> ;
  rdfs:label "1" ;
  rdfs:comment "ligand shared between dimeric partners" .
<Q9H5X1#SIP2113E97BF945072A>
  rdfs:subClassOf <http://purl.obolibrary.org/obo/CHEBI_29105> ;
  rdfs:label "2" ;
  rdfs:comment "ligand shared between dimeric partners" .
```

Example: [P39186](https://rest.uniprot.org/uniprotkb/P39186.ttl)

Current format:

```
<P39186> rdf:type up:Protein ;
...
  up:annotation ...
    <P39186#SIP2FA351DB0B3C2F16> ,
    <P39186#SIP68C53D2ADFC188FB> ,
    <P39186#SIP293BA29AFBE6705D> ,
    <P39186#SIP04086D3B0200EFDB> ,
    <P39186#SIP421DBD60EE668E9A> ,
    <P39186#SIPBE78F7D7D1DFDB96> ,
    <P39186#SIPF42DD8F9E97D4C04> ,
    <P39186#SIP67D0B11099583DF4> ,
...
<P39186#SIP2FA351DB0B3C2F16>
  rdf:type up:Metal_Binding_Annotation ;
  rdfs:comment "Iron (heme C 1 axial ligand); via tele nitrogen" ;
  up:range range:22574318868772398tt79tt79 .
...
<P39186#SIP68C53D2ADFC188FB>
  rdf:type up:Metal_Binding_Annotation ;
  rdfs:comment "Iron (heme C 1 axial ligand); via tele nitrogen" ;
  up:range range:22574318868772398tt97tt97 .
...
<P39186#SIP293BA29AFBE6705D>
  rdf:type up:Metal_Binding_Annotation ;
  rdfs:comment "Iron (heme C 2 axial ligand); via tele nitrogen" ;
  up:range range:22574318868772398tt114tt114 .
...
<P39186#SIP04086D3B0200EFDB>
  rdf:type up:Metal_Binding_Annotation ;
  rdfs:comment "Iron (heme C 2 axial ligand); via tele nitrogen" ;
  up:range range:22574318868772398tt137tt137 .
...
<P39186#SIP421DBD60EE668E9A>
  rdf:type up:Binding_Site_Annotation ;
  rdfs:comment "Heme C 1; covalent" ;
  up:range range:22574318868772398tt93tt93 .
...
<P39186#SIPBE78F7D7D1DFDB96>
  rdf:type up:Binding_Site_Annotation ;
  rdfs:comment "Heme C 1; covalent" ;
  up:range range:22574318868772398tt96tt96 .
...
<P39186#SIPF42DD8F9E97D4C04>
  rdf:type up:Binding_Site_Annotation ;
  rdfs:comment "Heme C 2; covalent" ;
  up:range range:22574318868772398tt133tt133 .
...
<P39186#SIP67D0B11099583DF4>
  rdf:type up:Binding_Site_Annotation ;
  rdfs:comment "Heme C 2; covalent" ;
  up:range range:22574318868772398tt136tt136 .
```

New format:

```
<P39186> rdf:type up:Protein ;
...
  up:annotation ...
    <P39186#SIP6B05083539025B03> ,
    <P39186#SIP26EC788A934C8F47> ,
    <P39186#SIPE6A28D6EA4C9FD5D> ,
    <P39186#SIPFBD274DC3C6C2D4D> ,
    <P39186#SIP35F10B423DCD5ABF> ,
    <P39186#SIP2B84A319ABAB6D10> ,
    <P39186#SIP3DF7879BD48FFB15> ,
    <P39186#SIP4B946529653D1444> ,
...
<P39186#SIP6B05083539025B03>
  rdf:type up:Binding_Site_Annotation ;
  rdfs:comment "axial binding residue" ;
  up:ligand <P39186#SIP03157F908F4B7F18> ;
  up:ligandPart <P39186#SIP85C37483D3E0B42A> ;
  up:range range:22574318868772398tt79tt79 .
...
<P39186#SIP26EC788A934C8F47>
  rdf:type up:Binding_Site_Annotation ;
  rdfs:comment "covalent" ;
  up:ligand <P39186#SIP03157F908F4B7F18> ;
  up:range range:22574318868772398tt93tt93 .
...
<P39186#SIPE6A28D6EA4C9FD5D>
  rdf:type up:Binding_Site_Annotation ;
  rdfs:comment "covalent" ;
  up:ligand <P39186#SIP03157F908F4B7F18> ;
  up:range range:22574318868772398tt96tt96 .
...
<P39186#SIPFBD274DC3C6C2D4D>
  rdf:type up:Binding_Site_Annotation ;
  rdfs:comment "axial binding residue" ;
  up:ligand <P39186#SIP03157F908F4B7F18> ;
  up:ligandPart <P39186#SIP85C37483D3E0B42A> ;
  up:range range:22574318868772398tt97tt97 .
...
<P39186#SIP35F10B423DCD5ABF>
  rdf:type up:Binding_Site_Annotation ;
  rdfs:comment "axial binding residue" ;
  up:ligand <P39186#SIP997F95171519AEFE> ;
  up:ligandPart <P39186#SIP428C6123B1B272B9> ;
  up:range range:22574318868772398tt114tt114 .
...
<P39186#SIP2B84A319ABAB6D10>
  rdf:type up:Binding_Site_Annotation ;
  rdfs:comment "covalent" ;
  up:ligand <P39186#SIP997F95171519AEFE> ;
  up:range range:22574318868772398tt133tt133 .
...
<P39186#SIP3DF7879BD48FFB15>
  rdf:type up:Binding_Site_Annotation ;
  rdfs:comment "covalent" ;
  up:ligand <P39186#SIP997F95171519AEFE> ;
  up:range range:22574318868772398tt136tt136 .
...
<P39186#SIP4B946529653D1444>
  rdf:type up:Binding_Site_Annotation ;
  rdfs:comment "axial binding residue" ;
  up:ligand <P39186#SIP997F95171519AEFE> ;
  up:ligandPart <P39186#SIP428C6123B1B272B9> ;
  up:range range:22574318868772398tt137tt137 .
...
<P39186#SIP03157F908F4B7F18>
  rdfs:subClassOf <http://purl.obolibrary.org/obo/CHEBI_61717> ;
  rdfs:label "1" .
<P39186#SIP85C37483D3E0B42A>
  rdfs:subClassOf <http://purl.obolibrary.org/obo/CHEBI_18248> ;
  up:partOf <P39186#SIP03157F908F4B7F18> .
<P39186#SIP997F95171519AEFE>
  rdfs:subClassOf <http://purl.obolibrary.org/obo/CHEBI_61717> ;
  rdfs:label "2" .
<P39186#SIP428C6123B1B272B9>
  rdfs:subClassOf <http://purl.obolibrary.org/obo/CHEBI_18248> ;
  up:partOf <P39186#SIP997F95171519AEFE> .
```

Example: [Q9H6S0](https://rest.uniprot.org/uniprotkb/Q9H6S0.ttl)

Current format:

```
<Q9H6S0> rdf:type up:Protein ;
...
  up:annotation ...
    <Q9H6S0#SIP1A82C4FF56746BB8> ,
...
    <Q9H6S0#SIPBD815A286DC38CC5> ,
    <Q9H6S0#SIPC5465EB9289C0B15> ,
...
<Q9H6S0#SIP1A82C4FF56746BB8>
  rdf:type up:Region_Annotation ;
  rdfs:comment "N6-methyladenosine residue binding" ;
  up:range range:22862455425413166tt1294tt1296 .
...
<Q9H6S0#SIPBD815A286DC38CC5>
  rdf:type up:Binding_Site_Annotation ;
  rdfs:comment "N6-methyladenosine residue" ;
  up:range range:22862455425413166tt1310tt1310 .
...
<Q9H6S0#SIPC5465EB9289C0B15>
  rdf:type up:Binding_Site_Annotation ;
  rdfs:comment "N6-methyladenosine residue" ;
  up:range range:22862455425413166tt1360tt1360 .
```

New format:

```
<Q9H6S0> rdf:type up:Protein ;
...
  up:annotation ...
    <Q9H6S0#SIP422D37614A6D5721> ,
    <Q9H6S0#SIP181E7990DC5C18D8> ,
    <Q9H6S0#SIP21050F3BB73E81A2> ,
...
<Q9H6S0#SIP422D37614A6D5721>
  rdf:type up:Binding_Site_Annotation ;
  up:ligand <Q9H6S0#SIPC276DB5E970331C9> ;
  up:ligandPart <Q9H6S0#SIP93E43149D18FF63B> ;
  up:range range:22862455425413166tt1294tt1296 .
...
<Q9H6S0#SIP181E7990DC5C18D8>
  rdf:type up:Binding_Site_Annotation ;
  up:ligand <Q9H6S0#SIPC276DB5E970331C9> ;
  up:ligandPart <Q9H6S0#SIP93E43149D18FF63B> ;
  up:range range:22862455425413166tt1310tt1310 .
...
<Q9H6S0#SIP21050F3BB73E81A2>
  rdf:type up:Binding_Site_Annotation ;
  up:ligand <Q9H6S0#SIPC276DB5E970331C9> ;
  up:ligandPart <Q9H6S0#SIP93E43149D18FF63B> ;
  up:range range:22862455425413166tt1360tt1360 .
...
<Q9H6S0#SIPC276DB5E970331C9>
  rdfs:subClassOf <http://purl.obolibrary.org/obo/CHEBI_33697> .
<Q9H6S0#SIP93E43149D18FF63B>
  rdfs:subClassOf <http://purl.obolibrary.org/obo/CHEBI_74449> ;
  up:partOf <Q9H6S0#SIPC276DB5E970331C9> .
```
