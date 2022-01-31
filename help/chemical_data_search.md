---
title: How can I search UniProt for chemical or reaction data?
categories: Text_search,Function,UniProtKB,faq
---

[Video tutorial](https://www.youtube.com/watch?v=5eW-eZJ08wc)

Enzyme-catalysed reactions are annotated in UniProtKB in the [Catalytic activity](http://www.uniprot.org/help/catalytic%5Factivity) section.

The [Advanced search](http://www.uniprot.org/help/advanced%5Fsearch) can be used to search in these annotations, by reaction participant (name or [ChEBI](https://www.ebi.ac.uk/chebi/) identifier), reaction identifier (from [Rhea](https://www.rhea-db.org/) ), or by [InChIKey](https://en.wikipedia.org/wiki/International%5FChemical%5FIdentifier#InChIKey) .

### Search for a reaction compound using autocompletion

Click on "Advanced" and select "Catalytic activity" under "Function". When starting to type the name of a chemical compound, e.g. "L-lys.…" the autocompletion mechanism suggests several compounds from ChEBI, and others from Rhea:

![image](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/chemical_data_search-2.png)

### Search for a given reaction by Rhea identifier

[RHEA:20856](https://www.rhea-db.org/reaction?id=20856) describes the reaction

    an N-acylsphing-4-enine + H2O = a fatty acid + sphing-4-enine

All proteins annotated to catalyze this reaction in UniProtKB can be retrieved with this query:  
[annotation:(type:"catalytic activity" rhea:20856)](https://www.uniprot.org/uniprotkb/?query=annotation%3A%28type%3A%22catalytic+activity%22+RHEA%3A20856%29&sort=score)

![image](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/chemical_data_search-3.png)

### Search for reactions based on parent-child relationships defined in ChEBI

To retrieve entries catalyzing reactions involving sugars, it is possible to use the auto-completion functionality, e.g. with the word "sugar".

![image](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/chemical_data_search-4.png)

To retrieve all entries catalyzing reactions involving any monosaccharide, it is also possible to search with the high-level term "monosaccharide":

[annotation:(type:"catalytic activity" chebi:"monosaccharide \[35381\]")](https://www.uniprot.org/uniprotkb/?query=annotation%3A%28type%3A%22catalytic+activity%22+CHEBI%3A35381%29)

### Chemical structure search with InChIKey

You can search UniProtKB for small molecule reaction participants and cofactors using the InChIKey, a standard hashed representation of the IUPAC International Chemical Identifier ( [InChI](https://www.inchi-trust.org/about-the-inchi-standard/) ) that provides a unique and compact representation of chemical structure data. Flexible chemical structure searches are possible with the complete InChIKey, as well as with the connectivity and stereochemistry layers, or the connectivity layer alone. You can search our "Catalytic activity" or "Cofactor" annotations, or both combined, by using the "Small molecule" advanced search field:

![image](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/chemical_data_search-5.png)

#### Chemical structure search with a complete InChIKey

WQZGKKKJIJFFOK-GASJEMHNSA-N is the InChIKey for [CHEBI:4167](https://www.ebi.ac.uk/chebi/searchId.do?chebiId=CHEBI:4167) - D-glucopyranose

![image](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/chemical_data_search-6.png)

![image](https://github.com/ebi-uniprot/uniprot-manual/raw/main/images/chemical_data_search-7.png)

#### Chemical structure search with a partial InChIKey (connectivity information only)

##### Partial InChIKey without the \[de\]protonation indicator

e.g. [WQZGKKKJIJFFOK-GASJEMHNSA](https://www.ebi.ac.uk/chebi/advancedSearchFT.do?searchString=WQZGKKKJIJFFOK-GASJEMHNSA)

[annotation:(type:"catalytic activity" inchikey:WQZGKKKJIJFFOK-GASJEMHNSA)](https://www.uniprot.org/uniprotkb/?query=annotation%3A%28type%3A%22catalytic+activity%22+inchikey%3AWQZGKKKJIJFFOK-GASJEMHNSA%29)

##### Partial InChIKey for the molecular skeleton (connectivity)

a 14-character hash encoding the basic (Mobile-H) InChI layer, e.g. [WQZGKKKJIJFFOK](https://www.ebi.ac.uk/chebi/advancedSearchFT.do?searchString=WQZGKKKJIJFFOK)

[annotation:(type:"catalytic activity" inchikey:WQZGKKKJIJFFOK)](https://www.uniprot.org/uniprotkb/?query=annotation%3A%28type%3A%22catalytic+activity%22+inchikey%3AWQZGKKKJIJFFOK%29)

### Search for a compound not present in ChEBI, or with a word from a free text reaction description

Historically, UniProt has followed the recommendations of the Nomenclature Committee of the International Union of Biochemistry and Molecular Biology (NC-IUBMB) for the description of enzymatic activities. The NC-IUBMB use their own names for the reactants, and sometimes the catalytic activity from IUBMB is a free text reaction description.

When searching with a compound name that is not in ChEBI but part of a reaction sourced from IUBMB, or with a word from a free text reaction description, a full text search instead of an identifier search is performed in catalytic activity annotation. Since IUBMB does not use ChEBI or any other ontology, there is no autocompletion in this case, and no hierarchical relationships (such as is\_a) can be taken into account.

Example:  
[annotation:(type:"catalytic activity" PretRNA)](https://www.uniprot.org/uniprotkb/?query=annotation%3A%28type%3A%22catalytic+activity%22+PretRNA%29)

The following query returns all entries that have a catalytic activity annotated that is not sourced from Rhea but from IUBMB:  
[annotation:(type:"catalytic activity") NOT annotation:(type:"catalytic activity "rhea:\*)](https://www.uniprot.org/uniprotkb/?query=annotation%3A%28type%3A%22catalytic+activity%22%29+NOT+annotation%3A%28type%3A%22catalytic+activity%22+rhea%3A%2A%29)

### Search for small molecules, using ChEBI (not restricted to catalytical activity)

The ChEBI (Chemical Entities of Biological Interest) ontology is used in "Catalytic activity" or "Cofactor" annotations, and the advanced search allows to search in either of these fields separately, or in both combined, by using the "Small molecule" advanced search field:

Example biotin ( [ChEBI:57586](https://www.ebi.ac.uk/chebi/searchId.do?chebiId=CHEBI:57586) ) :

Biotin in "Small molecule":  
[reviewed:yes AND chebi:"biotin\[57586\]"](https://www.uniprot.org/uniprotkb/?query=chebi%3A%22biotin+%5B57586%5D%22+reviewed%3Ayes)  
Biotin in "Catalytic activity":  
[reviewed:yes AND annotation:(type:"catalytic activity" chebi:"biotin \[57586\]")](https://www.uniprot.org/uniprotkb/?query=annotation%3A%28type%3A%22catalytic+activity%22+CHEBI%3A57586%29+reviewed%3Ayes)

Biotin in "Cofactor":  
[reviewed:yes AND cofactor:(chebi:"biotin \[57586\]")](https://www.uniprot.org/uniprotkb/?query=cofactor%3A%28chebi%3A%22biotin+%5B57586%5D%22%29+reviewed%3Ayes)
