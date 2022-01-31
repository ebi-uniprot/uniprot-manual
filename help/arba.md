---
title: Automatic annotation using ARBA
categories: UniProtKB,Automatic_annotation,help
---

UniProt's [Automatic Annotation pipeline](http://www.uniprot.org/help/automatic%5Fannotation) enhances the unreviewed records in UniProtKB by enriching them with automatic classification and annotation.

The Association-Rule-Based Annotator (ARBA) is one of the contributors to this pipeline. It is a multiclass learning system trained on expertly annotated entries in UniProtKB/Swiss-Prot. ARBA uses [rule mining techniques](https://link.springer.com/protocol/10.1007%2F978-1-4939-7027-8%5F12) to generate concise annotation models with the highest representativeness and coverage for annotation, based on the properties of [InterPro](http://www.ebi.ac.uk/interpro) group membership and taxonomy. ARBA employs a data exclusion set that censors data not suitable for computational annotation (such as specific biophysical or chemical properties) and generates human-readable rules for each release.

ARBA rules can annotate protein properties such as function, catalytic activity, pathway membership, subcellular location and protein names but feature predictions are currently excluded. Generating rules on-the-fly in this way allows rules to evolve along with the content of UniProtKB with little or no manual intervention. It also provides a constant supply of potential 'seed rules' which can be further developed by the curators into [UniRule](http://www.uniprot.org/help/unirule) rules.

### ARBA based evidence for UniProtKB annotation (example: [Q3TWF3](https://www.uniprot.org/uniprotkb/Q3TWF3) )

UniProtKB entries contain [evidence tags](http://www.uniprot.org/help/evidences) that describe the provenance of a given annotation and provide links to a reference where applicable. When an annotation is added to an entry based on an automatic annotation ARBA rule, the evidence tag indicates this:

<figure><img src="https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/arba-8.png" style="width:80.0%" alt="ARBA evidence tag" /><figcaption aria-hidden="true">ARBA evidence tag</figcaption></figure>

When you click on the tag, you see a link to the relevant ARBA annotation rule:

<figure><img src="https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/arba-9.png" style="width:80.0%" alt="Link to ARBA annotation rule" /><figcaption aria-hidden="true">Link to ARBA annotation rule</figcaption></figure>

### Searching ARBA rules

The ARBA dataset is available from the [UniProt](https://www.uniprot.org/) website. In order to search the dataset to view rules of interest, click on the dropdown next to the search box and select 'ARBA'. Now enter a search term or rule ID. You can also use the advanced search to build your query.

![UniProt namespace dropdown, including ARBA](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/arba-10.png)

### Exploring the ARBA rule pages

[Example](http://www.uniprot.org/arba/ARBA00004016)

An ARBA rule page contains the unique ARBA ID, a link to the UniProtKB entries annotated by the rule, and the full rule with its conditions and annotations. A rule consists of a set of conditions and corresponding annotations that apply to a protein entry if the conditions are true.

<figure><img src="https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/arba-11.png" style="width:80.0%" alt="ARBA rule page ARBA00004016" /><figcaption aria-hidden="true">ARBA rule page ARBA00004016</figcaption></figure>

Conditions are listed on the left hand side of the rule page and annotations are on the right hand side. If a condition holds true then the corresponding annotation is applied. An ARBA rule only ever applies one annotation but can have multiple condition sets that lead to this annotation. Clicking on the conditions highlights the annotation and vice versa.
