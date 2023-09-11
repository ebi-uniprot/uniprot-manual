---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

# Change of TSV format for cross-references with multiple identifiers

**On November 8th, 2023**

The current TSV format for cross-references to external resources consists of the primary identifier of the external resource and, optionally, the [UniProt isoform identifier in square brackets](https://www.uniprot.org/help/isoform_crossreferences). When an entry has several cross-references to the same external resources, these cross-references are separated by a semi-colon in the TSV format.

In response to user requests, we are going to include all identifiers of external resources that are available in our other UniProtKB download formats. The format for an individual cross-reference will be identical to the format used in the UniProtKB text format (with multiple fields being separated by semi-colons). In order to continue to separate multiple cross-references to the same external resource with a semi-colon, each individual cross-reference will be enclosed in double quotes.

Example: [A0JNW5](https://rest.uniprot.org/uniprotkb/A0JNW5.tsv?fields=xref_ensembl)

Current format:

```
ENST00000279907.12 [A0JNW5-1];ENST00000356828.7 [A0JNW5-2];
```

New format:

```
"ENST00000279907.12; ENSP00000279907.7; ENSG00000111647.13. [A0JNW5-1]";"ENST00000356828.7; ENSP00000349285.3; ENSG00000111647.13. [A0JNW5-2]";
```
