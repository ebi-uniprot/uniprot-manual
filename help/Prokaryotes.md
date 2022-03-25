---
title: Prokaryotic protein annotation project
categories: biocuration,project
---

The Prokaryotic protein annotation project focuses on the manual annotation of bacterial and archaeal-specific proteins and protein families.

See: [How do we manually annotate a UniProtKB entry?](https://www.uniprot.org/faq/45)

Our major effort is currently directed towards the annotation of proteins from the already well-characterized model bacteria *[Escherichia coli](https://www.uniprot.org/taxonomy/83333)* and *[Bacillus subtilis](https://www.uniprot.org/taxonomy/224308)*, as well as the annotation of pathogens such as *[Mycobacterium tuberculosis](https://www.uniprot.org/taxonomy/1773)*.

-   All manually reviewed *Escherichia coli* entries can be found [here](https://www.uniprot.org/uniprotkb/?query=organism:83333+AND+reviewed:yes) [(statistics)](https://www.uniprot.org/biocuration%5Fproject/Prokaryotes/statistics#Escherichiacoli)
-   All manually reviewed *Bacillus subtilis* entries can be found [here](https://www.uniprot.org/uniprotkb/?query=organism:224308+AND+reviewed:yes) [(statistics)](https://www.uniprot.org/biocuration%5Fproject/Prokaryotes/statistics#Bacillussubtilis)
-   All manually reviewed *Mycobacterium tuberculosis* entries can be found [here](https://www.uniprot.org/uniprotkb/?query=organism:1773+AND+reviewed:yes) [(statistics)](https://www.uniprot.org/biocuration%5Fproject/Prokaryotes/statistics#Mycobacteriumtuberculosis)

### High-quality automated annotation propagation

Due to the quantity of data produced today thanks to next-generation sequencing and the ever increasing rate of genome sequencing, it is no longer possible to manually annotate even a small portion of these genomes, despite the considerable demand for corrected and annotated proteomes. To enrich their annotation in UniProtKB, we developed [HAMAP](http://hamap.expasy.org/) (High-quality Automated and Manual Annotation of Proteins), whose goal is to automatically annotate a significant percentage of the huge amount of proteins originating from genome sequencing projects. This automatic annotation pipeline, based on a collection of family profiles and manually created annotation rules, is only applied in cases where it can produce the same quality as manual annotation would, that is for proteins that are part of well-defined families or subfamilies. By this we mean protein families which have a well-defined function and which are well conserved at the sequence level.
