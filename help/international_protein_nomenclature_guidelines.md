---
title: International Protein Nomenclature Guidelines
type: help
categories: Biocuration,Nomenclature,help
---

# Mission Statement

These guidelines have been produced jointly by the European Bioinformatics Institute
(EMBL-EBI), the National Center for Biotechnology Information (NCBI), the Protein
Information Resource (PIR) and the Swiss Institute for Bioinformatics (SIB) and are intended
for use by anyone who wants to name a protein to promote consistency in protein naming
across databases, which aids data retrieval and improves communication.

## Table of contents
1. Introduction
2. Formats for protein names
   - A. Language
   - B. Abbrviations and symbols
   - C. Punctuation
   - D. Notation
   - E. Style and format
   - F. Word useage
3. Choosing protein names
   - A. Sources of protein name annotation
   - B. Naming proceedure for specific cases
  
## 1. Introduction 
Consistent protein nomenclature is indispensable for communication, literature searching
and entry retrieval. A good protein name is one which is unique, unambiguous, can be
attributed to orthologs from other species and follows official gene nomenclature where
applicable. The process of associating a name with a protein sequence has various
components: sequence function identification/prediction, choosing a name and applying
formatting. This document provides guidelines on naming choices and universal formatting.
This does not include best practices on methods to be used for sequence function
identification/prediction.

## 2. Formats for protein names
### A. Language 
- Use American spelling, not British spelling
  - uncharacterized protein not uncharacterised protein
  - hemoglobin not haemoglobin
- Use protein names ending in 'in' (not 'ine')
  - maurocalcin not maurocalcine
- Avoid diacritics such as accents, umlauts etc.
  - protein spatzle 5 not protein spätzle 5
- Avoid pluralization for names based on domain and repeat content
  - ankyrin repeat-containing protein not ankyrin repeats-containing protein
- Avoid common words
  - Avoid naming proteins with common words which makes querying difficult e.g. avoid
names such as ‘protein IMPACT’.
- Avoid duplication
  - Check if the proposed name for a newly discovered protein is already used for a
different protein.
### B. Abbreviations and symbols
- Avoid using abbreviations as the complete name
  - acyl carrier protein not ACP
- An abbreviation may be part of a protein name
  - (3R)-hydroxymyristoyl-ACP dehydratase
  - See below for a list of standard scientific abbreviations.
- Protein name based on a protein symbol (PS) or gene symbol (GS) <br>
  Protein and gene symbols should use the same abbreviation. Some gene and protein
symbols are easily recognized by database users in certain research communities and
can be used as part of a protein name to provide specification and aid data retrieval.
  - Prokaryote symbol guidelines
    - A protein symbol is most commonly used in prokaryote protein names in combination with a functional protein name.
    - The first letter of a protein symbol is capitalized for prokaryotes e.g. RecA
    - In rare occurrences when there is no functional protein name, the format "protein <PS>" may be used, not "<PS> protein".
    - Example: recombinase RecA
  - Eukaryote symbol guidelines
    - A gene symbol is commonly used in eukaryote protein names in combination with a functional protein name.
    - Capitalization conventions of gene symbols differ between organism communities and this is reflected in the casing of gene symbols used as part of eukaryotic protein names. For vertebrates, use an all uppercase gene symbol in a protein name. For non-vertebrate eukaryotes, follow the gene casing conventions of the species in question.
    - In the case of conserved genes, if there is no known gene symbol in use in the species already, a known orthologous gene symbol from a species where the symbol was originally defined may be used.
    - In rare occurrences when there is no functional protein name, the format “protein <GS>” may be used, not “<GS> protein”.
    - Examples:
      - Human: tyrosine-protein kinase ABL1
      - Mouse: tyrosine-protein kinase ABL1
      - C.elegans: tyrosine-protein kinase abl-1
      - D.melanogaster: tyrosine-protein kinase Abl
      - S.cerevisiae: recombinase RAD51
      - S.pombe: recombinase rad51
  -




