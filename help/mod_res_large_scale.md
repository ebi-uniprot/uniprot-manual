---
title: Large scale modified residue
type: help
categories: PTM_processing
---

In addition to curated [Post-translational modification](https://www.uniprot.org/help/post-translational_modification) (PTM) data which is also included in the downloadable versions of our data, some entries on our website also include dynamically added large-scale PTM data. These originate from large-scale mass-spectrometry (MS) datasets, which have been reanalyzed via the PTMeXchange project. This project facilitates confidence scoring of PTM sites across multiple datasets. The confidence score reflects the strength of the [evidence](https://www.uniprot.org/help/evidences) for modifications at that site. 

Example: [B9FXV5](https://www.uniprot.org/uniprotkb/B9FXV5/entry#ptm_processing)

# Where does the data come from?

The data comes from a refined set of large-scale phosphoproteomic datasets available in the [PRIDE database](https://www.ebi.ac.uk/pride/). The links to each source dataset can be found in the expandable “evidence tag” section for each PTM, next to the modification name in the ‘Description’ column of the table. In addition, links to PeptideAtlas species-specific phosphoproteome builds are available.

# How can I access this data in UniProt?

The data is viewable in multiple formats, via the [UniProt Proteins API (Proteomics PTM section)](https://www.ebi.ac.uk/proteins/api/doc/), via the [protein entry page](https://www.uniprot.org/help/explore_uniprotkb_entry) under section [PTM/Processing](https://www.uniprot.org/help/ptm_processing_section) (e.g. [B9FXV5](https://www.uniprot.org/uniprotkb/B9FXV5/entry#ptm_processing)) and in the interactive Feature Viewer (planned). Links to original source datasets in PRIDE are provided for users to explore the data in more detail. Links to reanalyzed source datasets in [PRIDE](https://www.ebi.ac.uk/pride/) will be provided in the future.


# Confidence score

## How is the score calculated?
Source MS data have been re-processed with strict statistical control at the level of the peptide-spectrum match (PSM) and then at the level of site localization, using “decoy” amino acids to verify and control for incorrect identification of modification sites, using methods described in [Method for Independent Estimation of the False Localization Rate for Phosphoproteomics](https://pubs.acs.org/doi/full/10.1021/acs.jproteome.1c00827).

Observed PTM sites are ranked by a probability of detection, calculated as follows. The pipeline first models the probability *p1* that a peptide sequence with modifications (peptidoform) has been identified, then creates an orthogonal probability *p2*, that the exact site has been correctly localized on the peptide. The “final probability” is derived by multiplying *p1* by *p2*. Sites are ranked by final probability and then thresholded by site-level false discovery rate (or false localization rate, FLR). The FLR is calculated by summing the matches to decoy amino acids in the ranked list (modelling false positives), normalizing for the ratio of occurrence of the decoy amino acid (Ala) to target amino acids (Ser, Thr and Tyr for phosphorylation), and dividing by the count of rows. Results per data set are then thresholded at 1% and 5% FLR. Meta-analysis and final classification is determined by the simple gold/silver/bronze criteria, as described below.

## What is the gold/silver/bronze criterion?

A modified residue is classified into three categories based on its false localization rate (FLR) across multiple datasets.

| Category | Criteria                                      |
|----------|-----------------------------------------------|
| Gold     | Identified in multiple datasets at ≤1% FLR    |
| Silver   | Identified in a single dataset at ≤1% FLR     |
| Bronze   | Identified in one or more datasets at ≤5% FLR |
