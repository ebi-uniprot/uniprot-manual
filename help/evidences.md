
---
title: Evidence
categories: manual
---

### Introduction

Most information in UniProtKB has one or several "evidence tags" which describe the source of the information, e.g. an experiment that has been published in the scientific literature, an orthologous protein, a record from another database, etc.

Formally, an evidence is described by a mandatory **evidence type**, represented by a code from the [Evidence and Conclusion Ontology](http://www.evidenceontology.org/) (ECO) and, where applicable, the **source of the information**, which is usually a database record (articles from the scientific literature are represented as PubMed records, but in the case of publications that are not in PubMed we indicate instead the corresponding UniProtKB reference number).

ECO comprises two high-level classes, **evidence** and **assertion method**. Evidence is defined as a type of information that is used to support an assertion and assertion method is defined as a means by which a statement is made about an entity. Together evidence and assertion method can be used to describe both the support for an assertion and whether that assertion was made by a human being or a computer. UniProtKB is using only codes that combine evidence and assertion method.

Here are some examples of how evidence descriptions look in the UniProtKB flat file format:

*   An evidence type without source: `{type}`, e.g.
    
    {ECO:0000305}
    {ECO:0000250}
    {ECO:0000255}
    

*   An evidence type with source: `{type|source}`, e.g.
    
    {ECO:0000269|PubMed:24356955}
    {ECO:0000303|Ref.6}
    {ECO:0000305|PubMed:22388736}
    {ECO:0000250|UniProtKB:P11497}
    {ECO:0000255|HAMAP-Rule:MF\_03130}
    {ECO:0000256|HAMAP-Rule:MF\_03130}
    {ECO:0000312|EMBL:AAY86039.1}
    {ECO:0000313|EMBL:AAY86039.1}
    {ECO:0000244|PDB:1V90}
    {ECO:0000213|PDB:1V90}
    

*   Several evidence attributions: `{type|source, type|source, ...}`, e.g.
    
    {ECO:0000269|PubMed:10433554, ECO:0000303|Ref.6}
    

On the website, these descriptions are transformed to make them more user-friendly. The ECO codes are replaced by easy to understand labels and the sources are accessible by clicking on an arrow to list the hyper-linked sources. Evidence that is used in manual assertions is colored gold, e.g.

1 Publication

Manual assertion based on experiment

By similarity

Manual assertion inferred from sequence similarity

UniRule annotation

Manual assertion according to rules

*   [HAMAP-Rule:MF\_03130](http://hamap.expasy.org/unirule/MF_03130)

  
  
Imported

Manual assertion inferred from database entries

*   [EMBL:AAY86039.1](https://www.ebi.ac.uk/ena/browser/view/AAY86039)
*   [MGI:87860](http://www.informatics.jax.org/marker/MGI:87860)

and those that are used in automatic assertions are colored blue, e.g.

UniRule annotation

Automatic assertion according to rules

*   [PIRNR:PIRNR036489](http://pir.georgetown.edu/cgi-bin/pirrule?id=PIRNR036489)

  
  
Imported

Automatic assertion inferred from database entries

*   [EMBL:ABC70327.1](https://www.ebi.ac.uk/ena/browser/view/ABC70327)
*   [MGI:96952](http://www.informatics.jax.org/marker/MGI:96952)

### Evidence types that are used in UniProtKB

#### Evidence that is used only in manual assertions

##### Experimental evidence

We use the ECO code [ECO:0000269](http://bioportal.bioontology.org/ontologies/50043/?p=terms%26conceptid=ECO:0000269) for manually curated information for which there is published experimental evidence. The PubMed identifier of the publication(s) which is the original source of the information is provided (for publications that are not in PubMed we indicate instead the corresponding UniProtKB reference number(s)).

Example: [D9N129](http://www.uniprot.org/uniprot/D9N129#function)

1 Publication

Manual assertion based on experiment

*   **"The WD40-repeat proteins WDR-20 and WDR-48 bind and activate the deubiquitinating enzyme USP-46 to promote the abundance of the glutamate receptor GLR-1 in the ventral nerve cord of Caenorhabditis elegans."**  
      
    [Dahlberg C.L.](http://www.uniprot.org/?query=author:%22Dahlberg+C.L.%22), [Juo P.](http://www.uniprot.org/?query=author:%22Juo+P.%22)  
      
    [J. Biol. Chem. 289:3444-3456(2014)](http://dx.doi.org/10.1074/jbc.M113.507541) \[[PubMed](http://www.ncbi.nlm.nih.gov/pubmed/24356955)\] \[[Europe PMC](http://europepmc.org/abstract/MED/24356955)\] \[[Abstract](http://www.uniprot.org/citations/24356955)\]
    
    **Cited for**: FUNCTION, INTERACTION WITH USP-46, TISSUE SPECIFICITY, DISRUPTION PHENOTYPE.
    

CC   -!- FUNCTION: Together with wdr-48, binds to and stimulates the
CC       activity of the deubiquitinating enzyme usp-46, leading to
CC       deubiquitination and stabilization of the glr-1 glutamate
CC       receptor. {ECO:0000269|PubMed:24356955}.

##### Non-traceable author statement evidence

We use the ECO code [ECO:0000303](http://bioportal.bioontology.org/ontologies/50043/?p=terms%26conceptid=ECO:0000303) for manually curated information that is based on statements in scientific articles for which there is no experimental support. The PubMed identifier of the paper(s) which is the original source of the information is provided (for publications that are not in PubMed we indicate instead the corresponding UniProtKB reference number(s)).

Example: [Q24145](http://www.uniprot.org/uniprot/Q24145#function)

1 Publication

Manual assertion based on opinion

*   **"Shark, a Src homology 2, ankyrin repeat, tyrosine kinase, is expressed on the apical surfaces of ectodermal epithelia."**  
      
    [Ferrante A.W. Jr.](http://www.uniprot.org/?query=author:%22Ferrante+A.W.+Jr.%22), [Reinke R.](http://www.uniprot.org/?query=author:%22Reinke+R.%22), [Stanley E.R.](http://www.uniprot.org/?query=author:%22Stanley+E.R.%22)  
      
    [Proc. Natl. Acad. Sci. U.S.A. 92:1911-1915(1995)](http://dx.doi.org/10.1073/pnas.92.6.1911) \[[PubMed](http://www.ncbi.nlm.nih.gov/pubmed/7892198)\] \[[Europe PMC](http://europepmc.org/abstract/MED/7892198)\] \[[Abstract](http://www.uniprot.org/citations/7892198)\]
    
    **Cited for**: NUCLEOTIDE SEQUENCE \[MRNA\], FUNCTION, SUBCELLULAR LOCATION, TISSUE SPECIFICITY, DEVELOPMENTAL STAGE.
    

CC   -!- FUNCTION: May be involved in signal transduction on the apical
CC       surface of ectodermal epithelia regulating their polarity during
CC       invagination. Crumbs (crb) may be the intracellular signal.
CC       {ECO:0000303|PubMed:7892198}.

##### Curator inference evidence

We use the ECO code [ECO:0000305](http://bioportal.bioontology.org/ontologies/50043/?p=terms%26conceptid=ECO:0000305) for manually curated information which has been inferred by a curator based on his/her scientific knowledge or on the scientific content of an article. If the information is inferred from the scientific content of an article, the PubMed identifier of the supporting paper is provided (for publications that are not in PubMed we indicate instead the corresponding UniProtKB reference number(s)).

Example: [Q9UKV3](http://www.uniprot.org/uniprot/Q9UKV3#miscellaneous)

1 Publication

Manual assertion inferred from experiment in

*   **"The structure of the ASAP core complex reveals the existence of a Pinin-containing PSAP complex."**  
      
    [Murachelli A.G.](http://www.uniprot.org/?query=author:%22Murachelli+A.G.%22), [Ebert J.](http://www.uniprot.org/?query=author:%22Ebert+J.%22), [Basquin C.](http://www.uniprot.org/?query=author:%22Basquin+C.%22), [Le Hir H.](http://www.uniprot.org/?query=author:%22Le+Hir+H.%22), [Conti E.](http://www.uniprot.org/?query=author:%22Conti+E.%22)  
      
    [Nat. Struct. Mol. Biol. 19:378-386(2012)](http://dx.doi.org/10.1038/nsmb.2242) \[[PubMed](http://www.ncbi.nlm.nih.gov/pubmed/22388736)\] \[[Europe PMC](http://europepmc.org/abstract/MED/22388736)\] \[[Abstract](http://www.uniprot.org/citations/22388736)\]
    
    **Cited for**: INTERACTION WITH RNPS1, COMPOSITION OF THE ASAP COMPLEX, FUNCTION OF THE ASAP COMPLEX.
    

CC   -!- CAUTION: Structural and functional studies of the ASAP complex
CC       have been conducted with a chimeric complex involving a conserved
CC       fragment of Drosophila melanogaster Acinus/hkl.
CC       {ECO:0000305|PubMed:22388736}.

Example: [P62196](http://www.uniprot.org/uniprot/P62196#ptm%5Fprocessing)

1 Publication

Manual assertion inferred from experiment in

*   **"Mapping the murine cardiac 26S proteasome complexes."**  
      
    [Gomes A.V.](http://www.uniprot.org/?query=author:%22Gomes+A.V.%22), [Zong C.](http://www.uniprot.org/?query=author:%22Zong+C.%22), [Edmondson R.D.](http://www.uniprot.org/?query=author:%22Edmondson+R.D.%22), [Li X.](http://www.uniprot.org/?query=author:%22Li+X.%22), [Stefani E.](http://www.uniprot.org/?query=author:%22Stefani+E.%22), [Zhang J.](http://www.uniprot.org/?query=author:%22Zhang+J.%22), [Jones R.C.](http://www.uniprot.org/?query=author:%22Jones+R.C.%22), [Thyparambil S.](http://www.uniprot.org/?query=author:%22Thyparambil+S.%22), [Wang G.W.](http://www.uniprot.org/?query=author:%22Wang+G.W.%22), [Qiao X.](http://www.uniprot.org/?query=author:%22Qiao+X.%22), [Bardag-Gorce F.](http://www.uniprot.org/?query=author:%22Bardag-Gorce+F.%22), [Ping P.](http://www.uniprot.org/?query=author:%22Ping+P.%22)  
      
    [Circ. Res. 99:362-371(2006)](http://dx.doi.org/10.1161/01.RES.0000237386.98506.f7) \[[PubMed](http://www.ncbi.nlm.nih.gov/pubmed/16857966)\] \[[Europe PMC](http://europepmc.org/abstract/MED/16857966)\] \[[Abstract](http://www.uniprot.org/citations/16857966)\]
    
    **Cited for**: IDENTIFICATION IN THE 19S PROTEASOME REGULATORY COMPLEX, ACETYLATION AT ALA-2.
    

FT   INIT\_MET      1      1       Removed. {ECO:0000305|PubMed:16857966}.

##### Sequence similarity evidence

We use the ECO code [ECO:0000250](http://bioportal.bioontology.org/ontologies/50043/?p=terms%26conceptid=ECO:0000250) for manually curated information which has been propagated from a related experimentally characterized protein. The accession number of the experimental source is provided (except for some historic UniProtKB/Swiss-Prot annotations, see [Why don't all UniProtKB/Swiss-Prot annotations have evidence?](http://www.uniprot.org/faq/evidence%5Fin%5Fswissprot)).

Example: [D3DJ41](http://www.uniprot.org/uniprot/D3DJ41#ptm%5Fprocessing)

By similarity

Manual assertion inferred from sequence similarity

*   [UniProtKB:P11498](http://www.uniprot.org/uniprot/P11498)

FT   MOD\_RES     609    609       N6-biotinyllysine.
FT                                {ECO:0000250|UniProtKB:P11498}.

#### Evidence that is used in manual and automatic assertions

##### Sequence model evidence

We use the ECO code [ECO:0000255](http://bioportal.bioontology.org/ontologies/50043/?p=terms%26conceptid=ECO:0000255) in manual assertions and [ECO:0000256](http://bioportal.bioontology.org/ontologies/50043/?p=terms%26conceptid=ECO:0000256) (and its descendant code [ECO:0000259](http://bioportal.bioontology.org/ontologies/50043/?p=terms%26conceptid=ECO:0000259)) in automatic assertions, respectively, for information which has been generated by the UniProtKB [automatic annotation](http://www.uniprot.org/help/automatic%5Fannotation) system. The database name and identifier of the sequence model rule that has been used by the system are provided.

The ECO code [ECO:0000255](http://bioportal.bioontology.org/ontologies/50043/?p=terms%26conceptid=ECO:0000255) is also used for information which has been generated by various sequence analysis programs that are used during the manual curation process and which has been verified by a curator.

Example: [P0A940](http://www.uniprot.org/uniprot/P0A940#family%5Fand%5Fdomains)

UniRule annotation

Manual assertion according to rules

*   [HAMAP-Rule:MF\_00979](http://hamap.expasy.org/unirule/MF_00979)

  
  
PROSITE-ProRule annotations

Manual assertion according to rules

*   [PROSITE-ProRule:PRU00169](http://prosite.expasy.org/unirule/PRU00169)

  
  
Sequence Analysis

Manual assertion according to rules

CC   -!- SIMILARITY: Belongs to the BamA family. {ECO:0000255|HAMAP-
CC       Rule:MF\_01430}.
FT   TOPO\_DOM    790    803       Extracellular; loop 8. {ECO:0000305}.
FT   TRANSMEM    804    808       Beta stranded.
FT                                {ECO:0000269|PubMed:24914988}.
FT   DOMAIN       24     91       POTRA 1. {ECO:0000255|PROSITE-
FT                                ProRule:PRU01115,
FT                                ECO:0000305|PubMed:14559180}.

Example: [Q86NT5](http://www.uniprot.org/uniprot/Q86NT5#function)

UniRule annotation

Automatic assertion according to rules

*   [PIRSR000106-3](http://www.uniprot.org/unirule/UR000176873)

  
  
UniRule annotation

Automatic assertion according to rules

*   [RuleBase:RU003426](http://www.uniprot.org/unirule/UR000000446)

  
  
Sequence analysis

Automatic assertion according to rules

*   [SAM:Phobius](http://www.uniprot.org/help/sam)

CC   -!- SIMILARITY: Belongs to the malic enzymes family.
CC       {ECO:0000256|RuleBase:RU003426}.
KW   Membrane {ECO:0000256|SAM:Phobius};
KW   Metal-binding {ECO:0000256|PIRSR:PIRSR000106-3,
KW   ECO:0000256|RuleBase:RU003426};
KW   Transmembrane {ECO:0000256|SAM:Phobius};
KW   Transmembrane helix {ECO:0000256|SAM:Phobius}.
FT   TRANSMEM    327    345       Helical. {ECO:0000256|SAM:Phobius}.
FT   METAL       277    277       Divalent metal cation.
FT                                {ECO:0000256|PIRSR:PIRSR000106-3}.

##### Imported information evidence

We use the ECO code [ECO:0000312](http://bioportal.bioontology.org/ontologies/50043/?p=terms%26conceptid=ECO:0000312) in manual assertions and [ECO:0000313](http://bioportal.bioontology.org/ontologies/50043/?p=terms%26conceptid=ECO:0000313) in automatic assertions, respectively, for information which has been imported from another database. The database name and identifier of the entry from which the information has been imported are provided.

Example: [Q4JIM5](http://www.uniprot.org/uniprot/Q4JIM5#names%5Fand%5Ftaxonomy)

Imported

Manual assertion inferred from database entries

*   [EMBL:AAY86039.1](https://www.ebi.ac.uk/ena/browser/view/AAY86039)
*   [MGI:87860](http://www.informatics.jax.org/marker/MGI:87860)

GN   Name=Abl2 {ECO:0000312|EMBL:AAY86039.1, ECO:0000312|MGI:MGI:87860};

Example: [Q2L9A9](http://www.uniprot.org/uniprot/Q2L9A9#names%5Fand%5Ftaxonomy)

Imported

Automatic assertion inferred from database entries

*   [EMBL:ABC70327.1](https://www.ebi.ac.uk/ena/browser/view/ABC70327)
*   [MGI:96952](http://www.informatics.jax.org/marker/MGI:96952)

GN   Name=Mdm2 {ECO:0000313|EMBL:ABC70327.1, ECO:0000313|MGI:MGI:96952};

##### Combinatorial evidence

We use the ECO code [ECO:0000244](http://bioportal.bioontology.org/ontologies/50043/?p=terms%26conceptid=ECO:0000244) in manual assertions and [ECO:0000213](http://bioportal.bioontology.org/ontologies/50043/?p=terms%26conceptid=ECO:0000213) in automatic assertions, respectively, for information inferred from a combination of experimental and computational evidence. It is currently used in UniProtKB for published large-scale proteomics data and a subset of 3D structural data for which UniProt makes use of computational procedures to generate the data. If the experimental evidence is derived from a paper, the PubMed identifier of the paper is provided. For experimental data derived from the Protein Data Bank, the PDB code is provided.

Example: [P83256](http://www.uniprot.org/uniprot/P83256#structure)

Combined sources

Manual assertion inferred from algorithms based on publications or databases entries

*   [PDB:1V90](http://www.ebi.ac.uk/pdbe-srv/view/entry/1V90)

FT   STRAND        5      7       {ECO:0000244|PDB:1V90}.
FT   TURN         11     13       {ECO:0000244|PDB:1V90}.
FT   STRAND       26     29       {ECO:0000244|PDB:1V90}.

#### Related documents

[Why don't all UniProtKB/Swiss-Prot annotations have evidence?](http://www.uniprot.org/faq/evidence%5Fin%5Fswissprot)  
  
[How can I query UniProtKB annotations by evidence?](http://www.uniprot.org/faq/evidence%5Ftable) - A guide to evidence codes and labels in entry view and advanced search
        