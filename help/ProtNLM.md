---
title: ProtNLM
type: help
categories: UniProtKB,Automatic_annotation,help
---

# Introduction

UniProt's [Automatic Annotation pipeline](https://www.uniprot.org/help/automatic_annotation) automatically classifies and annotates unreviewed records in UniProtKB.

Google's **ProtNLM** (**Prot**ein **N**atural **L**anguage **M**odel) contributions to this pipeline are labeled 'GOOGLE:UNProtein'. ProtNLM is a [transformer model](https://proceedings.neurips.cc/paper/2017/file/3f5ee243547dee91fbd053c1c4a845aa-Paper.pdf) trained to predict the protein name from the protein's amino acid sequence.

# ProtNLM methodology

ProtNLM is a new method used by UniProt to automatically annotate sequences, with the goal of increasing the number of annotated sequences. This method works by predicting a short textual description for proteins based solely on their amino acid sequence, using a [sequence-to-sequence](https://en.wikipedia.org/wiki/Seq2seq) model.

## Sequence annotation as a machine learning problem

The sequence annotation problem shows similarities to other problems that can be solved with machine learning. Specifically, predicting a protein's name in English from its amino acid sequence is similar to predicting a title (or caption) for an image or a document.

![protnml-schematic.png](https://github.com/ebi-uniprot/uniprot-manual/blob/main/images/protnlm-schematic.png?raw=true)

ProtNLM uses a sequence-to-sequence model based on the [T5X framework](https://github.com/google-research/t5x).

## Notable challenges

This sequence annotation problem has been cast as a machine learning task similar to the task of assigning titles (or captions) to images and documents. It can sometimes present similar challenges.

For instance, one protein can be assigned multiple names, which can happen if each name focuses on different information. For example, the sequence [Q58842](https://www.uniprot.org/uniprotkb/Q58842/entry) can be assigned the following names: "Formaldehyde-activating enzyme", "3-hexulose-6-phosphate synthase", and "Bifunctional enzyme Fae/Hps", each of which focuses on a different functional domain or combination of functional domains detected in the protein. As such, it can be challenging to evaluate model-generated descriptions that differ from those assigned in UniProt.

Our task is particularly challenging because it can be hard even for experts to corroborate a particular proposed description without supporting evidence from external information, bioinformatics tools or experiments in the lab.

## Data processing and model validation

The ProtNLM model was trained with sequence-name pairs extracted from the UniProt database, including examples from both Swiss-Prot and TrEMBL. These pairs were filtered by name to remove entries deemed unsuitable for computational annotation. Example reasons for filtering out a sequence-name pair include low quality names, or names that are not informative.

Our validation procedure involves both automated and manual evaluation, including evaluation by a professional biocurator. Automatic evaluation was performed for various data subsets, including a challenging subset of sequences that were determined to have low sequence identity to the training set. Further, we release a file of additional evidence, based on traditional bioinformatics methods, that supports ProtNLM's predictions.

While we have carefully evaluated the models, we note that Machine Learning models can make errors and we invite users to flag any issues found via the UniProt [help desk](https://www.uniprot.org/update).

See also

- [Preprint](https://storage.googleapis.com/brain-genomics-public/research/proteins/protnlm/uniprot_2022_04/protnlm_preprint_draft.pdf)
- [Colab notebook to view evidence](https://colab.research.google.com/github/google-research/google-research/blob/master/protnlm/protnlm_evidencer_uniprot_2022_04.ipynb)
- [Colab notebook to use model](https://colab.research.google.com/github/google-research/google-research/blob/master/protnlm/protnlm_use_model_for_inference_uniprot_2022_04.ipynb)