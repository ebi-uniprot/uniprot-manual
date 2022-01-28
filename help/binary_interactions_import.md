
---
title: Why are only a subset of binary interactions from the IntAct database reported in UniProtKB?
categories: UniProtKB,Interaction,faq
---

The imported subset of binary interactions is determined using a simple scoring system developed by [IntAct](http://www.ebi.ac.uk/intact/main.xhtml) and a score threshold that has been deliberately chosen to exclude interactions supported by only one experimental observation. Details of how interactions are scored can be found at the [IntAct website](http://www.ebi.ac.uk/intact/pages/faq/faq.xhtml#4).

This simple score-based filter is used in combination with a set of defined rules that exclude certain types of data, such as interactions that are only ever observed in larger complexes, or interactions that have been inferred but not experimentally proven. These stringent criteria reduce the amount of interaction data that is imported into UniProtKB, which is composed solely of experimentally proven binary interactions supported by multiple observations.

See also:

*   [Binary interactions](http://www.uniprot.org/manual/binary_interactions)
        