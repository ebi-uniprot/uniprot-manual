---
title: Calcium binding
categories: Function,manual
---

This subsection of the [Function](https://www.uniprot.org/help/function%5Fsection) section specifies the position(s) of the calcium-binding region(s) within the protein. One common calcium-binding motif is the EF-hand, but other calcium-binding motifs also exist.

### 1. Annotation of EF-hands {\#1\_\_Annotation\_of\_EF\_hands}

The EF-hand is a helix-loop-helix calcium-binding motif in which two helices pack together at an angle of approximately 90 degrees. The two helices are separated by a loop region where calcium actually binds. The "EF" notation for the motif is derived from the notation applied to the structure of parvalbumin, in which the "E" and "F" helices were originally identified as forming this calcium-binding motif.

During evolution, some EF-hand structures may have lost the ability to coordinate calcium. For this reason, we denote the boundaries of EF-hand motifs in the ['Domain'](https://www.uniprot.org/help/domain) subsection of the 'Family and Domains' section, while the actual calcium-binding regions are annotated in the 'Calcium binding' subsection.  
When a protein contains degenerate EF-hands which may have lost the ability to bind calcium, then the number of EF-hand domains will differ from the number of calcium-binding motifs.  
Example: [P05937](https://www.uniprot.org/uniprotkb/P05937#function)

Note that for EF-hand containing proteins at least one of the EF-hands must retain the ability to bind calcium for the keyword [Calcium](https://www.uniprot.org/keywords/106) to be present.

Additional information concerning for example, relative affinity for calcium, may also be indicated.  
Example: [P02639](https://www.uniprot.org/uniprotkb/P02639#function)

EF-hand motifs are routinely detected using the PROSITE profile [PS50222](http://prosite.expasy.org/PDOC00018), which covers the entire EF-hand and which also detects EF-hands that no longer retain the ability to bind calcium. A complementary pattern ( [PS00018](http://prosite.expasy.org/PDOC00018),) is used to determine whether the EF-hand has the ability to coordinate calcium. The consensus pattern for calcium-binding is:

    D-x-[DNS]-{ILVFYW}-[DENSTG]-[DNQGHRK]-{GP}-[LIVMC]-[DENQSTAGC]-x(2)-[DE]

Matches to this pattern within an EF-hand motif are annotated in the 'Calcium binding' subsection. We annotate the calcium-binding region from the first Asp residue to the last Asp/Glu residue in the pattern.  
Example: [Q96P71](https://www.uniprot.org/uniprotkb/Q96P71#function)

### 2. Annotation of other calcium-binding regions {\#2\_\_Annotation\_of\_other\_calcium\_binding\_regions}

We also annotate other known calcium-binding regions that are not EF-hands. The presence of such regions may have been determined experimentally.  
Example: [P15381](https://www.uniprot.org/uniprotkb/P15381#function)

Such information is propagated 'By similarity' to orthologous proteins.  
Example: [P22002](https://www.uniprot.org/uniprotkb/P22002#function)

In the following example the calcium-binding domain is structurally similar to that of EF-hand proteins, but is in two parts, with the last calcium ligand provided by a single distal residue.  
Example: [P23925](https://www.uniprot.org/uniprotkb/P23925#function)

Related keyword: [Calcium](https://www.uniprot.org/keywords/106).
