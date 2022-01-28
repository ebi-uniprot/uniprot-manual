
---
title: How can I search UniProt for chemical or reaction data?
categories: Text_search,Function,UniProtKB,faq
---

[Video tutorial](https://www.youtube.com/watch?v=5eW%2DeZJ08wc)

Enzyme-catalysed reactions are annotated in UniProtKB in the [Catalytic activity](http://www.uniprot.org/help/catalytic%5Factivity) section.

The [Advanced search](http://www.uniprot.org/help/advanced%5Fsearch) can be used to search in these annotations, by reaction participant (name or [ChEBI](https://www.ebi.ac.uk/chebi/) identifier), reaction identifier (from [Rhea](https://www.rhea/%2Ddb.org/)), or by [InChIKey](https://en.wikipedia.org/wiki/International%5FChemical%5FIdentifier#InChIKey).

### Search for a reaction compound using autocompletion

Click on "Advanced" and select "Catalytic activity" under "Function". When starting to type the name of a chemical compound, e.g. "L-lys...." the autocompletion mechanism suggests several compounds from ChEBI, and others from Rhea:

![image](https://github.com/ebi-uniprot/uniprot-manual/blob/main/images/chem_search.png?raw=true)

### Search for a given reaction by Rhea identifier

[RHEA:20856](https://www.rhea/%2Ddb.org/reaction?id=20856) describes the reaction

an N-acylsphing-4-enine + H2O = a fatty acid + sphing-4-enine

All proteins annotated to catalyze this reaction in UniProtKB can be retrieved with this query:  
  
[(cc_catalytic_activity:"Rhea:20856")](http://www.uniprot.org/uniprotkb?query=(cc_catalytic_activity:"Rhea:20856"))

![image](https://github.com/ebi-uniprot/uniprot-manual/blob/main/images/chem_rhea.png?raw=true)

### Search for reactions based on parent-child relationships defined in ChEBI

To retrieve entries catalyzing reactions involving sugars, it is possible to use the auto-completion functionality, e.g. with the word "sugar".

![](https://github.com/ebi-uniprot/uniprot-manual/blob/main/images/chem_data_1a.png?raw=true)

To retrieve all entries catalyzing reactions involving any monosaccharide, it is also possible to search with the high-level term "monosaccharide":

annotation:(type:"catalytic activity" chebi:"monosaccharide [35381]")

### Chemical structure search with InChIKey

You can search UniProtKB for small molecule reaction participants and cofactors using the InChIKey, a standard hashed representation of the IUPAC International Chemical Identifier (InChI) that provides a unique and compact representation of chemical structure data. Flexible chemical structure searches are possible with the complete InChIKey, as well as with the connectivity and stereochemistry layers, or the connectivity layer alone. You can search our "Catalytic activity" or "Cofactor" annotations, or both combined, by using the "Small molecule" advanced search field:

![](https://github.com/ebi-uniprot/uniprot-manual/blob/main/images/chem_data_2a.png?raw=true)

#### Chemical structure search with a complete InChIKey
WQZGKKKJIJFFOK-GASJEMHNSA-N is the InChIKey for [CHEBI:4167](https://www.ebi.ac.uk/chebi/searchId.do?chebiId=CHEBI:4167) - D-glucopyranose