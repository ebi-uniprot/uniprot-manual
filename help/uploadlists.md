---
title: Retrieve / ID mapping
categories: Website,help
---

[Tutorial/Video](https://www.youtube.com/watch?v=kLdgjqWoMZc)

Select the **Retrieve/ID mapping** tab of the toolbar and enter or upload a list of identifiers (or gene names) to do one of the following:

-   Retrieve the corresponding UniProt entries to download them or work with them on this website.
-   Convert identifiers which are of a different type to UniProt identifiers or vice versa, and download the identifier lists.

#### How to use this tool

1.  Enter identifiers or upload them from a file, separated by a space or a new line, into the form field, for example: P31946 P62258 ALBU\_HUMAN
2.  If you need to convert to another identifier type (as performed previously by the "ID mapping" service), select the source and target type from the "From/To" dropdown menus under "Options". Otherwise, to retrieve or download a list UniProtKB entries, keep the default selection of these menus (from UniProtKB AC/ID to UniProtKB)
3.  Click the **Submit** button.

The following kinds of UniProt identifiers are supported:

|           |                       |                                  |
|:----------|:----------------------|:---------------------------------|
| UniProtKB | P00750                | UniProtKB entry                  |
|           | P00750 -2             | UniProtKB entry isoform sequence |
|           | P00750 \[39-81\]      | UniProtKB sequence range         |
|           | **A4\_HUMAN**         | UniProtKB entry name             |
| UniParc   | UPI0000000001         | UniParc entry                    |
| UniRef    | **UniRef100\_P00750** | UniRef entry                     |

When mapping from a source database external to UniProt, you can submit any identifier as used in the UniProtKB [cross-references](http://www.uniprot.org/help/cross%5Freferences%5Fsection). If your job is not successful and you are not sure which source database to use, try a text search in UniProtKB with one of your identifiers, and look at an example entry. Check out the cross-reference section to find out which database uses these identifiers.

#### Further queries involving your UniProtKB data sets

After you have submitted your data, you are forwarded to a query result page showing the correspondence of submitted identifiers (from external databases, or obsolete UniProtKB identifiers) with current UniProtKB accession numbers. You can use the [basket](http://www.uniprot.org/help/basket), download and align services like in any query result, as well as [reconfigure the table layout](http://www.uniprot.org/help/customize) ("Columns") or add additional constraints to your query.

Jobs have unique **identifiers**, which (depending on the job type) can be used in queries (e.g. to get the intersection of two sequence similarity searches). Job identifiers and the related data are kept for 7 days, and are then deleted.

#### Unmapped identifiers

The list of identifiers that could not be mapped can be retrieved for further inspection or analysis.

When mapping popular sequence database identifiers such as RefSeq, gi numbers, EMBL, EMBLCDS to UniProtKB, unmapped identifiers can be further mapped to [UniParc](http://www.uniprot.org/help/uniparc). This can be particularly useful for proteins from [redundant proteomes](http://www.uniprot.org/help/proteome%5Fredundancy) .

#### Programmatic access

Code examples for programmatic access are available in the relevant API help pages:  
[Programmatic access - Mapping database identifiers](http://www.uniprot.org/help/api%5Fidmapping)  
[Programmatic access - Batch retrieval of entries](http://www.uniprot.org/help/api%5Fbatch%5Fretrieval)

#### Notes

-   Very large mapping requests (&gt;50,000 identifiers) are likely to fail. Please do verify that your list does not contain any duplicates, and try to split it into smaller chunks (&lt;20,000) in case of problems. If you prefer to run your mapping locally, you can also [download the data underlying this service](https://ftp.uniprot.org/pub/databases/uniprot/current%5Frelease/knowledgebase/idmapping/) .

<!-- -->

-   For performance reasons, databases where the mapping relationship to UniProtKB identifiers is one-to-many, e.g. GO, InterPro or PubMed, are not supported. For limited lists of such identifiers, it is possible to query UniProtKB using the text search form with identifiers combined by "or", e.g. ["interpro IPR014000" OR "interpro IPR014002" OR "interpro IPR014003"](https://www.uniprot.org/uniprotkb/?query=%22interpro+IPR014000%22+or+%22interpro+IPR014002%22+or+%22interpro+IPR014003%22). One can then further use the [Columns](http://www.uniprot.org/help/customize) button to remove unwanted columns from the table view, or edit the query string (URL) to add "&columns=id,database(interpro)" to it. The same addition can be made to the URL for download of the tab-separated view, e.g. [/uniprot/?query=%22interpro+IPR014000%22+or+%22interpro+IPR014002%22+or+%22interpro+IPR014003%22&format=tab&columns=id,database(interpro)](https://www.uniprot.org/uniprotkb/?query=%22interpro+IPR014000%22+or+%22interpro+IPR014002%22+or+%22interpro+IPR014003%22&format=tab&columns=id,database(interpro)) .

See also: [Related questions from our FAQ](http://www.uniprot.org/help/?query=(batch+OR+%22id+mapping%22+OR+%22upload+lists%22)+AND+section%3Afaq)

Related terms: batch, bulk
