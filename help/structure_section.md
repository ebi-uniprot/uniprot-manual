---
title: Structure annotation in UniProt
type: help
categories: 3D_structure,manual
---

## Why are protein structures informative?

Protein structures can impart a wealth of information, for example they can:

- Inform the architecture of multimeric complexes, including the interactions with other proteins, nucleic acids, carbohydrates and lipids
- Reveal the topological arrangement and transmembrane domains
- Prove the existence of specific protein folds and provide insights on protein folding
- Confirm and provide a structural explanation of a protein’s functional role
- Provide residual-level details that are not available from other techniques, including:
     - Interactions with ligands and active sites
     - Post-translational modifications
     - Pathogenic mutations

Related keyword: [3D-structure](https://www.uniprot.org/keywords/KW-0002)

## Structure Section

This section within the protein entry page provides a list of tertiary structures available for proteins from [cross-referenced databases](https://www.uniprot.org/database?facets=category_exact%3A3D%20structure%20databases&query=%2A).<br>
This includes experimentally determined structures from [PDB](https://www.ebi.ac.uk/pdbe/) and predicted structural models from [AlphaFold](https://alphafold.ebi.ac.uk/). <br>
Experimentally determined structures can be fragments or variants of the protein sequence shown in a UniProt record and can include ligands, solvents, or other interacting partners. The most common experimental methods for structure determination are X-ray crystallography (X-ray), Cryo-Electron Microscopy (EM) and Nuclear Magnetic Resonance Spectroscopy (NMR).<br>

## AlphaFold structural models

A 3D structural model from AlphaFold2 prediction is always presented as a full-length monomeric protein based on the protein canonical sequence, without any ligands or interacting partners. These structural models are shown with a per-residue confidence score (pLDDT) that indicates the confidence of the prediction. Confidence is color-coded in the 3D structural viewer of a protein entry, and in the AlphaFold confidence track of the protein feature viewer, to indicate the confidence of the prediction along the amino acid sequence. <br>
Example: [P05067](https://www.uniprot.org/uniprotkb/P05067/feature-viewer). <br>
AlphaFold models for proteins longer than 2,700 (UniProtKB/SwissProt entries) or 1,280 (UniProtKB/TrEMBL entries) amino acids are not available. It is possible that the canonical sequence could have been updated since the AlphaFold2 prediction was made and therefore the 3D-structural prediction may not be based on the latest canonical sequence. If this is the case then a warning will be displayed. 



## Description of structure table contents

|                                                                                 |                                                                                 |
|:--------------------------------------------------------------------------------|:--------------------------------------------------------------------------------|
| **Subsection**                                                                  | **Content**                                                                     |
| Source                                                                          | The database where this structure can be found.                                 |
| Identifier                                                                      | The identifier used in the source database                                      |
| Method                                                                          | Experimental method for structure determination (such as X-ray, EM or NMR) or Predicted.        |
| Resolution                                                                      | Effective resolution of the refinement by X-ray or EM. |
| Chain                                                                           | A structure may consist of multiple entities (including proteins and nucleic acids) and each copy of an entity is assigned to a chain identifier in PDB. Not all the chains are shown for large structures, please refer to the PDB website for the full mapping.|
| Positions                                                                       |The positions here indicate the construct used to determine the structure. This may vary from the observable sequence in the structure. The same residual-level mapping is used in the [SIFTS project](https://www.ebi.ac.uk/pdbe/docs/sifts/).|

  
## Structure coverage

Multiple experimentally determined structures may be available for one protein (see the [PDB cross-reference help page](https://www.uniprot.org/help/multiple_pdb_xrefs)). These structures may cover different ranges of the sequence, depending on the experimental method and the construct used to determine the structure. The sequence coverage of different structures are shown in the PDBe 3D structure coverage track of the protein feature viewer.<br>
Example: [Q9H165](https://www.uniprot.org/uniprotkb/Q9H165/feature-viewer). 

## AlphaMissense prediction of genetic variation consequence
[AlphaFold missense](https://alphamissense.hegelab.org/) is a machine-learning derived prediction of the likelihood of a human missense genetic variant being pathogenic (disease-causing) or benign (limited effect). It is a culmination of two types of data, amino acid residue evolutionary conservation and structural context of the residue based on AlphaFold2 predictions. <br>

Pathogenicity scores are calculated per amino acid substitution in a heatmap visualization in the ‘AlphaMissense Pathogenicity’ track of the feature viewer. The higher the score (red) the more likely the variant is predicted to be pathogenic. These scores are then used to calculate an average likely pathogenicity score for each amino acid position within the protein sequence. This can be found in the ‘Average pathogenicity score’ track.<br>
Example: [Q12834](https://www.uniprot.org/uniprotkb/Q12834/feature-viewer)
                                                                                                                                                                                                                                                                                                                                                                                     

## See also
[Why are there multiple cross-references to PDB in a UniProtKB entry?](https://www.uniprot.org/help/multiple_pdb_xrefs)  
[How can I retrieve UniProtKB entries that have a PDB 3D structure cross-reference?](https://www.uniprot.org/help/retrieve_3d)  
[Why do some structures only show a portion of the protein sequence?](https://www.uniprot.org/help/structure_subseq)
