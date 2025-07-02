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
  - uncharacterized protein **not** uncharacterised protein
  - hemoglobin **not** haemoglobin
- Use protein names ending in 'in' (not 'ine')
  - maurocalcin **not** maurocalcine
- Avoid diacritics such as accents, umlauts etc.
  - protein spatzle 5 **not** protein spätzle 5
- Avoid pluralization for names based on domain and repeat content
  - ankyrin repeat-containing protein **not** ankyrin repeats-containing protein
- Avoid common words
  - Avoid naming proteins with common words which makes querying difficult e.g. avoid
names such as ‘protein IMPACT’.
- Avoid duplication
  - Check if the proposed name for a newly discovered protein is already used for a
different protein.
### B. Abbreviations and symbols
- Avoid using abbreviations as the complete name
  - acyl carrier protein **not** ACP
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
- Prime symbol (')
  - Use to indicate the cleavage location on a substrate and to distinguish different subunits with the same notation.
  - Use the single quote character (not the backtick) for the prime symbol.
  - Examples:
    - H(+)-transporting V0 sector ATPase subunit c'
    - 5'-nucleotidase **not** 5-prime-nucleotidase
    - coatomer subunit beta' **not** coatomer subunit beta-prime
- Chemical symbols may be part of a protein name
  - For elements with a single valence type, use the full element name with no valence indicated.
  - For elements that have variable types of valency, use the chemical symbol for the element followed by the valence in parenthesis.
  - Examples:
    - sodium/lithium-exporting P-type ATPase **not** Na(+)/Li(+)-exporting Ptype ATPase
    - magnesium transporter **not** Mg(2+) transporter
    - Fe(3+)/Cu(2+)-chelate reductase **not** ferric/cupric-chelate reductase **or not** Fe(III)/Cu(II)-chelate reductase
- Standard scientific abbreviations may be part of a protein name
  - Deoxyribonucleic acid: DNA, cDNA, dsDNA, ssDNA
  - Ribonucleic acid: dsRNA, mRNA, miRNA, piRNA, siRNA, snRNA, snoRNA, ssRNA, tRNA, tmRNA, rRNA
  - Mono-, di-, tri-nucleoside phosphates: dAMP, dCMP, dGMP, dTMP, dADP, dCDP, dGDP, dTDP, dATP, dCTP, dGTP, dTTP
  - Cofactors: FAD, FMN, NAD, NADP
  - Classes for transporters that inform about structure (e.g. ABC, MFS, RND, MATE, SMR) rather than substrate (e.g. **not** MDR)
  - Example: rRNA methyltransferase **not** ribosomal RNA methyltransferase

### C. Punctuation
- **Slash**
  - Do not use a back slash: ‘\’.
  - For separating multiple domains or functions, the forward slash ‘/’ or the word ‘and’ may be used.
  - Examples:
    - adenylyltransferase/ADP-heptose synthase cyclohydrolase **not** adenylyltransferase\ADP-heptose synthase cyclohydrolase
    - WD repeat and FYVE domain-containing protein 3 **not** WD repeat\FYVE domain-containing protein 3
<br>

- **Hyphen**
   - **Compound adjective**: a hyphen should be used to form compound modifiers (i.e. two or more words that are acting as a single modifier for a noun)<br>
Examples:
     - Ras GTPase-activating protein **not** Ras GTPase activating protein
     - secretin-binding protein **not** secretin binding protein
     - pyrophosphate-dependent phosphofructokinase **not** pyrophosphate dependent phosphofructokinase
   - **Examples of common modifiers:** activated, activating, adapting, adding,
amplified, anchored, anchoring, antagonizing, associated, associating,
attracting, binding, blocking, bound, branching, bridging, bundling, capping,
complementing, concentrating, conjugating, containing, controlled,
controlling, converting, coupled, coupling, decapping, degrading, dependent,
depolymerizing, derepressing, derived, deriving, destabilizing, docking,
editing, enhanced, enhancing, enriched, exposed, flanking, forming, gated,
grabbing, harvesting, independent, induced, inducible, inducing, inhibited,
inhibiting, insensitive, interacting, laying, like, linked, linking, metabolizing,
modifying, modulating, polymerizing, potentiating, preventing, processing,
promoting, recognizing, recruited, recruiting, regulated, regulating, related,
released, releasing, remodeling, removing, repressing, required, requiring,
resistant, responsive, rich, ripening, scaffolding, sensing, sensitive, signaling,
specific, splicing, spreading, stabilized, stabilizing, stacking, stimulated,
stimulating, structuring, sulfating, suppressing, trafficking, transformed,
transforming, transporting
   - **More than one domain/repeat in a name:**  if there is more than one
domain/repeat, only use a hyphen for the last item preceding "containing",
even though this violates conventional grammar.<br>
Example: ankyrin repeat and SAM domain-containing protein 6 **not** ankyrin
repeat- and SAM domain-containing protein 6
<br>

-  **Avoid apostrophes, periods, commas and other undesirable punctuation**
   - Remove trailing periods from names.
   - Avoid use of commas except when their usage is part of accepted chemical names.<br>
Example: SGT2 family TPR domain-containing protein **not** TPR repeat protein, SGT2 family<br>
  **Exception example**: 3-hydroxy-16-methoxy-2,3-dihydrotabersonine Nmethyltransferase
   - Avoid the semi-colon ";" or colon “:” except when it is part of an enzyme name.<br>
Example: type I cuticular keratin Ha8 **not** “Keratin, type I cuticular Ha8; Hair keratin,type I Ha8; Keratin-38; K38” <br>
**Exception example:** phospholipid:diacylglycerol acyltransferase
   - Avoid the percentage sign ‘%’
   - Avoid the at sign '@’
   - Avoid the equal sign ‘=’<br>
Example: guanine nucleotide-binding protein G(t) subunit alpha-3 **not** gustducin:SUBUNIT=alpha
<br>

-  **Avoid autocorrection of protein names**
   - Data submitters should not let Microsoft Excel, Word, Outlook, or any other utility with format interpolation and spelling autocorrection touch any protein names, especially those with quotes and double-hyphens.













