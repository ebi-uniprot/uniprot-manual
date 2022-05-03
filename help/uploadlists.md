---
title: Retrieve / ID mapping
type: help
categories: Website,help
---

[Tutorial/Video](https://www.youtube.com/watch?v=kLdgjqWoMZc)

Select the **Retrieve/ID mapping** tab of the toolbar and enter or upload a list of identifiers (or gene names) to do one of the following:

- Retrieve the corresponding UniProt entries to download them or work with them on this website.
- Convert identifiers which are of a different type to UniProt identifiers or vice versa, and download the identifier lists.

# How to use this tool

1.  Enter identifiers or upload them from a file, separated by a space or a new line, into the form field, for example: P31946 P62258 ALBU_HUMAN
2.  If you need to convert to another identifier type (as performed previously by the "ID mapping" service), select the source and target type from the "From/To" dropdown menus under "Options". Otherwise, to retrieve or download a list UniProtKB entries, keep the default selection of these menus (from UniProtKB AC/ID to UniProtKB)
3.  Click the **Submit** button.

The following kinds of UniProt identifiers are supported:

|           |                      |                                  |
| :-------- | :------------------- | :------------------------------- |
| UniProtKB | P00750               | UniProtKB entry                  |
|           | P00750 -2            | UniProtKB entry isoform sequence |
|           | P00750 \[39-81\]     | UniProtKB sequence range         |
|           | **A4_HUMAN**         | UniProtKB entry name             |
| UniParc   | UPI0000000001        | UniParc entry                    |
| UniRef    | **UniRef100_P00750** | UniRef entry                     |

When mapping from a source database external to UniProt, you can submit any identifier as used in the UniProtKB [cross-references](https://www.uniprot.org/help/cross_references_section). If your job is not successful and you are not sure which source database to use, try a text search in UniProtKB with one of your identifiers, and look at an example entry. Check out the cross-reference section to find out which database uses these identifiers.

# Further queries involving your UniProtKB data sets

After you have submitted your data, you are forwarded to a query result page showing the correspondence of submitted identifiers (from external databases, or obsolete UniProtKB identifiers) with current UniProtKB accession numbers. You can use the [basket](https://www.uniprot.org/help/basket), download and align services like in any query result, as well as [reconfigure the table layout](https://www.uniprot.org/help/customize) ("Columns") or add additional constraints to your query.

Jobs have unique **identifiers**, which (depending on the job type) can be used in queries (e.g. to get the intersection of two sequence similarity searches). Job identifiers and the related data are kept for 7 days, and are then deleted.

# Unmapped identifiers

The list of identifiers that could not be mapped can be retrieved for further inspection or analysis.

When mapping popular sequence database identifiers such as RefSeq, gi numbers, EMBL, EMBLCDS to UniProtKB, unmapped identifiers can be further mapped to [UniParc](https://www.uniprot.org/help/uniparc). This can be particularly useful for proteins from [redundant proteomes](https://www.uniprot.org/help/proteome_redundancy).

# Programmatic access

Code examples for programmatic access are available at [Programmatic access - Mapping database identifiers](https://www.uniprot.org/help/api_idmapping)

# Notes

- Very large mapping requests (&gt;50,000 identifiers) are likely to fail. Please do verify that your list does not contain any duplicates, and try to split it into smaller chunks (&lt;20,000) in case of problems. If you prefer to run your mapping locally, you can also [download the data underlying this service](https://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/idmapping/).

- For performance reasons, databases where the mapping relationship to UniProtKB identifiers is one-to-many, e.g. GO, InterPro or PubMed, are not supported. For limited lists of such identifiers, it is possible to query UniProtKB using the text search form with identifiers combined by "or", e.g. [(xref:interpro-IPR014000) OR (xref:interpro-IPR014002) OR (xref:interpro-IPR014003)](https://www.uniprot.org/uniprotkb?query=%28xref%3Ainterpro-IPR014000%29+OR+%28xref%3Ainterpro-IPR014002%29+OR+%28xref%3Ainterpro-IPR014003%29&fields=accession%2Cxref_interpro&view=table). One can then further use the Customize columns button to remove unwanted columns from the table view, or edit the query string (URL) by adding [&fields=accession,xref_interpro](https://www.uniprot.org/uniprotkb?query=%28xref%3Ainterpro-IPR014000%29+OR+%28xref%3Ainterpro-IPR014002%29+OR+%28xref%3Ainterpro-IPR014003%29&fields=accession%2Cxref_interpro&view=table). Finally, to download the results click the Download button where you can select the desired format.

See also: [Related questions from our FAQ](https://www.uniprot.org/help?query=%28batch%20OR%20%22id%20mapping%22%20OR%20%22upload%20lists%22%29)

Related terms: batch, bulk
