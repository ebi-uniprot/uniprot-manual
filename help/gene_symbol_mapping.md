---
title: Can I convert gene symbols to UniProtKB identifiers? How can I map UniProtKB IDs or ACs to gene symbols?
type: help
categories: UniProtKB,Text_search,Names_and_taxonomy,Website,faq
---

1.  **UniProtKB AC/ID to gene symbols**

    You can upload your list of UniProtKB identifiers (AC or ID) to the batch retrieval service ("Retrieve/ID mapping"). Then click on the link "UniProtKB(xx)" ("xx" being the number of entries in your result) and then on "Columns" to hide all columns except gene names. In the resulting page, click on "Download" and select the tab-separated format. To show only the recommended gene names (or only synonyms, ordered locus names (OLN) or ORF names) you can edit the URL and replace `'genes'` by one of the following:

        genes(PREFERRED)
        genes(ALTERNATIVE)
        genes(OLN)
        genes(ORF)

    See also

    - [Gene names](https://www.uniprot.org/help/gene%5Fname)

2.  **gene symbols to UniProtKB identifiers**

    If your genes are all from an organism for which a model organism database exists and is cross-referenced to UniProtKB (e.g. HGNC, MGI, FlyBase), it is possible to retrieve all the UniProtKB entries for your genes if you have the corresponding remote database identifiers: You can upload this list to our server under [Retrieve/ID mapping](https://www.uniprot.org/uploadlists), and map the identifiers from that remote database to UniProtKB.

    See also

    - [Organism-specific databases](https://www.uniprot.org/database/?query=category:%22Organism-specific+databases%22)
    - [Database identifier mapping (via 'Retrieve/ID mapping')](https://www.uniprot.org/help/uploadlists)
    - [Cross-references](https://www.uniprot.org/help/cross%5Freferences%5Fsection)

    The identifier mapping service also has an option "Gene name" where you can submit your list of gene symbols and optionally specify an organism. Note that mapping results can also be filtered after submission, e.g. by organism or reviewed/unreviewed status.

    Alternatively, to retrieve all entries corresponding to your query, you could build yourself a query string by concatenating all your gene names with `'or'` and prefixing them by `'gene:'` or `'gene_exact:'`. This can be done with a simple script or even using "find and replace" in a text processing program:

        gene_exact:BRAF or
        gene_exact:BRCA1 or
        gene_exact:BRCA2 or
        gene_exact:BTK or
        gene_exact:CASP10 or
        gene_exact:CASP8 or
        etc.

    Prefix this with your organism criteria, e.g. `'organism:"homo sapiens"'` and `'reviewed:true'` if you wish to restrict your results to reviewed UniProtKB/Swiss-Prot entries, or `'keyword:KW-1185'` to restrict to a reference proteome.

    [organism:"homo sapiens" and (gene_exact:braf or gene_exact:brca1 or gene_exact:brca2 or gene_exact:btk or gene_exact:casp10 or gene_exact:casp8) and reviewed:true](https://www.uniprot.org/uniprotkb/?query=organism%3A%22homo+sapiens%22+and+%28gene_exact%3Abraf+or+gene_exact%3Abrca1+or+gene_exact%3Abrca2+or+gene_exact%3Abtk+or+gene_exact%3Acasp10+or+gene_exact%3Acasp8%29%20and%20reviewed%3Atrue&sort=score)

    You can use the "Columns" button and [customize](https://www.uniprot.org/help/customize) your result table to show only gene names and UniProtKB identifiers, and then download the table (see 1. above).

    With long query strings, you may reach supported query string length limits. Should you run into problems (e.g. empty pages) please consider making POST requests, or splitting up your query.

    See also

    - [REST API - Access the UniProt website programmatically](https://www.uniprot.org/help/api)
    - [Programmatic access - Mapping database identifiers](https://www.uniprot.org/help/api%5Fidmapping)
    - [Customize display options](https://www.uniprot.org/help/customize)
