---
title: Reasons to exclude a proteome from UniProtKB
type: help
categories: help
---

UniProt excludes certain [proteomes](https://www.uniprot.org/help/proteome) where the assembly has been excluded from the NCBI Reference Sequence (RefSeq) project for any of the reasons listed below. This list is a subset of the [exclusion reasons used by RefSeq](https://www.ncbi.nlm.nih.gov/assembly/help/anomnotrefseq/).

The exclusion reason is provided in the proteome page for an excluded proteome, e.g. [UP000004469](https://www.uniprot.org/proteomes/UP000004469).
Sequences from excluded proteomes remain accessible in [UniParc](https://www.uniprot.org/uniparc).

| Exclusion reason           | Explanation                                                                                                                                                                                                      |
|:---------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| chimeric                   | Sequences from two different organisms are joined together.                                                                                                                                                      |
| contaminated               | Sequences from another organism, cloning vectors, linkers, adapters or primers are present in the assembly.                                                                                                      |
| hybrid                     | Sequences from a hybrid between different species, strains or isolates.                                                                                                                                          |
| misassembled               | Alignment to related genome assemblies or other evidence indicates the assembly is likely to have errors.                                                                                                        |
| mixed culture              | Sequences come from two or more organisms that were not cultured separately.                                                                                                                                     |
| sequence duplications      | Assembly has one or more large duplications.                                                                                                                                                                     |
| unverified source organism | The origin of the assembly is misidentified.                                                                                                                                                                     |
| genome length too large    | Total non-gapped sequence length of the assembly is more than 1.5 times that of the average for the genomes in the Assembly resource from the same species, more than 15 Mbp, or is otherwise suspiciously long. |
| genome length too small    | Total non-gapped sequence length of the assembly is less than half that of the average for the genomes in the Assembly resource from the same species, less than 300 Kbp, or is otherwise suspiciously short.    |



# See also

- [What are proteomes?](https://www.uniprot.org/help/proteome)
- [What are reference proteomes?](https://www.uniprot.org/help/reference_proteome)
- [UniParc](https://www.uniprot.org/help/uniparc)
- [How to retrieve sets of UniProtKB protein sequences?](https://www.uniprot.org/help/retrieve_sets)
- [Reducing proteome redundancy](https://www.uniprot.org/help/proteome_redundancy)
