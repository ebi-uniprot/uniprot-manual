
---
title: Assessing proteome completeness and quality
categories: help
---

In order to assess quality and completeness of [proteomes](http://www.uniprot.org/proteomes), we provide two values:

*   Statistical evaluation and classification of the proteome by the **Complete Proteome Detector (CPD)** algorithm (developed by UniProt)
*   The [BUSCO score](https://www.sib.swiss/about%2Dsib/news/10131%2Dgauging%2Dthe%2Dcompleteness%2Dof%2Dgenomics%2Ddata%2Dwith%2Dbusco) of the proteome, which was developed to quantify genomic data completeness in terms of expected gene content.

### Complete Proteome Detector (CPD)

CPD statistically analyses each proteome against a group of closely related proteomes in order to determine completeness. For each proteome, CPD uses [taxonomic lineage](http://www.uniprot.org/help/taxonomic%5Flineage) information to identify the group of proteomes taxonomically closest to it. A valid group is required to contain a minimum of three proteomes. For the proteome being analyzed, the algorithm compares selected attributes of all proteomes in its group to define the standard distribution of the number of proteins the proteome would be expected to contain in order to be considered complete. A quality metric is also determined based on the taxonomical closeness of the group of proteomes used for the analysis of the proteome in question.

This evaluation classifies each proteome into three possible categories (in terms of the proteome's protein count vs. the standard distribution of protein count expected for completeness): **standard**, **close to standard** or an **outlier**.

### Benchmarking Universal Single-Copy Orthologs (BUSCO)

For eukaryotic and bacterial proteomes, we also provide the [BUSCO score](https://www.sib.swiss/about%2Dsib/news/10131%2Dgauging%2Dthe%2Dcompleteness%2Dof%2Dgenomics%2Ddata%2Dwith%2Dbusco), which was developed to quantify genomic data completeness in terms of expected gene content.

This score includes percentages of complete (C) single-copy (S) genes, complete (C) duplicated (D) genes, fragmented (F) and missing (F) genes, as well as the total number of orthologous clusters (n) used in the BUSCO assessment.
        