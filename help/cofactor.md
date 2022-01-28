
---
title: Cofactor
categories: Function,manual
---

This subsection of the 'Function' section provides information relevant to cofactors. A cofactor is any non-protein substance required for a protein to be catalytically active. Some cofactors are inorganic, such as the metal atoms zinc, iron, and copper in various oxidation states. Others, such as most vitamins, are organic.

Cofactors are generally either bound tightly to active sites, or may bind loosely with the enzyme. They may also be important for structural integrity, i.e. if they are not present, the enzyme does not fold properly or becomes unstable.

The 'Cofactor' subsection is used when ions and other small ligands bind to the enzyme. These cofactor molecules are mapped to [ChEBI](http://www.ebi.ac.uk/chebi/) identifiers. In the case of multimers, cofactors can be bound either to only one subunit of the enzyme or to the interface. In the former case, the cofactor is only annotated for the subunit to which it binds.

Substrates for a reaction (NAD, FAD, ATP) that are listed in the [Catalytic activity](http://www.uniprot.org/manual/catalytic%5Factivity) subsection are not listed as cofactors, with the exception of the rare cases in which an enzyme binds the same type of molecule as a substrate at one site and as a cofactor at other sites.

The following substances are not considered as cofactors:  
  
\- Ubiquitous substances such as water are not considered as cofactors  
  
\- Ions that are part of well-described metal binding domains, such as EF-hands.

**When alternative molecules can act as cofactors at the same site**, they are listed in one 'Cofactor' annotation block. Only molecules that allow more than 50% of the maximum activity are mentioned, while others can be mentioned in the "Note" field.  
  
Examples: [P00918](http://www.uniprot.org/uniprot/P00918#function), [G3XD94](http://www.uniprot.org/uniprot/G3XD94#function)

**When the precise stoichiometry of a cofactor is known**, this is indicated in the "Note" field. In such cases, only one 'Cofactor' annotation block is created.  
  
Example: [Q90240](http://www.uniprot.org/uniprot/Q90240#function)

**When an enzyme binds chemically different cofactors at different sites**, there is one 'Cofactor' annotation block for each site.  
  
Example: [P38289](http://www.uniprot.org/uniprot/P38289#function)

**When an enzyme binds a cofactor via a covalent linkage**, the name of the compound is indicated under 'Cofactor', while the name of the modification is described under [Post-translational modifications (Modified residue)](http://www.uniprot.org/manual/mod%5Fres).  
  
Examples: [P9WP55](http://www.uniprot.org/uniprot/P9WP55#function), [B3QM53](http://www.uniprot.org/uniprot/B3QM53#function)

**If there is isoform-specific or chain-specific cofactor information**, there will be separate 'Cofactor' annotation blocks for each isoform or chain.  
  
Examples: [O15304](http://www.uniprot.org/uniprot/O15304#function), [P26662](http://www.uniprot.org/uniprot/P26662#function)

**If a cofactor is proven not to be required for activity, or too complex to be described with ChEBI**, it is possible to have 'Cofactor' annotation block consisting only of a "Note".  
  
Examples: [A9CEQ7](http://www.uniprot.org/uniprot/A9CEQ7#function), [Q9F1R6](http://www.uniprot.org/uniprot/Q9F1R6#function)
        