---
title: Do I still need to use the Sequence Retrieval System (SRS)?
categories: UniProtKB,UniParc,UniRef,Text_search,faq
---

The UniProt search tool allows users to perform Google and SRS-like queries, on UniProtKB, UniRef and UniParc [\*](http://www.uniprot.org/#note-uniparc) . Note that it is also possible to upload a list of accession numbers and then perform a search in that subset.

Example: **Search for Saccharomyces cerevisiae membrane glycoproteins in UniProtKB**

**Google-like queries**

-   Click the **Search** tab of the toolbar
-   Select `UniProtKB` from the main search menu
-   Type `Saccharomyces cerevisiae membrane glycoprotein` in the Query box
-   Click on the search button
-   Follow the suggestions proposed by the search tool, and use the [filter options](http://www.uniprot.org/help/filters) :
    -   Quote terms `"saccharomyces cerevisiae"`
    -   Use the **S.cerevisiae** filter under "Popular organisms"
    -   Filter `"membrane"` as `keyword`
    -   Filter `"glycoprotein"` as `keyword`
-   [Results](https://www.uniprot.org/uniprotkb/?query=organism%3A%22saccharomyces+cerevisiae%22+AND+keyword%3Amembrane+AND+keyword%3Aglycoprotein)
-   Click **Columns** to choose the columns to show in the result table
-   This URL can be bookmarked.

**SRS-like queries ( [Advanced search](http://www.uniprot.org/help/advanced_search) )**

-   Select `UniProtKB` from the search menu
-   Click **Advanced** to open the query builder
    -   Select `Taxonomy -> Organism [OS]` and type `saccharomyces cerevisiae` (use autocompletion)
    -   Select `Ontology -> Keyword [KW]` and type `Membrane` (use autocompletion)
    -   Select `Ontology -> Keyword [KW]` and type `Glycoprotein` (use autocompletion)
    -   Click on the search button
-   [Results](https://www.uniprot.org/uniprotkb/?query=organism%3A%22saccharomyces+cerevisiae%22+AND+keyword%3A%22Membrane+%5B472%5D%22+AND+keyword%3A%22Glycoprotein+%5B325%5D%22)
-   Click **Columns** to choose the columns to show in the result table
-   This URL can be bookmarked.

**Queries on your personal UniProt dataset**

-   Click on [Retrieve/ID mapping](http://www.uniprot.org/uploadlists) in the toolbar

-   Copy/paste your list of accession numbers (i.e. P38903 P47096 P40433 P31787 P28240 P32465 P28319)

-   Click **Retrieve**

-   Click the `UniProtKB` link

-   Click **Advanced** to open the query builder

    You can now add search criteria to get a specific subset of entries (i.e. Glycoprotein, Membrane, 3D-structure...).

-   Click **Columns** to choose the columns to show in the result table

\* Note that UniParc can be searched only with database names, taxonomy, checksum (CRC64) and accession numbers (ACs) or UniProtKB, UniRef and UniParc IDs.

Examples:

-   [Search UniParc with P12345](http://www.uniprot.org/uniparc/?query=P12345)
-   [Search UniParc with TaxID for Eukaryota](http://www.uniprot.org/uniparc/?query=taxonomy:2759)
-   [Search UniParc with taxonomy term Eukaryota](http://www.uniprot.org/uniparc/?query=taxonomy:Eukaryota)
