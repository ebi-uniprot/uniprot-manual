---
title: Gene Ontology (GO)
type: help
categories: Website,help
---

## Overview

The [Gene Ontology (GO)](https://geneontology.org/docs/ontology-documentation/) is a collaborative effort to provide structured, standardized descriptions of gene products (protein or ncRNA) across biological databases.

GO describes biological knowledge with respect to three aspects:

- Molecular function: activities performed by gene products (e.g. enzymatic activity).
- Biological process: biological modules or programs (e.g. cell cycle or citric acid cycle).
- Cellular component: location within cells (e.g. nucleus or ribosome).

[A variety of groups](https://geneontology.org/docs/annotation-contributors/), including UniProtKB curators, annotate gene products with GO terms, resulting in consistent and computationally tractable descriptions of gene products across biological databases.  
Note that many UniProtKB subcellular locations and keywords have been mapped to GO terms to allow an automatic assignment of the corresponding GO terms. While the original UniProtKB [subcellular locations](https://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/docs/subcell.txt) and [keywords](https://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/docs/keywlist.txt) are curated in UniProtKB/Swiss-Prot, their automatically mapped GO term equivalents will have the evidence type "Inferred from electronic annotation".

## Where to find Gene Ontology annotations in UniProt

In UniProt, GO annotations from all three aspects are displayed in the 'Function' section of protein entry pages, and annotated GO terms from the 'Cellular component' category can additionally be accessed in the 'Subcellular location' section. GO annotations are displayed in tabs;

### GO (standard) annotations

The ‘GO annotations’ tab is displayed by default and shows an annotation table with one annotation per row for the protein. In this view, the group that created the annotation is shown as the 'Source', and a click on this evidence tag will display details of the [supporting evidence](https://www.uniprot.org/help/evidences#evidence-types-used-for-go-annotations). Where available, a link to a supporting publication is provided.

### GO-CAMs

If data is available for that protein a second tab can be found in the ‘Function’ section of the protein entry labeled ‘GO-CAM’. This tab will display GO causal activity models ([GO-CAMs](https://geneontology.org/docs/gocam-overview/)) to which the protein has been annotated. In GO-CAMs, multiple GO annotations are linked, using relations from the [Relations Ontology](https://geneontology.org/docs/ontology-relations/), into an integrated model of a biological system. GO-CAMs link gene product activities to processes and components to provide context, and to one another to represent pathways. GO-CAMs also allow for specification of chemical substrates or ligands that may be beyond the scope of GO terms.

Only GO-CAM models that have been curated by UniProt curators are displayed to maintain consistency across the database. If a protein does not have an annotated GO-CAM model then a message will display this is in the tab once it has performed a search in https://geneontology.org.
