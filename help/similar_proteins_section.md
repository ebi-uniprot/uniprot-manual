---
title: Similar proteins section
type: help
categories: Similar_proteins,manual
---

# UniRef clusters

This section provides links to proteins that are similar to the protein sequence(s) described in this entry at different levels of sequence identity thresholds (100%, 90% and 50%) based on their membership in UniProt Reference Clusters ([UniRef](https://www.uniprot.org/help/uniref)).

# Orthology and paralogy

Ths section provides orthology and paralogy information which has been retrieved from the Alliance of Genome Resources (AGR). Orthology describes genes from different species that have evolved from a common ancestral gene through a speciation event, meaning these genes typically perform similar functions across species. Paralogy, on the other hand, refers to genes within the same species that originated from duplication events, often resulting in genes with related but distinct functions.

## Data source

The orthology and paralogy data presented within UniProtKB entry pages is sourced from the [Alliance of Genome Resources (AGR)](https://www.alliancegenome.org/), a collaborative effort that integrates comprehensive genetic and genomic data from multiple model organisms and humans. AGR utilizes the DRSC Integrative Ortholog Prediction Tool ([DIOPT](https://www.flyrnai.org/diopt)), which consolidates results from various ortholog and paralog prediction methods along with expert-curated information from resources like [HGNC](https://www.genenames.org/) (human), [MGI](https://www.informatics.jax.org/) (mouse), [Xenbase](https://www.xenbase.org/) (frog), [ZFIN](https://zfin.org/) (zebrafish), and [SGD](https://www.yeastgenome.org/) (yeast).

## Column descriptions

Each tab of this section contains a table listing the respective homology data with the following columns.

### Orthology

| Column       | Description                                                                                                             |
| ------------ | ----------------------------------------------------------------------------------------------------------------------- |
| Species      | Target organism in which this ortholog candidate resides                                                                |
| Gene Symbol  | Gene symbol of the ortholog in the target species                                                                       |
| Best         | Indicates this gene is the top-scoring (highest-count) ortholog candidate within this species                           |
| Best Reverse | Indicates this gene pair is also the top-scoring (highest-count) ortholog when roles are reversed (reciprocal best hit) |
| Method       | Results of orthology-inference resource and algorithm methods.                                                          |
| Match count  | Number of independent orthology-inference resource and algorithm methods that support this gene pair.                   |

### Paralogy

| Column      | Description                                                                                          |
| ----------- | ---------------------------------------------------------------------------------------------------- |
| Gene Symbol | Gene symbol of the paralog in the same species                                                       |
| Rank        | Rank of this gene among all paralog candidates based on supporting evidence                          |
| Length      | Length (in amino acids) of the paralogous protein sequence                                           |
| Similarity  | Percent sequence similarity between the query gene and its paralog                                   |
| Identity    | Percent sequence identity between the query gene and its paralog                                     |
| Method      | Result of paralogy-inference resource and algorithm                                                  |
| Match count | Number of independent paralogy-inference resource and algorithm methods that support this gene pair. |

## Additional information and help

For further details and assistance, visit the AGR help documentation at https://www.alliancegenome.org/help.

# Related documents

- [UniRef](https://www.uniprot.org/help/uniref)
- [Orthology](https://www.uniprot.org/help/orthology)
- [Orthologs between two species](https://www.uniprot.org/help/orthologs_between_two_species)
