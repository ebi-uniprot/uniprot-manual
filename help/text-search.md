---
title: Text search
categories: Website,Technical,Text_search,Programmatic_access,help
---

You can use the search bar in the UniProt banner at the top of all pages to search the various data sets provided by the UniProt Consortium. There is a drop-down list that allows to select the data set.

To search one of the UniProt resources proceed as follows:

1.  select the appropriate data set (the default selection is UniProtKB),
2.  type in your query and
3.  hit the search button.

Note that the background color around the search field changes depending on the data set, in order to keep you aware of the selected data set.

**Query syntax**

Here is a brief overview of the supported query syntax (see also [query fields for UniProtKB](http://www.uniprot.org/help/query-fields) ):

|                                                                                                                           |                                                                                                                                                                                                                                                                                                                                      |
|:--------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [human antigen](https://www.uniprot.org/uniprotkb/?query=human%20antigen)                                                 | All entries containing both terms.                                                                                                                                                                                                                                                                                                   |
| [human AND antigen](https://www.uniprot.org/uniprotkb/?query=human%20AND%20antigen)                                       |                                                                                                                                                                                                                                                                                                                                      |
| [human && antigen](https://www.uniprot.org/uniprotkb/?query=human%20%26%26%20antigen)                                     |                                                                                                                                                                                                                                                                                                                                      |
| ["human antigen"](https://www.uniprot.org/uniprotkb/?query=%22human%20antigen%22)                                         | All entries containing both terms in the exact order.                                                                                                                                                                                                                                                                                |
| [human -antigen](https://www.uniprot.org/uniprotkb/?query=human%20-antigen)                                               | All entries containing the term 'human' but not 'antigen'.                                                                                                                                                                                                                                                                           |
| [human NOT antigen](https://www.uniprot.org/uniprotkb/?query=human%20NOT%20antigen)                                       |                                                                                                                                                                                                                                                                                                                                      |
| [human !antigen](https://www.uniprot.org/uniprotkb/?query=human%20!antigen)                                               |                                                                                                                                                                                                                                                                                                                                      |
| [human OR mouse](https://www.uniprot.org/uniprotkb/?query=human%20OR%20mouse)                                             | All entries containing either term.                                                                                                                                                                                                                                                                                                  |
| [human \|\| mouse](https://www.uniprot.org/uniprotkb/?query=human%20%7C%7C%20mouse)                                       |                                                                                                                                                                                                                                                                                                                                      |
| [antigen AND (human OR mouse)](https://www.uniprot.org/uniprotkb/?query=antigen%20AND%20%28human%20OR%20mouse%29)         | Using parentheses to override boolean precedence rules.                                                                                                                                                                                                                                                                              |
| [anti\*](https://www.uniprot.org/uniprotkb/?query=anti%2A)                                                                | All entries containing terms starting with 'anti'. Asterisks can also be used at the beginning and within terms. **Note:** Terms starting with an asterisk or a single letter followed by an asterisk can slow down queries considerably.                                                                                            |
| [author:Tiger\*](https://www.uniprot.org/uniprotkb/?query=author:Tiger%2A)                                                | Citations that have an author whose name starts with 'Tiger'. To search in a specific field of a dataset, you must prefix your search term with the field name and a colon. To discover what fields can be queried explicitly, observe the query hints that are shown after submitting a query or use the query builder (see below). |
| [length:\[100 TO \*\]](https://www.uniprot.org/uniprotkb/?query=length:%5B100%20TO%20%2A%5D)                              | All entries with a sequence of at least 100 amino acids.                                                                                                                                                                                                                                                                             |
| [citation:(author:Arai author:Chung)](https://www.uniprot.org/uniprotkb/?query=citation:%28author:Arai%20author:Chung%29) | All entries with a publication that was coauthored by two specific authors.                                                                                                                                                                                                                                                          |

To use characters that have a special meaning in the query syntax literally in your query, you must escape them with a backslash, e.g. use ['gene:L\\(1\\)2CB'](https://www.uniprot.org/uniprotkb/?query=gene:L%5C(1%5C)2CB) to search for the gene name 'L(1)2CB'. The current list of special characters is:

`+ - && || ! ( ) { } [ ] ^ " ~ * ? : \\`

**Query builder**

You can also access [advanced search options](http://www.uniprot.org/help/advanced%5Fsearch) by clicking on *'Advanced'* , e.g. to restrict terms to specific fields in advance or to combine multiple terms using boolean logic. Depending on the chosen data set and field, you can enter some text or choose values from various levels of drop-down lists. Then click the search button ("looking glass" icon) to run the query.

The advanced search interface allows to browse the different search fields and options within the dropdown menus. There is a search box right at the top when you open the blue dropdown menu that allows you to type a concept name (e.g. 'structure') and receive some autocompleted suggestions from which you can then select the most suitable one:

![image](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/text-search-15.png)

See also:

-   [Search tips from our FAQ](http://www.uniprot.org/help/?query=section%3Afaq+AND+category%3A%22Text%20search%22)
-   [UniProtKB tutorial/video](https://www.youtube.com/watch?v=ado1r8IDm3U)
-   [Advanced search options](http://www.uniprot.org/help/advanced%5Fsearch)
-   [Customize display options](http://www.uniprot.org/help/customize)
-   [Query fields for UniProtKB](http://www.uniprot.org/help/query-fields)
