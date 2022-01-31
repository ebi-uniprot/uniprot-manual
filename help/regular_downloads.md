---
title: How can I download data at every UniProt release?
categories: UniProtKB,UniRef,UniParc,Download,Technical,Release,faq
---

If the data sets you need are available on our [ftp site](https://ftp.uniprot.org/pub/databases/uniprot/) , we recommend that you download them from there. Other data sets can be downloaded by querying this website (read [how to retrieve entries via queries programmatically](http://www.uniprot.org/help/api%5Fqueries) ), but please use a [tool](http://www.uniprot.org/help/api%5Fdownloading) that makes use of the HTTP protocol's `If-Modified-Since` header to avoid more than one download per release.

See also:

-   [Downloads](http://www.uniprot.org/downloads)
-   [How can I access resources on this website programmatically?](http://www.uniprot.org/help/programmatic%5Faccess)
-   [How frequently is UniProt released? What is the synchronization delay with other databases?](http://www.uniprot.org/help/synchronization)
-   [Downloaded data seems incomplete or corrupted - how can I get help with download problems?](http://www.uniprot.org/help/metalink)

Related terms: programmatic access, program, script, wget, curl, web services, API
