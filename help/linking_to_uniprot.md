---
title: How to link to UniProt entries (UniProtKB, UniParc and UniRef)
categories: UniProtKB,UniRef,UniParc,Technical,faq
---

### Standard format

The standard way of linking to UniProt databases, displaying the UniProt HTML view is:

`https://www.uniprot.org/dataset/identifier`

where the value of `dataset` is either uniprot, uniparc or uniref

Examples:

-   [https://www.uniprot.org/uniprot/P99999](https://www.uniprot.org/uniprotkb/P99999)
-   [https://www.uniprot.org/uniref/UniRef100\_P99999](http://www.uniprot.org/uniref/UniRef100%5FP99999) (cf remark 2)
-   [https://www.uniprot.org/uniref/UniRef90\_P99999](http://www.uniprot.org/uniref/UniRef90%5FP99999) (cf remark 2)
-   [https://www.uniprot.org/uniref/UniRef50\_P99999](http://www.uniprot.org/uniref/UniRef50%5FP99999) (cf remark 2)
-   [https://www.uniprot.org/uniparc/UPI00000002E4](http://www.uniprot.org/uniparc/UPI00000002E4)

Remarks:

1.  A UniProtKB accession number (AC) is a stable identifier and therefore allows unambiguous citation of a UniProtKB entry. This is not the case for the 'Entry name'. (see [What is the difference between an accession number (AC) and the entry name?](http://www.uniprot.org/help/difference%5Faccession%5Fentryname). It is recommended to always link to a UniProtKB entry by its primary accession number.
2.  The UniRef identifiers (e.g. UniRef50\_P99999) are not stable. These identifiers consist of the cluster resolution (UniRef50, 90 or 100) and the accession number of the representative. As clusters are recomputed at every release, the representatives may change.  
      
    How to link to the UniRef50 cluster containing a given UniProtKB entry, e.g. P99999: <https://www.uniprot.org/uniref/?query=member:P99999+AND+identity:0.5>  
      
    How to link to the UniRef90 cluster containing a given UniProtKB entry, e.g. P99999: <https://www.uniprot.org/uniref/?query=member:P99999+AND+identity:0.9>  
      
    How to link to the UniRef100 cluster containing a given UniProtKB entry, e.g. P99999: <https://www.uniprot.org/uniref/?query=member:P99999+AND+identity:1.0>

### Other formats

Additional formats for entries and queries can be displayed by adding an extension to the URL:

`https://www.uniprot.org/dataset/identifier.format`

The following `format` values are valid:

    txt    = flat file view (*)
    xml    = xml format
    fasta  = fasta format
    rdf    = rdf format
    gff    = gff format (*)
    tab    = tab-separated format (**)

`(*)` = not available for UniRef or UniParc

`(**)` = not available for UniProtKB

Examples:

-   [https://www.uniprot.org/uniprot/P99999.txt](https://www.uniprot.org/uniprotkb/P99999.txt)
-   [https://www.uniprot.org/uniref/UniRef100\_P99999.xml](https://www.uniprot.org/uniref/UniRef100%5FP99999.xml)
-   [https://www.uniprot.org/uniprot/P99999.fasta](https://www.uniprot.org/uniprotkb/P99999.fasta)
-   <https://www.uniprot.org/uniparc/UPI00000002E4.rdf>
-   [https://www.uniprot.org/uniprot/P99999.gff](https://www.uniprot.org/uniprotkb/P99999.gff)
-   [https://www.uniprot.org/uniref/UniRef100\_P99999.tab](https://www.uniprot.org/uniref/UniRef100%5FP99999.tab)
-   <https://www.uniprot.org/uniparc/UPI00000002E4.tab>

Note that all individual records and queries are accessible using simple URLs (REST). All pages (in particular query results) can therefore be bookmarked and linked. Example: [https://www.uniprot.org/uniprot/?query=gene:at2g37710](https://www.uniprot.org/uniprotkb/?query=gene:at2g37710)

See also:

-   [REST API - Access the UniProt website programmatically](http://www.uniprot.org/help/api)
-   [Accession number](https://www.uniprot.org/help/accession%5Fnumbers)
-   [How do I link to a specific version of a UniProtKB entry?](http://www.uniprot.org/help/link%5Fold%5Fversions)
