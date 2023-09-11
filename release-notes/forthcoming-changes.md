---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

# TSV format

**On November 8th, 2023**

We are going to make the following changes to multiple ids columns related values (Ensembl, EMBL, RefSeq).

* We will separate these ids with semicolon, wrapping with double quotes.

Example: [A0JNW5](https://rest.uniprot.org/uniprotkb/A0JNW5.tsv?fields=xref_ensembl)

Current format:

```
ENST00000279907.12 [A0JNW5-1];ENST00000356828.7 [A0JNW5-2];
```

New format:

```
"ENST00000279907.12;ENSP00000279907.7;ENSG00000111647.13; [A0JNW5-1]";"ENST00000356828.7;ENSP00000349285.3;ENSG00000111647.13; [A0JNW5-2]";
```