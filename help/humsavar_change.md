---
title: Changes to the humsavar.txt file and related keywords
type: help
categories: changes
---

The [humsavar.txt](https://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/docs/humsavar) file lists all missense variants annotated in UniProtKB/Swiss-Prot human entries. It provides a variant classification which is intended for research purposes only, not for clinical and diagnostic use. Variants are currently classified into the categories `Disease`, `Polymorphisms` and `Unclassified`. We will rename these categories to follow the terminology recommended by the American College of Medical Genetics and Genomics/Association for Molecular Pathology (ACMG/AMP) (Richards et al. [PubMed:25741868](https://pubmed.ncbi.nlm.nih.gov/25741868/)):

| Old category | New category | Description                     |
| ------------ | ------------ | ------------------------------- |
| Disease      | LP/P         | likely pathogenic or pathogenic |
| Polymorphism | LB/B         | likely benign or benign         |
| Unclassified | US           | uncertain significance          |

Current format:

Main Swiss-Prot AA Type of
gene name AC FTId change variant dbSNP Disease name
\_\_\_\_\_\_\_\_\_ \_\_\_\_\_\_\_\_\_\_ \_\_\_\_\_\_\_\_\_\_\_ \_\_\_\_\_\_\_\_\_\_\_\_\_\_ \_\_\_\_\_\_\_\_\_\_\_\_\_ \_\_\_\_\_\_\_\_\_\_\_\_\_\_ \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
...
CC2D2A Q9P2K1 VAR_075698 p.Trp1182Arg Disease rs386833755 Joubert syndrome 9 (JBTS9) \[MIM:612285\]
CC2D2A Q9P2K1 VAR_076881 p.Ser117Arg Unclassified rs186264635 Joubert syndrome 9 (JBTS9) \[MIM:612285\]
CC2D2A Q9P2K1 VAR_076882 p.Lys507Glu Polymorphism rs144439937 Joubert syndrome 9 (JBTS9) \[MIM:612285\]
...

New format:

Main Swiss-Prot AA Variant
gene name AC FTId change category dbSNP Disease name
\_\_\_\_\_\_\_\_\_ \_\_\_\_\_\_\_\_\_\_ \_\_\_\_\_\_\_\_\_\_\_ \_\_\_\_\_\_\_\_\_\_\_\_\_\_ \_\_\_\_\_\_\_\_ \_\_\_\_\_\_\_\_\_\_\_\_\_\_ \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
...
CC2D2A Q9P2K1 VAR_075698 p.Trp1182Arg LP/P rs386833755 Joubert syndrome 9 (JBTS9) \[MIM:612285\]
CC2D2A Q9P2K1 VAR_076881 p.Ser117Arg US rs186264635 Joubert syndrome 9 (JBTS9) \[MIM:612285\]
CC2D2A Q9P2K1 VAR_076882 p.Lys507Glu LB/B rs144439937 Joubert syndrome 9 (JBTS9) \[MIM:612285\]
...

Also in line with the ACMG/AMP guidelines, we will at the same time deprecate the keyword "Polymorphism" and rename the keyword ["Disease mutation"](https://www.uniprot.org/keywords/KW%2D0225) to "Disease variant", because the terms 'polymorphism' and 'mutation', which have been used widely, often lead to confusion due to incorrect assumptions of pathogenic and benign effects, respectively.

Entries with variant annotations can be retrieved on the UniProt website with the query [`ft_variant:*`](<https://www.uniprot.org/uniprotkb?query=(ft_variant:*)>).
