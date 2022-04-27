---
title: How can I get all green plant entries integrated in UniProtKB since release 12.0?
type: help
categories: UniProtKB,Text_search,Release,faq
---

1.  Go to the [news archive](https://www.uniprot.org/news) and find the date of the UniProt release under consideration, e.g. Release 12.0 was published on July 24, 2007
2.  Use the query builder as described below.

Retrieve all green plant entries:

- Select **Search in** : `Protein Knowledgebase (UniProtKB)`
- Click **Advanced** to open the query builder
- Select **Field** : `Taxonomy [OC]`
- Type `Viridiplantae` (use autocompletion)

Restrict results to data integrated since release 12.0:

- Select **Field** : `Date of` - `Date of creation`
- Type **From** : `20070724`
- Click **Search**

You can choose to view only [reviewed](https://www.uniprot.org/uniprot?query=taxonomy:viridiplantae+created:%5B20070724+TO+%2A%5D+reviewed:true) (UniProtKB/Swiss-Prot) or [unreviewed](https://www.uniprot.org/uniprot?query=taxonomy:viridiplantae+created:%5B20070724+TO+%2A%5D+reviewed:false) (UniProtKB/TrEMBL) entries.

Note that the date can be modified in the query box 'taxonomy:Viridiplantae AND created:\[20070724 TO \*\]' and that you can bookmark the result page.

# See also

- [How do I get automatically notified of updates to UniProtKB?](https://www.uniprot.org/help/update%5Fnotification)
- [How do I link to a specific version of a UniProtKB entry?](https://www.uniprot.org/help/link%5Fold%5Fversions)
- [What are the date formats accepted in the relevant fields of the query builder (e.g. UniProtKB date integrated/date modified)?](https://www.uniprot.org/help/date%5Fformats/)
- [UniProtKB advanced search options](https://www.uniprot.org/help/advanced%5Fsearch)
