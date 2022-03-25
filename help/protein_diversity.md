---
title: How are protein sequence variety and protein diversity represented in UniProtKB?
categories: UniProtKB,Keywords,Text_search,Biocuration,Sequence,faq
---

The article [C. R. Biol. (2005)](http://dx.doi.org/10.1016/j.crvi.2005.06.001) ( [2008 version](http://education.expasy.org/CRB_2008.pdf) ) gives an overview on cellular processes that can lead to sequence variety and structural diversity in eukaryotes. It explains, with examples, how such processes are represented in UniProtKB.

This tutorial also shows how to use the UniProtKB annotation to extract specific datasets of entries, e.g.:

-   [proteins containing a selenocysteine](https://www.uniprot.org/uniprotkb/?query=keyword:712)
-   [proteins whose sequences are derived from a RNA editing event](https://www.uniprot.org/uniprotkb/?query=keyword:691)
-   [proteins containing a GPI-anchor](https://www.uniprot.org/uniprotkb/?query=keyword:336) ...

Remark: Most information in UniProtKB has one or several ['evidence tags'](https://www.uniprot.org/help/evidences) which describe the source of the information, e.g. an experiment that has been published in the scientific literature, an orthologous protein, a record from another database, etc.

Example of query:

-   [proteins phosphorylated on serine](https://www.uniprot.org/uniprotkb/?query=annotation%3A(type%3Amod_res+phosphoserine)) (Experimentally proven, predicted or propagated by similarity)
-   [proteins which have been experimentally proven to be phosphorylated on a serine](https://www.uniprot.org/uniprotkb/?query=annotation%3A(type%3Amod_res+phosphoserine+evidence%3Aexperimental)) ...

Note: Examples on the website might differ slightly from those printed in the article, due to [format changes](https://www.uniprot.org/news/) and updates to the annotation.

Related terms: post-translational modification, posttranslational modification, PTM, alternative splicing, variant, isoform, mRNA editing, ribosomal frameshifting.

See also:

-   [What is the canonical sequence? Are all isoforms described in one entry?](https://www.uniprot.org/help/canonical_and_isoforms)
-   [How do we manually annotate a UniProtKB entry?](https://www.uniprot.org/help/manual_curation)
-   [Alternative products](https://www.uniprot.org/help/alternative_products)
-   [Alternative sequence](https://www.uniprot.org/help/var_seq)
