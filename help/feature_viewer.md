---
title: Feature viewer
type: help
categories: manual
---

The feature viewer is a comprehensive graphical representation of protein sequence features that are mapped to a protein's amino acid sequence. It includes a range of data from multiple sources such as domains, sites, post-translational modifications, mutagenesis, proteomics-derived peptides, antigenic sequences and natural variants. Data is composed of a mixture of UniProtKB curated and imported data from [cross-referenced](https://www.uniprot.org/database?query=*) databases and collaboration initiatives.
The feature viewer facilitates understanding of multiple aspects of a protein's function by providing an overview of all the protein's features in a single graphical view.

## Navigating the feature viewer

Protein features are displayed in tracks. Each track represents a biological category of features, many of which can be expanded into sub-tracks for a more detailed overview. Selecting a feature displays more detailed information, including the amino acid residue numbers involved, feature description and source of the data. Selecting a feature also results in a yellow vertical highlight at those amino acid residues across all tracks on the feature viewer, which assists in identification of co-occurring features at those residues.

When 3D structure information is available for a protein, an interactive graphic of the structure is shown below the feature table, with options below the graphic to change the structure shown (if [multiple structures are available](https://www.uniprot.org/help/structure_section#structure_coverage)). Selecting a feature in the feature viewer  highlights the residues involved on the 3D structure graphic, provided that the structure covers the [sequence portion](https://www.uniprot.org/help/structure_subseq) on which the feature occurs.

## Where to find the feature viewer

The feature viewer can be found in the ‘Feature viewer’ tab at the top of a protein entry page. 
Some tracks from the feature viewer can also be found within the protein entry, such as in the PTM/Processing section.

## How to download data found in the feature viewer
Information found in the feature viewer can be downloaded by using the ‘Download’ option in the top left of the feature viewer window. 
- Download UniProtKB > Entry will download all information shown in the [UniProtKB entry view](https://www.uniprot.org/help/explore_uniprotkb_entry) for this protein.
- Download UniProtKB > Features Only will download all protein sequence features in the entry that are mapped to amino acid residues from within the UniProtKB entry.
- Download Additional Datasets > downloads imported data associated with that track from datasets that are sourced from [cross-referenced databases](https://www.uniprot.org/database?query=*).

## Feature viewer tracks and associated help pages
Each track within the feature viewer shows a category of biological data for the protein displayed. Some tracks can be expanded into sub-tracks which show further categories within that track and allow a more detailed view of the features. 
Tracks will only be shown if there is data available for that feature type for a selected protein.

Find below a list of all possible tracks, sub-tracks and their associated help pages. 

|                                                                                                                                   |                                                                                                                                            |
| :-------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| **Track**                                                                                                                    | **Sub-track**                                                                                                                                |
| [Sequence status](https://www.uniprot.org/help/sequence_status)                                                                   | Indicates if the protein sequence is complete or not                                                                                       |
| [Sequence processing](https://www.uniprot.org/help/sequence_processing)                                                           | Indicates if the mature form of a protein is derived by processing of a precursor                                                          |
| [Sequence](https://www.uniprot.org/help/sequences)                                                                                | Canonical protein sequence data and list of described protein isoforms                                                                     |
| [Alternative products](https://www.uniprot.org/help/alternative_products)                                                         | Description of the different proteins generated from the same gene                                                                         |
| [Computationally mapped potential isoform sequences](https://www.uniprot.org/help/gene_centric_isoform_mapping)                   | Automatic gene-centric isoform mapping for eukaryotic reference proteome sequences                                                         |
| [Sequence caution](https://www.uniprot.org/help/sequence_caution)                                                                 | Warning about possible errors related to the protein sequence                                                                              |
| [RNA editing](https://www.uniprot.org/help/rna_editing)                                                                           | Description of amino acid change(s) due to RNA editing                                                                                     |
| [Mass spectrometry](https://www.uniprot.org/help/mass_spectrometry)                                                               | Information derived from mass spectrometry experiments                                                                                     |
| [Polymorphism](https://www.uniprot.org/help/polymorphism)                                                                         | Description of polymorphism(s)                                                                                                             |
| [Natural variant](https://www.uniprot.org/help/variant)                                                                           | Natural variants documented for the protein                                                                                                |
| [Alternative sequence](https://www.uniprot.org/help/var_seq)                                                                      | Amino acid change(s) producing alternate protein isoforms                                                                                  |
| [Sequence uncertainty](https://www.uniprot.org/help/unsure)                                                                       | Regions of uncertainty in the sequence                                                                                                     |
| [Sequence conflict](https://www.uniprot.org/help/conflict)                                                                        | Description of sequence discrepancies of unknown origin                                                                                    |
| [Non-adjacent residues](https://www.uniprot.org/help/non_cons)                                                                    | Indicates that two residues in a sequence are not consecutive                                                                              |                                 
