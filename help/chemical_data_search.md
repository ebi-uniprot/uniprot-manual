---
title: How can I search UniProt for chemical or reaction data?
type: help
categories: Text_search,Function,UniProtKB,faq
---

[Video tutorial](https://www.youtube.com/watch?v=5eW-eZJ08wc)

Enzyme-catalysed reactions are annotated in UniProtKB in the [Catalytic activity](https://www.uniprot.org/help/catalytic_activity) section.

The [Advanced search](https://www.uniprot.org/help/advanced_search) can be used to search in these annotations, by reaction participant (name or [ChEBI](https://www.ebi.ac.uk/chebi/) identifier), reaction identifier (from [Rhea](https://www.rhea-db.org/) ), or by [InChIKey](https://en.wikipedia.org/wiki/International_Chemical_Identifier#InChIKey).

# Search for a reaction compound using autocompletion

Click on "Advanced" and select "Catalytic activity" under "Function". When starting to type the name of a chemical compound, e.g. "L-lys.…" the autocompletion mechanism suggests several compounds from ChEBI, and others from Rhea:

![image](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/chem_search.png)

# Search for a given reaction by Rhea identifier

[RHEA:20856](https://www.rhea-db.org/reaction?id=20856) describes the reaction

    an N-acylsphing-4-enine + H2O = a fatty acid + sphing-4-enine

All proteins annotated to catalyze this reaction in UniProtKB can be retrieved with this query:  
[(cc_catalytic_activity:"Rhea:20856")](https://www.uniprot.org/uniprotkb?query=(cc_catalytic_activity:%22rhea:20856%22))

![image](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/chem_rhea.png)

# Search for reactions based on parent-child relationships defined in ChEBI

To retrieve entries catalyzing reactions involving sugars, it is possible to use the auto-completion functionality, e.g. with the word "sugar".

![image](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/catalytic_activity_sugar.png)

To retrieve all entries catalyzing reactions involving any monosaccharide, it is also possible to search with the high-level term "monosaccharide":

[(cc_catalytic_activity:"CHEBI:35381")](https://www.uniprot.org/uniprotkb?query=(cc_catalytic_activity:%22CHEBI:35381%22))

# Chemical structure search with InChIKey

You can search UniProtKB for small molecule reaction participants and cofactors using the InChIKey, a standard hashed representation of the IUPAC International Chemical Identifier ( [InChI](https://www.inchi-trust.org/about-the-inchi-standard/) ) that provides a unique and compact representation of chemical structure data. Flexible chemical structure searches are possible with the complete InChIKey, as well as with the connectivity and stereochemistry layers, or the connectivity layer alone. You can search our "Catalytic activity" or "Cofactor" annotations, or both combined, by using the "Small molecule" advanced search field:

![image](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/inchikey-field-search.png)

## Chemical structure search with a complete InChIKey

WQZGKKKJIJFFOK-GASJEMHNSA-N is the InChIKey for [CHEBI:4167](https://www.ebi.ac.uk/chebi/searchId.do?chebiId=CHEBI:4167) - D-glucopyranose

![image](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/WQZGKKKJIJFFOK-GASJEMHNSA-N.png)

![image](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/WQZGKKKJIJFFOK-GASJEMHNSA-N-results.png)

## Chemical structure search with a partial InChIKey (connectivity information only)

### Partial InChIKey without the \[de\]protonation indicator

e.g. [WQZGKKKJIJFFOK-GASJEMHNSA](https://www.ebi.ac.uk/chebi/advancedSearchFT.do?searchString=WQZGKKKJIJFFOK-GASJEMHNSA)

[(inchikey:WQZGKKKJIJFFOK-GASJEMHNSA)](https://www.uniprot.org/uniprotkb?query=(inchikey:WQZGKKKJIJFFOK-GASJEMHNSA))

### Partial InChIKey for the molecular skeleton (connectivity)

a 14-character hash encoding the basic (Mobile-H) InChI layer, e.g. [WQZGKKKJIJFFOK](https://www.ebi.ac.uk/chebi/advancedSearchFT.do?searchString=WQZGKKKJIJFFOK)

[(inchikey:WQZGKKKJIJFFOK)](https://www.uniprot.org/uniprotkb?query=(inchikey:WQZGKKKJIJFFOK))

# Search for a compound not present in ChEBI, or with a word from a free text reaction description

Historically, UniProt has followed the recommendations of the Nomenclature Committee of the International Union of Biochemistry and Molecular Biology (NC-IUBMB) for the description of enzymatic activities. The NC-IUBMB use their own names for the reactants, and sometimes the catalytic activity from IUBMB is a free text reaction description.

When searching with a compound name that is not in ChEBI but part of a reaction sourced from IUBMB, or with a word from a free text reaction description, a full text search instead of an identifier search is performed in catalytic activity annotation. Since IUBMB does not use ChEBI or any other ontology, there is no autocompletion in this case, and no hierarchical relationships (such as is_a) can be taken into account.

Example:  
[(cc_catalytic_activity:PretRNA)](https://www.uniprot.org/uniprotkb?query=(cc_catalytic_activity:PretRNA))

The following query returns all entries that have a catalytic activity annotated that is not sourced from Rhea but from IUBMB:  
[(cc_catalytic_activity:\*) NOT (cc_catalytic_activity:"rhea:\*")](https://www.uniprot.org/uniprotkb?query=(cc_catalytic_activity:*)%20NOT%20(cc_catalytic_activity:%22rhea:*%22))

# Search for small molecules, using ChEBI (not restricted to catalytical activity)

The ChEBI (Chemical Entities of Biological Interest) ontology is used in "Catalytic activity" or "Cofactor" annotations, and the advanced search allows to search in either of these fields separately, or in both combined, by using the "Small molecule" advanced search field:

Example biotin ( [ChEBI:57586](https://www.ebi.ac.uk/chebi/searchId.do?chebiId=CHEBI:57586) ) :

- Biotin in "Small molecule":  
[(chebi:"CHEBI:57586") AND (reviewed:true)](https://www.uniprot.org/uniprotkb?query=(chebi:%22CHEBI:57586%22)%20AND%20(reviewed:true))
- Biotin in "Catalytic activity":  
[(cc_catalytic_activity:"CHEBI:57586") AND (reviewed:true)](https://www.uniprot.org/uniprotkb?query=%28cc_catalytic_activity%3A%22CHEBI%3A57586%22%29%20AND%20%28reviewed%3Atrue%29)
- Biotin in "Cofactor":  
[cc_cofactor_chebi](https://www.uniprot.org/uniprotkb?query=%28cc_cofactor_chebi%3A%22CHEBI%3A57586%22%29%20AND%20%28reviewed%3Atrue%29)
