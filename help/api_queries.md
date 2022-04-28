---
title: Programmatic access - Retrieving entries via queries
type: help
categories: UniProtKB,UniRef,UniParc,Programmatic_access,Text_search,Technical,help
---

You can use any query to define the set of entries that you are interested in. It is perhaps simplest to start with an interactive [text search](https://www.uniprot.org/help/text%2Dsearch) to find the URL for your set, e.g., all reviewed human entries:

```bash
https://rest.uniprot.org/uniprotkb/search?query=reviewed:true+AND+organism_id:9606
```

The data for the website is provided by our REST API. For the above example, the REST request is:

```bash
https://rest.uniprot.org/uniprotkb/search?query=reviewed:true+AND+organism_id:9606
```

# Formats

Formats for search results / an entry can be requested in several ways.

## Format Parameter

All requests allow the `format` parameter, which can be used to indicate the desired format. For example:

```bash
# TAB SEPARATED VALUES
"https://rest.uniprot.org/uniprotkb/search?query=reviewed:true+AND+organism_id:9606&format=tsv"

# XML
"https://rest.uniprot.org/uniprotkb/P12345?format=xml"
```

## Accept Header

As is typical with REST requests, the desired format can be specified as an Accept header. For example:

```bash
# TAB SEPARATED VALUES
curl -H "Accept: text/plain; format=tsv" "https://rest.uniprot.org/uniprotkb/search?query=reviewed:true+AND+organism_id:9606"

# XML
curl -H "Accept: application/xml" "https://rest.uniprot.org/uniprotkb/P12345"
```

# What formats are available?

The different end-points in our API provide different formats, though generally, JSON and tab-separated-values formats (TSV) are
available throughout.

## List of all formats

| Description                                                            | Accept Header Media Type    | Format Parameter |
| ---------------------------------------------------------------------- | --------------------------- | ---------------- |
| JavaScript Object Notation (JSON)                                      | application/json            | json             |
| Extensible Markup Language (XML)                                       | application/xml             | xml              |
| Text file representation                                               | text/plain; format=flatfile | txt              |
| List of one or more IDs                                                | text/plain; format=list     | list             |
| Tab-Separated-Values                                                   | text/plain; format=tsv      | tsv              |
| FASTA: a text-based format representing nucleotide / peptide sequences | text/plain; format=fasta    | fasta            |
| Genomic Feature Format (GFF)                                           | text/plain; format=gff      | gff              |
| Open Biomedical Ontologies (OBO)                                       | text/plain; format=obo      | obo              |
| Resource Description Framework (RDF)                                   | application/rdf+xml         | rdf              |
| Excel                                                                  | application/vnd.ms-excel    | xlsx             |

Some examples are given in the following:

```bash
## Accept header
curl -H "Accept: text/plain; format=flatfile" "https://rest.uniprot.org/uniprotkb/P12345"

## Format Parameter
curl "https://rest.uniprot.org/uniprotkb/search?query=human&format=gff"
```

# Tips

- Familiarise oneself with the [advanced search builder](http://www.uniprot.org/help/advanced_search) by clicking on **Advanced**.
- Click [Customize data](http://www.uniprot.org/help/customize) on the search results page to select the columns to show in the results table.
- You can also look up your relevant column names in the full list of [UniProtKB column names for programmatic access](http://www.uniprot.org/help/uniprotkb_column_names).

The URL for a query result consists of a data set name (e.g. `uniprot`, `uniref`, `uniparc`, `taxonomy`,...) and the actual query. The following query parameters are supported:

| Parameter        | Values                                     | Description                                                                                                                                                                                                                                                                              |
| ---------------- | ------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `query`          | _string_                                   | See [query syntax](https://www.uniprot.org/help/text-search) <br> and [query fields for UniProtKB](http://www.uniprot.org/help/query-fields). <br>An empty query string will retrieve all entries in a data set. **Tip:** Refine your search by clicking **Advanced** in the search bar. |
| `format`         | See section, "What formats are available?" | See section, "What formats are available?"                                                                                                                                                                                                                                               |
| `fields`         | comma-separated list of column names       | Columns to retrieve in the results. Applies to `tsv`, `xslx` and `json` formats only. <br>(For UniProtKB you can also read the [full list of UniProtKB column names](https://www.uniprot.org/help/uniprotkb_column_names)).                                                              |
| `includeIsoform` | `true` or `false`                          | Whether or not to include isoforms in the search results. _Note:_ Only applies to UniProtKB searches.                                                                                                                                                                                    |
| `compressed`     | `true` or `false`                          | Return results gzipped. Note that if the client supports HTTP compression, results may be compressed transparently even if this parameter is not set to `true`.                                                                                                                          |
| `size`           | _integer_                                  | Maximum number of results to retrieve. _Note:_ Only takes effect on searches.                                                                                                                                                                                                            |
| `cursor`         | _string_                                   | Specifies the cursor position in the entire result set, from which returned results will begin. Cursors are used to allow paging through results. Typically used together with the `size` parameter.                                                                                     |

The following example retrieves all human entries matching the term '`antigen`' in compressed JSON and tab-separated-values formats, respectively.

```bash
https://rest.uniprot.org/uniprotkb/search?query=organism_id:9606+AND+antigen&format=json&compressed=true
https://rest.uniprot.org/uniprotkb/search?query=organism_id:9606+AND+antigen&format=tsv&compressed=true
```

The next example retrieves all human entries with cross-references to PDB in tab-separated format, showing only the UniProtKB and PDB identifiers.

https://rest.uniprot.org/uniprotkb/search?query=organism_id:9606+AND+database:pdb&format=tsv&fields=id,xref_pdb
