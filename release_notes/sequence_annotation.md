---
title: Sequence annotation (Features)
categories: manual
---

Sequence annotations describe regions or sites of interest in the protein sequence, such as post-translational modifications, binding sites, enzyme active sites, local secondary structure or other characteristics reported in the cited references. Sequence conflicts between references are also described in this manner.

Sequence annotations (position-specific annotations) used to be found in the 'Sequence annotation (Features)' section in the previous version of the UniProtKB entry view. The flat file and XML formats still group all position-specific annotation together in a "feature table" (FT, ). Each sequence annotation consists of a "feature key", "from" and "to" positions as well as a short description.

The current entry view displays annotation by subject (Function, PTM & processing, etc), and the various position-specific annotations are now distributed to the relevant new sections.

|                                                                |                                                                                                         |
|:---------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------|
| **Subsection**                                                 | **Content**                                                                                             |
| **Molecule processing**                                        |                                                                                                         |
| [Initiator methionine](https://www.uniprot.org/help/init_met)  | Cleavage of the initiator methionine                                                                    |
| [Signal](https://www.uniprot.org/help/signal)                  | Sequence targeting proteins to the secretory pathway or periplasmic space                               |
| [Transit peptide](https://www.uniprot.org/help/transit)        | Extent of a transit peptide for organelle targeting                                                     |
| [Propeptide](https://www.uniprot.org/help/propep)              | Part of a protein that is cleaved during maturation or activation                                       |
| [Chain](https://www.uniprot.org/help/chain)                    | Extent of a polypeptide chain in the mature protein                                                     |
| [Peptide](https://www.uniprot.org/help/peptide)                | Extent of an active peptide in the mature protein                                                       |
| **Regions**                                                    |                                                                                                         |
| [Topological domain](https://www.uniprot.org/help/topo_dom)    | Location of non-membrane regions of membrane-spanning proteins                                          |
| [Transmembrane](https://www.uniprot.org/help/transmem)         | Extent of a membrane-spanning region                                                                    |
| [Intramembrane](https://www.uniprot.org/help/intramem)         | Extent of a region located in a membrane without crossing it                                            |
| [Domain](https://www.uniprot.org/help/domain)                  | Position and type of each modular protein domain                                                        |
| [Repeat](https://www.uniprot.org/help/repeat)                  | Positions of repeated sequence motifs or repeated domains                                               |
| [Calcium binding](https://www.uniprot.org/help/ca_bind)        | Position(s) of calcium binding region(s) within the protein                                             |
| [Zinc finger](https://www.uniprot.org/help/zn_fing)            | Position(s) and type(s) of zinc fingers within the protein                                              |
| DNA binding                                                    | Position and type of a                                                                                  |
|                                                                | DNA -binding domain                                                                                     |
| [Nucleotide binding](https://www.uniprot.org/help/np_bind)     | Nucleotide phosphate binding region                                                                     |
| [Region](https://www.uniprot.org/help/region)                  | Region of interest in the sequence                                                                      |
| [Coiled coil](https://www.uniprot.org/help/coiled)             | Positions of regions of coiled coil within the protein                                                  |
| [Motif](https://www.uniprot.org/help/motif)                    | Short (up to 20 amino acids) sequence motif of biological interest                                      |
| [Compositional bias](https://www.uniprot.org/help/compbias)    | Region of compositional bias in the protein                                                             |
| **Sites**                                                      |                                                                                                         |
| [Active site](https://www.uniprot.org/help/act_site)           | Amino acid(s) directly involved in the activity of an enzyme                                            |
| [Metal binding](https://www.uniprot.org/help/metal)            | Binding site for a metal ion                                                                            |
| [Binding site](https://www.uniprot.org/help/binding)           | Binding site for any chemical group (co-enzyme, prosthetic group, etc.)                                 |
| [Site](https://www.uniprot.org/help/site)                      | Any interesting single amino acid site on the sequence                                                  |
| **Amino acid modifications**                                   |                                                                                                         |
| [Non-standard residue](https://www.uniprot.org/help/non_std)   | Occurence of non-standard amino acids (selenocysteine and pyrrolysine) in the protein sequence          |
| [Modified residue](https://www.uniprot.org/help/mod_res)       | Modified residues excluding lipids, glycans and protein cross-links                                     |
| [Lipidation](https://www.uniprot.org/help/lipid)               | Covalently attached lipid group(s)                                                                      |
| [Glycosylation](https://www.uniprot.org/help/carbohyd)         | Covalently attached glycan group(s)                                                                     |
| [Disulfide bond](https://www.uniprot.org/help/disulfid)        | Cysteine residues participating in disulfide bonds                                                      |
| [Cross-link](https://www.uniprot.org/help/crosslnk)            | Residues participating in covalent linkage(s) between proteins                                          |
| **Natural variations**                                         |                                                                                                         |
| [Alternative sequence](https://www.uniprot.org/help/var_seq)   | Amino acid change(s) producing alternate protein isoforms                                               |
| [Natural variant](https://www.uniprot.org/help/variant)        | Description of a natural variant of the protein                                                         |
| **Experimental info**                                          |                                                                                                         |
| [Mutagenesis](https://www.uniprot.org/help/mutagen)            | Site which has been experimentally altered by mutagenesis                                               |
| [Sequence uncertainty](https://www.uniprot.org/help/unsure)    | Regions of uncertainty in the sequence                                                                  |
| [Sequence conflict](https://www.uniprot.org/help/conflict)     | Description of sequence discrepancies of unknown origin                                                 |
| [Non-adjacent residues](https://www.uniprot.org/help/non_cons) | Indicates that two residues in a sequence are not consecutive                                           |
| [Non-terminal residue](https://www.uniprot.org/help/non_ter)   | The sequence is incomplete. Indicate that a residue is not the terminal residue of the complete protein |
| **Secondary structure**                                        |                                                                                                         |
| [Helix](https://www.uniprot.org/help/helix)                    | Helical regions within the experimentally determined protein structure                                  |
| [Turn](https://www.uniprot.org/help/turn)                      | Turns within the experimentally determined protein structure                                            |
| [Beta strand](https://www.uniprot.org/help/strand)             | Beta strand regions within the experimentally determined protein structure                              |

The exact boundaries of the described sequence feature, as well as its length, are provided. When a feature is known to extend beyond the position that is given in this section, the endpoint specification will be preceded by '&lt;' (less than) for features which continue to the N-terminal direction or by '&gt;' (greater than) for features which continue to the C-terminal direction.

Example: [P62756](https://www.uniprot.org/uniprotkb/P62756#ptm%5Fprocessing)

Unknown endpoints are denoted by a question mark '?'.  
Example: [P78586](https://www.uniprot.org/uniprotkb/P78586#ptm%5Fprocessing)

Uncertain endpoints are denoted by a question mark '?' before the position, e.g. '?42'.  
Example: [Q3ZC31](https://www.uniprot.org/uniprotkb/Q3ZC31#ptm%5Fprocessing)

### Feature identifiers

Some features are associated with a unique and stable identifier that allows to construct links between these position-specific annotations and specialized protein-related databases.

The format of the identifiers is a 3-letter prefix, specific for an annotation type, separated by an underscore from a 6 to 10-digit number.

Feature identifiers currently exist for the following annotation topics: Propeptide, Chain, Peptide, Glycosylation, Alternative sequence and Natural variant.

------------------------------------------------------------------------

**Subsection** **Identifier prefix** **Availability** **Example**

**Molecule processing**

[Propeptide](https://www.uniprot.org/help/propep) PRO Any processed propeptide Q7XAD0

[Chain](https://www.uniprot.org/help/chain)  PRO Any mature polypeptide Q9W568  
[Peptide](https://www.uniprot.org/help/peptide)  
P15515

**Amino acid modifications**

[Glycosylation](https://www.uniprot.org/help/carbohyd) CAR Only for residues attached to an oligosaccharide structure annotated in the [GlyConnect](https://glyconnect.expasy.org/) database P02771

**Natural variations**

[Alternative sequence](https://www.uniprot.org/help/var_seq) VSP Any sequence with an ‘Alternative sequence’ feature P81278

[Natural variant](https://www.uniprot.org/help/variant) VAR Only for protein sequence variants of Hominidae (great apes and humans) P11171 ————————————————————– ———————– ———————————————————————————————————————————– —————–
