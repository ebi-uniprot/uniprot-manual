
---
title: Topological domain
categories: Subcellular_location,manual
---

This subsection of the ['Subcellular location'](http://www.uniprot.org/help/subcellular%5Flocation%5Fsection) section describes the subcellular compartment where each non-membrane region of a membrane-spanning protein is found.

Topological domains are annotated according to a controlled vocabulary, the elements of which are listed below.

**Common topological domains**

*   Chloroplast intermembrane
*   Cytoplasmic
*   Extracellular
*   Intravacuolar
*   Intravirion
*   Lumenal
*   Lumenal, thylakoid
*   Lumenal, vesicle
*   Mitochondrial intermembrane
*   Mitochondrial matrix
*   Periplasmic
*   Peroxisomal
*   Peroxisomal matrix
*   Nuclear
*   Perinuclear space
*   Stromal
*   Vacuolar
*   Vesicular
*   Virion surface

**Rare topological domains**

*   Lumenal, melanosome
*   Mother cell cytoplasmic
*   Forespore intermembrane space
*   Intragranular
*   In membrane
*   Pore forming
*   Exoplasmic loop

Examples: [Q8BJ48](http://www.uniprot.org/uniprot/Q8BJ48#subcellular_location), [O14300](http://www.uniprot.org/uniprot/Q9BDE0#subcellular_location), [Q93ZB2](http://www.uniprot.org/uniprot/Q93ZB2#subcellular_location), [Q9LD37](http://www.uniprot.org/uniprot/Q9LD37#subcellular_location), [P43524](http://www.uniprot.org/uniprot/P43524#subcellular_location), [Q9NR77](http://www.uniprot.org/uniprot/Q9NR77#subcellular_location), [P25818](http://www.uniprot.org/uniprot/P25818#subcellular_location), [O15155](http://www.uniprot.org/uniprot/O15155#subcellular_location), [Q9H598](http://www.uniprot.org/uniprot/Q9H598#subcellular_location), [P0A221](http://www.uniprot.org/uniprot/P0A221#subcellular_location)

Note that in each case the subcellular location of the protein as a whole is defined in the ['Subcellular location'](http://www.uniprot.org/manual/subcellular_location) subsection.

We annotate both experimentally determined and predicted topological domains.

### 1\. Annotation of experimentally proven topological domains:

Most often, there is proof for the **existence** of transmembrane domains, but not for their **boundaries**. As a consequence, the **extents** of [transmembrane regions](http://www.uniprot.org/help/transmem) and the corresponding neighboring topological domains are predicted. Even when supporting experimental evidence is available for the assignment of a particular region of a protein to a particular cellular compartment, the topological domains of a protein are therefore generally annotated using the evidence ['Sequence analysis'](http://www.uniprot.org/help/evidences#ECO:0000255).  
  
Example: [Q96BI3](http://www.uniprot.org/uniprot/Q96BI3#subcellular_location)

When there is clear experimental proof for the location of the N-terminus or the C-terminus in the cytoplasm (or some other cellular compartment), this is labeled with ['Experimental'](http://www.uniprot.org/help/evidences#ECO:0000269) or ['Curated'](http://www.uniprot.org/help/evidences#ECO:0000305) evidence depending on the level of confidence. In this case, the positions of the topological domains can be propagated to related entries ['By similarity'](http://www.uniprot.org/help/evidences#ECO:0000250) if applicable.  
  
Examples: [Q8TCT9](http://www.uniprot.org/uniprot/Q8TCT9#subcellular_location) (experimental), [Q9D8V0](http://www.uniprot.org/uniprot/Q9D8V0#subcellular_location) (propagated by similarity)

However when the experimental technique used allows the assignment of the transmembrane boundary to a particular position (X-ray crystallography, etc.), the topological domain is labeled with ['Experimental'](http://www.uniprot.org/help/evidences#ECO:0000269) or ['Curated'](http://www.uniprot.org/help/evidences#ECO:0000305) evidence. In this case, the positions of the topological domains can be propagated to related entries ['By similarity'](http://www.uniprot.org/help/evidences#ECO:0000250) if applicable.  
  
Examples: [P63142](http://www.uniprot.org/uniprot/P63142#subcellular_location) (experimental), [P22459](http://www.uniprot.org/uniprot/P22459#subcellular_location) (propagated by similarity)

Having said this, unfortunately [not all UniProtKB/Swiss-Prot annotations have evidence](http://www.uniprot.org/help/evidence%5Fin%5Fswissprot). The annotations which are missing evidence were created before we started to manually curate information with evidence in UniProtKB/Swiss-Prot, and manual attribution of evidence to these existing annotations was not possible due to the huge amount of existing data. In such cases, the absence of any evidence for topological domains may in many cases be interpreted as 'Experimental' or 'Curated'.

### 2\. Annotation of predicted topological domains:

We also annotate topological domains based on the predictions provided by the program TMHMM, which returns a probability that non-transmembrane regions of a protein are in a cytoplasmic compartment (specified as 'in') or a non-cytoplasmic compartment (specified as 'out'). When TMHMM returns a high confidence topology prediction for a protein of known subcellular location, the notional 'in' and 'out' predictions from TMHMM are specified using a controlled vocabulary as described above. For instance, we may specify 'in' as 'cytoplasmic' and 'out' as 'periplasmic'.  
  
Example: [Q8BJ48](http://www.uniprot.org/uniprot/Q8BJ48#subcellular%5Flocation)

When nothing is known about the subcellular location of the protein, we annotate the topological domains based on TMHMM predictions using the default values of 'cytoplasmic' and 'extracellular'. In all cases, predicted topological domains are annotated with ['Sequence analysis'](http://www.uniprot.org/help/evidences#ECO:0000255).

See also:

*   [Evidence](http://www.uniprot.org/help/evidences)
*   [Transmembrane](http://www.uniprot.org/help/transmem)
*   [Sequence annotation (features)](http://www.uniprot.org/help/sequence%5Fannotation)
        