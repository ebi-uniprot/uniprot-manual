---
title: Programmatic access - Retrieving entries via queries
categories: UniProtKB,UniRef,UniParc,Programmatic_access,Text_search,Technical,help
---

You can use any query to define the set of entries that you are interested in. Best start with an interactive [text search](http://www.uniprot.org/help/text-search) to find the base URL for your set, e.g. all reviewed human entries:

    https://www.uniprot.org/uniprot/?query=reviewed:yes+AND+organism:9606

or all reviewed entries that were created in the current UniProtKB/Swiss-Prot release:

    https://www.uniprot.org/uniprot/?query=reviewed:yes+AND+created:[current TO *]

There are several ways of obtaining the URL corresponding to your query for programmatic use:

-   The URL for the html format with the default column setup can always be found in the browser's location bar.
-   For alternative formats (e.g. fasta, tab-separated), you can click on **Download** to explore the various download formats available for your query. You can request a preview by selecting a format and clicking on **Preview first 10** . In that case, the browser's location bar will contain the URL corresponding to your query and format selections, provided that it is not longer than 1000 characters. All you will have to do before using the URL programmatically is to remove the "&limit=10" part.
-   The **Share** button gives access to the base URL for your query with all the columns in your web view (see also [Customise and share your search results](https://insideuniprot.blogspot.com/2015/03/) ). The URL is shown irrespective of its length, even if it may exceed the limitation for the length of GET requests (dependent on client and server software). The default format that this URL generates is the HTML view format. To define a download format, you can append the format of your choice to the URL (i.e. &format=). The table below describes the parameters that you can append to your base URL to retrieve the entries in this format. For example, if you wanted to download the UniProtKB results for 'insulin' with the default columns in tab-separated format:

<!-- -->

    https://www.uniprot.org/uniprot/?query=insulin&sort=score&columns=id,entry name,reviewed,protein names,genes,organism,length&format=tab  

**Tips** :

-   Get familiar with the [query builder](http://www.uniprot.org/help/advanced%5Fsearch) (advanced search form) by clicking on **Advanced** .
-   Click [**Columns**](http://www.uniprot.org/help/customize) on the search results page to select the columns for retrieving result tables in tab-separated or Excel format.
-   You can also look up your relevant column names in the full list of [UniProtKB column names for programmatic access](http://www.uniprot.org/help/uniprotkb%5Fcolumn%5Fnames) .

The URL for a query result consists of a data set name (e.g. `uniprot` , `uniref` , `uniparc` , `taxonomy` , ...) and the actual query. The following query parameters are supported:

<table><colgroup><col style="width: 10%" /><col style="width: 33%" /><col style="width: 55%" /></colgroup><thead><tr class="header"><th>Parameter</th><th>Values</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>query</code></td><td><em>string</em></td><td>See <a href="http://www.uniprot.org/help/text-search">query syntax</a><br />
and <a href="http://www.uniprot.org/help/query-fields">query fields for UniProtKB</a> .<br />
An empty query string will retrieve all entries in a data set. <strong>Tip:</strong> Click <strong>Advanced</strong><br />
in the search bar.</td></tr><tr class="even"><td><code>format</code></td><td><code>html | tab | xls | fasta | gff | txt | xml | rdf | list | rss</code></td><td><p>Format in which to return results:</p><ul><li><code>tab</code> returns data for the selected <code>columns</code> in tab-separated format.</li><li><code>xls</code> returns data for the selected <code>columns</code> for import into Excel.</li><li><code>fasta</code> returns sequence data only, where applicable.</li><li><code>gff</code> returns sequence annotation, where applicable.</li><li><code>txt</code> , <code>xml</code> and <code>rdf</code> return full entries.</li><li><code>list</code> returns a list of identifiers.</li><li><code>rss</code> returns an <a href="http://opensearch.a9.com/">OpenSearch</a> RSS feed.</li></ul><p><strong>Tip:</strong> Click <code>Download</code> above the list of results.</p></td></tr><tr class="odd"><td><code>columns</code></td><td>comma-separated list of column names</td><td>Columns to select for retrieving results in <code>tab</code> or <code>xls</code> format.<br />
Click <strong>Columns</strong> on the search results page to see the available columns<br />
(for UniProtKB you can also read the <a href="http://www.uniprot.org/help/uniprotkb_column_names">full list of UniProtKB column names</a> ).<br />
<strong>Tip:</strong> Some columns can be parameterized, e.g. <code>database(PDB)</code> (see the example at the end of this section).</td></tr><tr class="even"><td><code>include</code></td><td><code>yes | no</code></td><td>Include isoform sequences when the <code>format</code> parameter is set to <code>fasta</code> .<br />
Include description of referenced data when the <code>format</code> parameter is set to <code>rdf</code> .<br />
This parameter is ignored for all other values of the <code>format</code> parameter.</td></tr><tr class="odd"><td><code>compress</code></td><td><code>yes | no</code></td><td>Return results gzipped. Note that if the client supports HTTP compression,<br />
results may be compressed transparently even if this parameter is<br />
not set to <code>yes</code> .</td></tr><tr class="even"><td><code>limit</code></td><td><em>integer</em></td><td>Maximum number of results to retrieve.</td></tr><tr class="odd"><td><code>offset</code></td><td><em>integer</em></td><td>Offset of the first result, typically used together with<br />
the <code>limit</code> parameter.</td></tr></tbody></table>

The following example retrieves all human entries matching the term ' `antigen` ' in RDF/XML and tab-separated format, respectively.

    https://www.uniprot.org/uniprot/?query=organism:9606+AND+antigen&format=rdf&compress=yes

    https://www.uniprot.org/uniprot/?query=organism:9606+AND+antigen&format=tab&compress=yes&columns=id,reviewed,protein names

The next example retrieves all human entries with cross-references to PDB in tab-separated format, showing only the UniProtKB and PDB identifiers.

    https://www.uniprot.org/uniprot/?query=organism:9606+AND+database:pdb&format=tab&compress=yes&columns=id,database(PDB)

See also:

-   [REST API - Access the UniProt website programmatically](http://www.uniprot.org/help/api)
-   \- batch retrieval, ID mapping, queries, downloads, etc

Related terms: programmatic access, program, script, wget, curl, web services, API
