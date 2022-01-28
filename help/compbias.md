
---
title: Compositional bias
categories: Family_and_domains,manual
---

This subsection of the 'Family and Domains' section describes the position of regions of compositional bias within the protein and the particular amino acids that are over-represented within those regions.

We annotate two types of compositionally biased regions: **homopolymeric stretches** of at least 4 residues in length, which are annotated as 'Poly-Xaa', and large **regions of compositional bias**, which are annotated as 'Xaa-rich', where Xaa is a valid 3-letter amino acid code.  
  
Examples: [Q9W705](http://www.uniprot.org/uniprot/Q9W705#family_and_domains), [P62521](http://www.uniprot.org/uniprot/P62521#family_and_domains)

### Homopolymeric stretches

We annotate homopolymeric stretches even if there is a single amino acid interruption in the run of amino acids, provided that there is less than one such interruption per five residues on average. In contrast, an interruption of two or more residues is not allowed.

Examples:

*   AAAAAAMAAAAA : will be annotated as Poly-Ala (1 interruption in 12 residues)
*   AAMAAAMAAAAA : will be annotated as Poly-Ala (2 interruptions in 12 residues)
*   AAMAAAMAAMAA : will NOT be annotated as Poly-Ala (3 interruptions in 12 residues)
*   AAAAAMMAAAAA : will NOT be annotated as Poly-Ala (2 consecutive interruptions)

In general we annotate only those homopolymeric stretches which are particularly striking or those which concern an amino acid that is known to have specific characteristics, such as proline residues which disrupt alpha-helical regions. Homopolymeric stretches of the more common amino acids in the proteome (such as alanine, glutamic acid, glycine, leucine, serine and valine) are rarely annotated unless they are especially long.  
  
Conversely, homopolymeric stretches of rare amino acids in the proteome (such as glutamine, histidine, methionine, tryptophan and tyrosine) are annotated more frequently. We do not annotate homopolymeric stretches that overlap with known or predicted transmembrane or signal sequences.  
  
Examples: [Q9UPA5](http://www.uniprot.org/uniprot/Q9UPA5#family_and_domains), [O60563](http://www.uniprot.org/uniprot/O60563#family_and_domains)

### Regions of compositional bias

For larger regions of compositional bias which are specifically enriched in one or more residues we indicate the identity or identities of those residues using the syntax Aa1\[/Aa2/.../Aan\]-rich, where Aa1, Aa2, ... Aan are valid amino-acid three letter amino-acid codes listed in alphabetical order.  
  
Example: [Q94546](http://www.uniprot.org/uniprot/Q94546#family_and_domains)

We also indicate the general properties of the regions of bias.  
  
Examples: [P06651](http://www.uniprot.org/uniprot/P06651#family_and_domains), [P25054](http://www.uniprot.org/uniprot/P25054#family_and_domains)

When residues in a region of compositional bias are subject to a specific post-translational modification, it is indicated both in the 'Compositional bias' and ['Modified residue'](http://www.uniprot.org/manual/mod_res) subsections of the 'PTM / Processing' section, and in the ['Post-translational modification'](http://www.uniprot.org/manual/post-translational_modification) subsection of the 'PTM / Processing' section. For instance in the fibrillarin family, the Gly-rich region is subject to extensive dimethylation.  
  
Example: [Q756P0](http://www.uniprot.org/uniprot/Q756P0#family_and_domains)

When regions of compositional bias are features of known domains, they are not explicitly described; for instance, we do not indicate the fact that EGF-domains are cysteine-rich.
        