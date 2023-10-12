---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

# Additional TSV return fields for cross-references - UPDATE of Oct. 5, 2023

**On November 8th, 2023**

On Sep 13, 2023 we announced our plan to change the TSV format for cross-references with multiple identifiers in response to user requests. After further user feedback, we have revised our original plan in the following way:

1. We will not change the format of the existing [UniProtKB return fields for cross-references](https://www.uniprot.org/help/return_fields_databases).

   These fields consist of the primary identifier of the external resource and, optionally, the [UniProt isoform identifier in square brackets](https://www.uniprot.org/help/isoform_crossreferences). When an entry has several cross-references to the same external resources, these cross-references are separated by a semi-colon in the TSV format.

2. We will introduce additional UniProtKB return fields for all cross-references that have additional identifiers or other information.
   
   The format of an individual cross-reference will be identical to the format used in the UniProtKB text format (with multiple fields being separated by semi-colons). In order to continue to separate multiple cross-references to the same external resource with a semi-colon, each individual cross-reference will be enclosed in double quotes.

Example: [A0JNW5 Ensembl cross-references](https://rest.uniprot.org/uniprotkb/A0JNW5.tsv?fields=xref_ensembl)

Existing return field ``xref_ensembl``:

```
ENST00000279907.12 [A0JNW5-1];ENST00000356828.7 [A0JNW5-2];
```

New return field ``xref_ensembl_full``:

```
"ENST00000279907.12; ENSP00000279907.7; ENSG00000111647.13. [A0JNW5-1]";"ENST00000356828.7; ENSP00000349285.3; ENSG00000111647.13. [A0JNW5-2]";
```

Example: [A0JNW5 InterPro cross-references](https://rest.uniprot.org/uniprotkb/A0JNW5.tsv?fields=xref_interpro)

Existing return field ``xref_interpro``:

```
IPR026728;IPR026854;
```

New return field ``xref_interpro_full``:

```
"IPR026728; BLTP3A/B.";"IPR026854; VPS13-like_N."
```
