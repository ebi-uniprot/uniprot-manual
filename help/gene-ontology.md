---
title: Gene Ontology (GO)
type: help
categories: Website,help
---

## Overview

The [Gene Ontology (GO)](https://geneontology.org/docs/ontology-documentation/) knowledgebase is a collaborative effort to provide consistent descriptions of gene products (protein or ncRNA) across different databases.

GO maintains three ontologies (structured, controlled vocabularies) that describe biological knowledge with respect to three aspects:
Molecular function (single step activities, such as an enzymatic or receptor activity).
Biological process (genetically-encoded biological modules or programs, such as the cell cycle or citric acid cycle).
Cellular component (localizations, such as the nucleus or ribosome)

[A variety of groups](https://geneontology.org/docs/annotation-contributors/), including UniProtKB curators, apply GO terms to gene products ("annotation") resulting in consistent and computationally tractable descriptions of gene products across biological databases.
Note that many UniProtKB [subcellular locations](https://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/docs/subcell.txt) and [keywords](https://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/docs/keywlist.txt) have been mapped to GO terms to allow an automatic assignment of the corresponding GO terms. While the original UniProtKB subcellular locations and keywords are curated in UniProtKB/Swiss-Prot, their automatically mapped GO term equivalents will have the evidence type "Inferred from electronic annotation".

## Where to find Gene Ontology annotations in UniProt

### GO annotations

In UniProt, GO annotations from all three aspects are displayed in the 'Function' section of protein entry pages, and annotated GO terms from the 'Cellular component' category can additionally be accessed in the 'Subcellular location' section. Two representations are available for viewing GO annotations in the ‘Function’ section of the protein entry page; standard annotation tables and GO-CAMs. The ‘GO annotations’ tab is displayed by default and shows an annotation table with one annotation per row for the protein. In this view, the group that created the annotation is shown as the 'Source', and a click on this evidence tag will display details of the [supporting evidence](https://www.uniprot.org/help/evidences#evidence-types-used-for-go-annotations). Where available, a link to a supporting publication is provided.

### GO-CAMs

The second GO-CAM tab shows GO causal activity models ([GO-CAMs](https://geneontology.org/docs/gocam-overview/)) to which the protein has been annotated. In GO-CAMs, multiple GO annotations are linked, using relations from the [Relations Ontology](https://geneontology.org/docs/ontology-relations/), into an integrated model of a biological system. GO-CAMs link gene product activities to processes and components to provide context, and to one another to represent pathways. GO-CAMs also allow for specification of chemical substrates or ligands that may be beyond the scope of GO terms.

Only GO-CAM models that have been curated by UniProt curators are displayed to maintain consistency across the database.
