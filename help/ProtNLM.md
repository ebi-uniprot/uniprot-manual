---
title: Automatic annotation using ProtNLM
type: help
categories: UniProtKB,Automatic_annotation,help
---

UniProt’s [Automatic Annotation pipeline](https://www.uniprot.org/help/automatic_annotation) enhances [unreviewed](https://www.uniprot.org/help/uniprotkb_sections)/TrEMBL [UniProtKB](https://www.uniprot.org/uniprotkb) entries with automatic classification and annotation.

UniProt leverages machine learning artificial intelligence (AI) using a Protein Natural Language Model (ProtNLM) developed by collaborators at [Google DeepMind](https://deepmind.google/science/). ProtNLM was originally used to predict [protein names](https://www.uniprot.org/help/protein_names) but has now been expanded with ProtNLM2 to include predictions for [function](https://www.uniprot.org/help/function) comments, [subcellular locations](https://www.uniprot.org/help/subcellular_location), [keywords](https://www.uniprot.org/help/keywords), and [Gene Ontology](https://www.uniprot.org/help/gene_ontology) (GO) terms.

# ProtNLM methodology

ProtNLM is a [transformer-based sequence-to-sequence AI model](https://storage.googleapis.com/brain-genomics-public/research/proteins/protnlm/uniprot_2022_04/protnlm_preprint_draft.pdf) trained on a snapshot of UniProtKB data to generate annotations for unreviewed/TrEMBL UniProtKB entries. It uses an approach similar to AI natural language models that generate titles or captions for images. Predictions were originally generated using amino acid sequence as input, while later models have added [organism TaxID](https://www.uniprot.org/help/taxonomic_identifier) and secondary structure predictions from [AlphaFoldDB](https://alphafold.ebi.ac.uk/) to the inputs.

# Timeline of ProtNLM generated data in UniProt

The original iteration of ProtNLM, trained on [protein name](https://www.uniprot.org/help/protein_names) data from UniProt release 2021_02 (including all recommended names (RecNames), alternative names (AltNames) and submitted names (SubNames)), has provided predicted protein names for proteins with the name “Uncharacterized protein”. From UniProt release 2022_04 onwards, these predicted protein names have been included in unreviewed/TrEMBL entry pages with the “Automatic Annotation ([ECO:0008006](https://www.ebi.ac.uk/QuickGO/term/ECO:0008006)) Google:ProtNLM” evidence tag.

ProtNLM has continued to develop over time. Early iterations of ProtNLM data used a single model to generate predictions while later [releases](https://www.uniprot.org/help/synchronization) use an ensemble of multiple models, some taking different combinations of inputs, to improve performance:

- Release 2022_04 - ProtNLM was used to predict protein names for proteins with the Submitted name (SubName) “Uncharacterized protein”.
- Release 2022_05 - Predictions updated using an ensemble of 3 models that take only the amino acid sequence as input, and 3 models that take both the amino acid sequence and the organism TaxID as input.
- Release 2023_01 - Model score threshold introduced and improved post-processing to enhance prediction accuracy.
- Release 2023_02 - A new ensemble of 7 models was trained on the original data, including 1 model that uses AlphaFoldDB secondary structure predictions as input.

![ProtNLM: Ensemble of seven models](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/ProtNLM_model_ensemble.png)

# ProtNLM2: expanding annotation beyond protein names

A second iteration of ProtNLM (ProtNLM2) expands annotation predictions to include protein names, protein function comments, subcellular locations, keywords and Gene Ontology terms. ProtNLM2 is trained on 240 million proteins from UniProt release 2023_04, including both [curator reviewed](https://www.uniprot.org/help/manual_curation)/Swiss-Prot entries and unreviewed/TrEMBL entries with submitter provided names (SubNames) and annotated by the UniProt [Automatic Annotation](https://www.uniprot.org/help/automatic_annotation) pipeline. 
An initial ProtNLM2 pilot release, providing annotations for roughly [26,000 TrEMBL entries](https://ftp.ebi.ac.uk/pub/contrib/UniProt/ProtNLM2/List_of_UniProt_accessions_that_have_ProtNLM2_annotations.tsv) from the species most commonly searched for on the UniProtKB website, has been made public in conjunction with the UniProt 2026_02 release.

# ProtNLM2 prediction quality assessment

Predicted annotations have been continually assessed throughout the development of the ProtNLM models, both by automated evaluation as well as manual evaluation by expert UniProt biocurators working in close collaboration with Google DeepMind.

While ProtNLM models have been carefully evaluated during their development, machine learning AI models do make errors. We invite users to carefully evaluate these predictions and flag any issues or errors they find via the “Entry feedback” link in the corresponding entry, or via the general [UniProt help desk](https://www.uniprot.org/contact).

## ProtNLM model score

Each ProtNLM prediction is assigned a model score representing an estimate of the likelihood of the prediction being generated. This score reflects the model's probability of generating the prediction based on the input sequence. The score ranges from 0 to 1, with higher scores indicating a higher estimated likelihood.

For ProtNLM protein name ([RecName](https://www.uniprot.org/help/protein_names)) predictions, we apply a model score threshold of 0.2, removing any predictions that fall below this.

For ProtNLM2 predictions, we have reduced the model score threshold to 0.05 as many predictions with low model scores were judged to be accurate. Instead, Google DeepMind have implemented a post-processing corroboration strategy (described below) to filter out unreliable predictions. Based on ongoing curator evaluation and user feedback on the ProtNLM2 pilot release, this model score threshold may be altered (increased or removed) for future ProtNLM2 releases. Model scores for all predictions are provided for the user to make their own assessment on prediction reliability.

## Post-processing corroboration strategy

As AI natural language models are in essence a black box system, there is no way to determine what evidence the model uses to make a certain prediction. Instead, we implement a post-processing corroboration system (a.k.a. Evidencer) as a quality control pipeline for ProtNLM2 predictions. This process mimics the expert [biocurator evaluation process](https://www.uniprot.org/help/biocuration).

Predicted annotations that match certain exclusion criteria, such as GO annotations that are restricted by [GO taxon constraints](https://geneontology.org/docs/taxon-constraints/#:~:text=Taxon%20constraints%20are%20used%20to,specificity%20of%20the%20GO%20terms), or inaccurate protein names that do not conform to the [International Protein Nomenclature guidelines](https://www.uniprot.org/help/international_protein_nomenclature_guidelines), are removed.

Predicted annotations are then corroborated by looking for exact or partial (substring) matches with other annotations in the entry being annotated. The corroboration process also queries several external databases such as [InterPro](https://www.ebi.ac.uk/interpro/), and checks for an exact or partial (substring) match (designated as a hydrated string/substring match) within descriptions of signatures cross-referenced within the entries being annotated. 

### Corroboration by sequence similarity

If no string/substring match is found, the corroboration process checks for sequence similarity (determined by the [phmmer tool](https://www.ebi.ac.uk/Tools/hmmer/search/phmmer)) to other entries in UniProtKB containing annotations identical to the predicted annotation. Predicted annotations are considered reliable if they have matching annotations in entries with a sequence similarity phmmer bit score greater than 25. 

### Corroboration by structural similarity

If there is no corroboration by sequence similarity, the process checks structural similarity (determined by the [tm-align tool](https://www.rcsb.org/alignment)) to other entries in UniProtKB containing annotations identical to the predicted annotation.  Corroboration requires the TM-align score normalized to the protein with the predicted annotation to be greater than 0.5 and the TM-align score normalized to the corroborating protein possessing a matching prediction to be greater than 0.1. Additionally, structural similarity corroboration requires a minimum sequence identity of 5%, a minimum of 3 matching secondary structure elements and a minimum pLDDT score for aligned residues of 70.

The corroboration workflow produces three possible outcomes:

- **Rejected**: The ProtNLM2 annotation matches exclusion criteria. The annotation is flagged and not displayed in UniProtKB.
- **Approved and Displayed**: The ProtNLM2 annotation does not match exclusion criteria and is corroborated by exact/substring matches or similarity matches. The annotation is approved and displayed in UniProtKB.
- **Uncertain Quality**: The ProtNLM2 annotation is neither corroborated nor rejected, leaving prediction quality uncertain. The annotation is flagged and not displayed in UniProtKB.

![ProtNLM: Evidencer Workflow](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/ProtNLM_evidencer_flow.png)

## Summary of prediction exclusion criteria

Predictions are excluded if they satisfy **all** of the following criteria:

|                            |                                            |        |
|:---------------------------|:-------------------------------------------|--------|
| Prediction confidence      | ProtNLM model score                        | <0.05  |
| Sequence similarity        | Phmmer bit score                           | <25    |
| Structural similarity      | TM-align score (protein with prediction): <br> or <br> TM-align score (protein with matching annotation): <br> or <br>Matching secondary structure elements: <br> or <br> Sequence identity: <br> or <br> pLDDT of aligned residues:  |<0.5 <br> <br> <0.1 <br> <br> <3 <br> <br> <5% <br> <br> <70 |



# Accessing ProtNLM annotated data

## FTP download

A complete list of TrEMBL entries annotated using ProtNLM2 is avaliable on our [FTP site](https://ftp.ebi.ac.uk/pub/contrib/UniProt/ProtNLM2/List_of_UniProt_accessions_that_have_ProtNLM2_annotations.tsv). This file provides a list of approximately 26K protein entries, the protein names present in this file are those present in UniProt and are not protein names generated by ProtNLM2. 

## On the website

The ProtNLM predicted protein names for proteins previously named “uncharacterized protein” have been integrated into the UniProtKB data in a similar way as names predicted by other automatic annotation methods. These annotations can be recognised by the “Automatic Annotation (ECO:0008006) Google:ProtNLM” evidence tag, for example in entries  [A0A6E8VIU4](https://www.uniprot.org/uniprotkb/A0A6E8VIU4/entry#names_and_taxonomy) and [Q54TU2](https://www.uniprot.org/uniprotkb/Q54TU2/entry#names_and_taxonomy). To search or filter for all entries annotated with a ProtNLM predicted protein name, use the search term “source:google” to filter for entries with [ProtNLM annotations](https://www.uniprot.org/uniprotkb?query=source%3Agoogle).

ProtNLM2 predicted annotations are not integrated into the UniProtKB entries directly but are stored in parallel and can be viewed on the website by switching on the AI annotation toggle found at the top of the entry page next to the [entry name](https://www.uniprot.org/help/entry_name) of ProtNLM2 annotated entries. AI generated annotations are clearly differentiated by a purple background colour and sparkle icon.

![ProtNLM: Example entry](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/ProtNLM2_example_entry_image.jpg)

## Interpreting prediction evidence information

We provide Evidencer information for ProtNLM2 predictions to help users evaluate their accuracy. These can be viewed by clicking the “Automatic Annotation” tag next to the predicted information. This will open a text box containing [evidence](https://www.uniprot.org/help/evidences) in support of the prediction. Several types of evidence statements are given:

- **Exact/Partial matches**: An exact string or substring match of the prediction is found in the entry. Currently, predictions that are an exact match to an annotation in an entry (e.g. a predicted function statement matching the function statement already in the entry) are not shown. Alternatively, the match is found in the description of a term in an external database cross-referenced in the entry. The cross-referenced databases queried using this approach include [InterPro/Pfam](https://www.ebi.ac.uk/interpro/), the [Gene Ontology (GO) knowledgebase](https://geneontology.org/), and the [Enzyme nomenclature database](https://enzyme.expasy.org/) for [EC (Enzyme Commission) numbers](https://en.wikipedia.org/wiki/Enzyme_Commission_number). A link is provided to the matching database entry.
- **Sequence similarity**: The predicted annotation is found in other entries with sequence homology to the entry. A link is provided to the entry with the highest similarity as determined by phmmer alignment. The higher the provided similarity bit score the more significant the sequence similarity.
- **Structure similarity**: The predicted annotation is found in other entries that share structural homology with the entry. A link is provided to the entry with the highest similarity as determined by TM-align. The TM-align score ranges from 0 to 1, with a score of 1 indicating a perfect match and structures with scores of <0.2 considered unrelated while those with scores >0.5 are considered to have a highly similar protein fold.

In the case of sequence and structure evidence, links are included to perform sequence alignments using the UniProt [Align tool](https://www.uniprot.org/align) or structural alignments using the FoldSeek [FoldMason tool](https://search.foldseek.com/foldmason). This allows users to evaluate the prediction evidence themselves.


# Links

- [ProtNLM preprint](https://storage.googleapis.com/brain-genomics-public/research/proteins/protnlm/uniprot_2022_04/protnlm_preprint_draft.pdf)
- [YouTube video](https://www.youtube.com/watch?v=FLkoaDJBC54)
- [Explore all entries with ProtNLM protein name predictions](https://www.uniprot.org/uniprotkb?query=%28source:google%29)
- [List of all ProtNLM2 pilot release annotated entries](https://ftp.ebi.ac.uk/pub/contrib/UniProt/ProtNLM2/List_of_UniProt_accessions_that_have_ProtNLM2_annotations.tsv)
