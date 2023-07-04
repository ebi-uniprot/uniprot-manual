---
title: ProtNLM
type: help
categories: UniProtKB,Automatic_annotation,help
---

# Introduction

UniProt's [Automatic Annotation pipeline](https://www.uniprot.org/help/automatic_annotation) automatically classifies and annotates unreviewed records in UniProtKB.

Google's **ProtNLM** (**Prot**ein **N**atural **L**anguage **M**odel) contributions to this pipeline are labeled 'Google:ProtNLM'. See e.g. [A0A2Z4IEP2](https://www.uniprot.org/uniprotkb/A0A2Z4IEP2/entry). ProtNLM is a [transformer model](https://proceedings.neurips.cc/paper/2017/file/3f5ee243547dee91fbd053c1c4a845aa-Paper.pdf) trained to predict the protein name from the protein's amino acid sequence.

# ProtNLM methodology

ProtNLM is a new method used by UniProt to automatically annotate uncharacterized protein sequences. This method works by predicting a short textual description for proteins based solely on their amino acid sequence, using a [sequence-to-sequence](https://en.wikipedia.org/wiki/Seq2seq) model.

## Sequence annotation as a machine learning problem

The sequence annotation problem has similarities to other problems that can be solved with machine learning. For example, predicting a protein's name in English from its amino acid sequence can be seen as similar to predicting a title (or caption) for an image or a document.

![protnlm-UNProtein input-output figure.png](https://raw.githubusercontent.com/ebi-uniprot/uniprot-manual/main/images/protnlm-UNProtein%20input-output%20figure.png)

ProtNLM uses a sequence-to-sequence model based on the [T5X framework](https://github.com/google-research/t5x).

## Notable challenges

This sequence annotation problem has been cast as a machine learning task similar to the task of assigning titles (or captions) to images and documents. It can sometimes present similar challenges.

For instance, one protein can be assigned multiple names, which can happen if each name focuses on different information. For example, the sequence [Q58842](https://www.uniprot.org/uniprotkb/Q58842/entry) can be assigned the following names: "Formaldehyde-activating enzyme", "3-hexulose-6-phosphate synthase", and "Bifunctional enzyme Fae/Hps", each of which focuses on a different functional domain or combination of functional domains detected in the protein. As such, it can be challenging to evaluate model-generated descriptions that differ from those assigned in UniProt.

Our task is particularly challenging because it can be hard even for experts to corroborate a particular proposed description without supporting evidence from external information, bioinformatics tools or experiments in the lab.

## Data processing and model validation

ProtNLM was trained with input-output pairs extracted from the UniProt database, including examples from both Swiss-Prot and TrEMBL. These pairs were filtered by name to remove entries deemed unsuitable for computational annotation. Example reasons for filtering out a sequence-name pair include low quality names, or names that are not informative as advised by experts at UniProt.

Our validation procedure involves both automated and manual evaluation, including evaluation by a professional biocurator. Automatic evaluation was performed for various data subsets, including a challenging subset of sequences that were determined to have low sequence identity to the training set. Further, we release a file of additional evidence, based on traditional bioinformatics methods, that supports ProtNLM's predictions.

## Leveraging additional protein information

The simplest version of ProtNLM model takes in an amino acid sequence as input and produces a protein name as output. In UniProt 2022_04, all ProtNLM annotations were produced by a single model of this form.

In more recent releases, we leverage models that take as input not only the protein amino acid sequence but also additional information that is typically available even when the protein is uncharacterized.

First, we include the organism where the protein was found. The organism is typically known even for uncharacterized proteins and can provide information about potential names; for example "Ovule protein" occurs commonly among plant proteins, but less frequently among proteins from other kingdoms of life.

![protnlm-UNProtein with organism input-output figure.png](https://raw.githubusercontent.com/ebi-uniprot/uniprot-manual/main/images/protnlm-UNProtein%20with%20organism%20input-output%20figure.png)

Second, we consider models that additionally take as input the protein's secondary structure, which we extract from the predicted AlphaFold structure included in UniProt.

![protnlm-UNProtein with secondary structure input-output figure.png](https://raw.githubusercontent.com/ebi-uniprot/uniprot-manual/main/images/protnlm-UNProtein%20with%20secondary%20structure%20input-output%20figure.png)

## Ensembling

For recent releases, we have used an ensemble across multiple types of models to improve performance.

In UniProt 2022_05, we used an ensemble containing 3 models that take only the amino acid sequence as input, and 3 models that take both the amino acid sequence and the organism as input. For proteins that were previously named by ProtNLM, we provided new names whenever the ensemble prediction exceeded the initial model score by more than 0.1.

![protnlm-UNProtein ensemble input-output figure.png](https://raw.githubusercontent.com/ebi-uniprot/uniprot-manual/main/images/protnlm-UNProtein%20ensemble%20input-output%20figure.png)

In UniProt 2023_01, we used this ensemble to update all ProtNLM annotations, and introduced a model score threshold so that predictions are only released when the model score is above 0.2. We also improved the post-processing of predicted names and where possible, we used an automatic corroboration pipeline to decide which ensemble prediction to select as the recommended protein name.

Starting with UniProt 2023_02, when UniProt supplies an AlphaFold prediction for a given accession, we also include in the ensemble a model that takes the amino acid sequence, organism and predicted secondary structure as inputs. The 7 models that form the new ensemble were re-trained from scratch on the original training data, from which we also held out a small amount of random sequences for in-distribution validation. To incorporate new biocurator feedback and recent updates to some ground truth names in UniProt, we also fine-tuned the models on updated training data with additional protein name filtering proposed by the biocurators.

## Curation of predictions

While we have carefully evaluated the models, we note that Machine Learning models can make errors and we invite users to flag any issues found via the UniProt [help desk](https://www.uniprot.org/update).

One approach for investigating the accuracy of a predicted name is to search for proteins whose protein name matches our prediction and examine whether there is a significant alignment between the protein sequence whose prediction is being investigated and the retrieved protein sequences:

![protnlm-UNProtein evidence via alignment figure.png](https://raw.githubusercontent.com/ebi-uniprot/uniprot-manual/main/images/protnlm-UNProtein%20evidence%20via%20alignment%20figure.png)

In previous releases, we provided a [colab notebook](https://colab.sandbox.google.com/github/google-research/google-research/blob/master/protnlm/protnlm_evidencer_uniprot_2023_01.ipynb) with precomputed alignment information for ProtNLM annotations. We have now deprecated this colab, and instead recommend using the UniProt search and alignment features. For example, to search for evidence for the predicted name "Adhesion G protein-coupled receptor V1" assigned to protein [D2GX75](https://www.uniprot.org/uniprotkb/D2GX75/entry), a user can

1. [Add the sequence D2GX75 to the basket](https://raw.githubusercontent.com/ebi-uniprot/uniprot-manual/main/images/protnlm-4-pandasquencessorted%20by%20length.png),
2. Search for proteins named "Adhesion G protein-coupled receptor V1" via the [UniProt search feature](https://www.uniprot.org/uniprotkb?query=protein_name%3A%22Adhesion%20G%20protein-coupled%20receptor%20V1%22),
3. Select the proteins to compare protein D2GX75 with, e.g. [all reviewed entries named "Adhesion G protein-coupled receptor V1"](https://raw.githubusercontent.com/ebi-uniprot/uniprot-manual/main/images/protnlm-7-selection%20of%20SwissProt.png), and [add them to the basket containing already the original protein D2GX75](https://raw.githubusercontent.com/ebi-uniprot/uniprot-manual/main/images/protnlm-8-basket%20function.png),
4. [Perform sequence alignment](https://raw.githubusercontent.com/ebi-uniprot/uniprot-manual/main/images/protnlm-9-alignment%20part%201.png), and [examine the resulting alignment](https://raw.githubusercontent.com/ebi-uniprot/uniprot-manual/main/images/protnlm-10-alignment%20part%202.png). For instance, in this case, a distinguishing property of G protein-coupled receptors (GPCRs) is that [they contain 7 transmembrane domains](https://raw.githubusercontent.com/ebi-uniprot/uniprot-manual/main/images/protnlm-12-G-protein%20couples%20receptors.png), so one can use [UniProt website's ability to highlight the transmembrane regions](https://raw.githubusercontent.com/ebi-uniprot/uniprot-manual/main/images/protnlm-11-alignment%20part%203_with%20transmembrane%20annotation.png) to [assess whether the transmembrane domains are conserved across the proteins compared](https://raw.githubusercontent.com/ebi-uniprot/uniprot-manual/main/images/protnlm-13-alignment%20part%203_conservation%20of%20transmembrane%20domains.png).

## References

- [Preprint](https://storage.googleapis.com/brain-genomics-public/research/proteins/protnlm/uniprot_2022_04/protnlm_preprint_draft.pdf)
- [YouTube video](https://www.youtube.com/watch?v=FLkoaDJBC54)
- [Colab notebook to query one of the ProtNLM models](https://colab.research.google.com/github/google-research/google-research/blob/master/protnlm/protnlm_use_model_for_inference_uniprot_2022_04.ipynb)
- [Explore all UniProtKB entries with these annotations](https://www.uniprot.org/uniprotkb?query=%28source:google%29)
