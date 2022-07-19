---
title: UniProtKB return fields for cross-references
type: help
categories: Text_search,Technical,Website,help
---

# Databases/External links

This document also explains about differences in the names of the returned fields between new and old APIs.
This document is only for external cross-references. <br />
Please see example in [Return Fields](https://www.uniprot.org/help/return_fields) for usage in API.

## Sequences

| **Label\*** | **Legacy Returned Field** | **Returned Field** |
| :---------: | :-----------------------: | :----------------: |
|    CCDS     |      database(CCDS)       |     xref_ccds      |
|    EMBL     |      database(EMBL)       |     xref_embl      |
|     PIR     |       database(PIR)       |      xref_pir      |
|   RefSeq    |     database(RefSeq)      |    xref_refseq     |

_\* Label in the old and new API unless otherwise specified_

## 3D structure

| **Label\*** | **Legacy Returned Field** | **Returned Field** |
| :---------: | :-----------------------: | :----------------: |
|    BMRB     |      database(BMRB)       |     xref_bmrb      |
|    PCDDB    |      database(PCDDB)      |     xref_pcddb     |
|     PDB     |       database(PDB)       |      xref_pdb      |
|   PDBsum    |     database(PDBsum)      |    xref_pdbsum     |
|   SASBDB    |     database(SASBDB)      |    xref_sasbdb     |
|     SMR     |       database(SMR)       |      xref_smr      |

## Protein-protein interaction

|  **Label\***  | **Legacy Returned Field** | **Returned Field** |
| :-----------: | :-----------------------: | :----------------: |
|    BioGRID    |     database(BioGRID)     |    xref_biogrid    |
| ComplexPortal |  database(ComplexPortal)  |     xref_corum     |
|     CORUM     |      database(CORUM)      | xref_complexportal |
|      DIP      |       database(DIP)       |      xref_dip      |
|      ELM      |       database(ELM)       |      xref_elm      |
|    IntAct     |     database(IntAct)      |    xref_intact     |
|     MINT      |      database(MINT)       |     xref_mint      |
|    STRING     |     database(STRING)      |    xref_string     |

## Chemistry

|     **Label\***     |   **Legacy Returned Field**   |    **Returned Field**    |
| :-----------------: | :---------------------------: | :----------------------: |
|      BindingDB      |      database(BindingDB)      |      xref_bindingdb      |
|       ChEMBL        |       database(ChEMBL)        |       xref_chembl        |
|      DrugBank       |      database(DrugBank)       |      xref_drugbank       |
|     DrugCentral     |     database(DrugCentral)     |     xref_drugcentral     |
| GuidetoPHARMACOLOGY | database(GuidetoPHARMACOLOGY) | xref_guidetopharmacology |
|     SwissLipids     |     database(SwissLipids)     |     xref_swisslipids     |

## Protein family/group

| **Label\***  | **Legacy Returned Field** | **Returned Field** |
| :----------: | :-----------------------: | :----------------: |
|  Allergome   |    database(Allergome)    |   xref_allergome   |
|     CAZy     |      database(CAZy)       |     xref_cazy      |
|     CLAE     |      database(CLAE)       |     xref_clae      |
|    ESTHER    |     database(ESTHER)      |    xref_esther     |
|    IDEAL     |            NA             |     xref_ideal     |
| IMGT_GENE-DB |  database(IMGT GENE-DB)   | xref_imgt_gene-db  |
|    MEROPS    |     database(MEROPS)      |    xref_merops     |
|    MoonDB    |     database(MoonDB)      |    xref_moondb     |
|   MoonProt   |    database(MoonProt)     |   xref_moonprot    |
|  PeroxiBase  |   database(PeroxiBase)    |  xref_peroxibase   |
|    REBASE    |     database(REBASE)      |    xref_rebase     |
|     TCDB     |      database(TCDB)       |     xref_tcdb      |
|  UniLectin   |    database(UniLectin)    |   xref_unilectin   |

## PTM

|   **Label\***   | **Legacy Returned Field** |  **Returned Field**  |
| :-------------: | :-----------------------: | :------------------: |
|   CarbonylDB    |   database(CarbonylDB)    |   xref_carbonyldb    |
|      DEPOD      |      database(DEPOD)      |      xref_depod      |
|   GlyConnect    |   database(GlyConnect)    |   xref_glyconnect    |
|     GlyGen      |     database(GlyGen)      |     xref_glygen      |
|     iPTMnet     |     database(iPTMnet)     |     xref_iptmnet     |
|    MetOSite     |    database(MetOSite)     |    xref_metosite     |
| PhosphoSitePlus | database(PhosphoSitePlus) | xref_phosphositeplus |
|    SwissPalm    |    database(SwissPalm)    |    xref_swisspalm    |
|    UniCarbKB    |            NA             |    xref_unicarbkb    |

## Genetic variation/Polymorphism and mutation

| **Label\*** | **Legacy Returned Field** | **Returned Field** |
| :---------: | :-----------------------: | :----------------: |
|   BioMuta   |     database(BioMuta)     |    xref_biomuta    |
|    dbSNP    |      database(dbSNP)      |     xref_dbsnp     |
|    DMDM     |      database(DMDM)       |     xref_dmdm      |

## 2D gel

|     **Label\***     |   **Legacy Returned Field**   |    **Returned Field**    |
| :-----------------: | :---------------------------: | :----------------------: |
| COMPLUYEAST-2DPAGE  | database(COMPLUYEAST-2DPAGE)  | xref_compluyeast-2dpage  |
|  DOSAC-COBS-2DPAGE  |  database(DOSAC-COBS-2DPAGE)  |  xref_dosac-cobs-2dpage  |
|         OGP         |         database(OGP)         |         xref_ogp         |
| REPRODUCTION-2DPAGE | database(REPRODUCTION-2DPAGE) | xref_reproduction-2dpage |
|    SWISS-2DPAGE     |    database(SWISS-2DPAGE)     |    xref_swiss-2dpage     |
|     UCD-2DPAGE      |     database(UCD-2DPAGE)      |     xref_ucd-2dpage      |
|    World-2DPAGE     |    database(World-2DPAGE)     |    xref_world-2dpage     |

## Proteomic

|    **Label\***    |  **Legacy Returned Field**  |   **Returned Field**   |
| :---------------: | :-------------------------: | :--------------------: |
|       CPTAC       |       database(CPTAC)       |       xref_cptac       |
|        EPD        |        database(EPD)        |        xref_epd        |
|       jPOST       |       database(jPOST)       |      xref_massive      |
|      MassIVE      |      database(MassIVE)      |       xref_maxqb       |
|       MaxQB       |       database(MaxQB)       |       xref_pride       |
|       PaxDb       |       database(PaxDb)       |       xref_paxdb       |
|   PeptideAtlas    |   database(PeptideAtlas)    |   xref_peptideatlas    |
|       PRIDE       |       database(PRIDE)       |      xref_promex       |
|      ProMEX       |      database(ProMEX)       |   xref_proteomicsdb    |
|   ProteomicsDB    |   database(ProteomicsDB)    | xref_topdownproteomics |
| TopDownProteomics | database(TopDownProteomics) |       xref_jpost       |

## Protocols and materials

|  **Label\***  | **Legacy Returned Field** | **Returned Field** |
| :-----------: | :-----------------------: | :----------------: |
|     ABCD      |      database(ABCD)       |     xref_abcd      |
| Antibodypedia |  database(Antibodypedia)  | xref_antibodypedia |
|     CPTC      |      database(CPTC)       |     xref_cptc      |
|     DNASU     |      database(DNASU)      |     xref_dnasu     |

## Genome annotation

|   **Label\***   | **Legacy Returned Field** |  **Returned Field**  |
| :-------------: | :-----------------------: | :------------------: |
|     Ensembl     |     database(Ensembl)     |     xref_ensembl     |
| EnsemblBacteria | database(EnsemblBacteria) | xref_ensemblbacteria |
|  EnsemblFungi   |  database(EnsemblFungi)   |  xref_ensemblfungi   |
| EnsemblMetazoa  | database(EnsemblMetazoa)  | xref_ensemblmetazoa  |
|  EnsemblPlants  |  database(EnsemblPlants)  |  xref_ensemblplants  |
| EnsemblProtists | database(EnsemblProtists) | xref_ensemblprotists |
|     GeneDB      |     database(GeneDB)      |     xref_genedb      |
|     GeneID      |     database(GeneID)      |     xref_geneid      |
|     Gramene     |     database(Gramene)     |     xref_gramene     |
|      KEGG       |      database(KEGG)       |      xref_kegg       |
|     PATRIC      |     database(PATRIC)      |     xref_patric      |
|      UCSC       |      database(UCSC)       |      xref_ucsc       |
|   VectorBase    |            NA             |   xref_vectorbase    |
|   WBParaSite    |   database(WBParaSite)    |   xref_wbparasite    |

## Organism-specific

|  **Label\***  | **Legacy Returned Field** | **Returned Field** |
| :-----------: | :-----------------------: | :----------------: |
| ArachnoServer |  database(ArachnoServer)  | xref_arachnoserver |
|    Araport    |     database(Araport)     |    xref_araport    |
|      CGD      |       database(CGD)       |      xref_cgd      |
|  ConoServer   |   database(ConoServer)    |  xref_conoserver   |
|      CTD      |       database(CTD)       |      xref_ctd      |
|   dictyBase   |    database(dictyBase)    |   xref_dictybase   |
|   DisGeNET    |    database(DisGeNET)     |   xref_disgenet    |
|   EchoBASE    |    database(EchoBASE)     |   xref_echobase    |
|    euHCVdb    |     database(euHCVdb)     |    xref_euhcvdb    |
|    FlyBase    |     database(FlyBase)     |    xref_flybase    |
|   GeneCards   |    database(GeneCards)    |   xref_genecards   |
|  GeneReviews  |   database(GeneReviews)   |  xref_genereviews  |
|     HGNC      |      database(HGNC)       |     xref_hgnc      |
|      HPA      |       database(HPA)       |      xref_hpa      |
|   LegioList   |    database(LegioList)    |   xref_legiolist   |
|    Leproma    |     database(Leproma)     |    xref_leproma    |
|   MaizeGDB    |    database(MaizeGDB)     |   xref_maizegdb    |
|   MalaCards   |    database(MalaCards)    |   xref_malacards   |
|      MGI      |       database(MGI)       |      xref_mgi      |
|      MIM      |       database(MIM)       |      xref_mim      |
|   neXtProt    |    database(neXtProt)     |   xref_nextprot    |
|    NIAGADS    |     database(NIAGADS)     |    xref_niagads    |
|  OpenTargets  |   database(OpenTargets)   |  xref_opentargets  |
|   Orphanet    |    database(Orphanet)     |   xref_orphanet    |
|   PharmGKB    |    database(PharmGKB)     |   xref_pharmgkb    |
|   PHI-base    |            NA             |   xref_phi-base    |
|    PomBase    |     database(PomBase)     |    xref_pombase    |
|   PseudoCAP   |    database(PseudoCAP)    |   xref_pseudocap   |
|      RGD      |       database(RGD)       |      xref_rgd      |
|      SGD      |       database(SGD)       |      xref_sgd      |
|     TAIR      |      database(TAIR)       |     xref_tair      |
|  TubercuList  |   database(TubercuList)   |  xref_tuberculist  |
|   VEuPathDB   |    database(VEuPathDB)    |   xref_veupathdb   |
|     VGNC      |      database(VGNC)       |     xref_vgnc      |
|   WormBase    |    database(WormBase)     |   xref_wormbase    |
|    Xenbase    |     database(Xenbase)     |    xref_xenbase    |
|     ZFIN      |      database(ZFIN)       |     xref_zfin      |

## Phylogenomic

| **Label\*** | **Legacy Returned Field** | **Returned Field** |
| :---------: | :-----------------------: | :----------------: |
|   eggNOG    |     database(eggNOG)      |    xref_eggnog     |
|  GeneTree   |    database(GeneTree)     |   xref_genetree    |
|   HOGENOM   |     database(HOGENOM)     |    xref_hogenom    |
| InParanoid  |   database(InParanoid)    |  xref_inparanoid   |
|     KO      |            NA             |      xref_ko       |
|     OMA     |       database(OMA)       |      xref_oma      |
|   OrthoDB   |     database(OrthoDB)     |    xref_orthodb    |
|  PhylomeDB  |    database(PhylomeDB)    |   xref_phylomedb   |
|   TreeFam   |     database(TreeFam)     |    xref_treefam    |

## Enzyme and pathway

|  **Label\***   | **Legacy Returned Field** | **Returned Field**  |
| :------------: | :-----------------------: | :-----------------: |
|     BioCyc     |     database(BioCyc)      |     xref_biocyc     |
|     BRENDA     |     database(BRENDA)      |     xref_brenda     |
| PathwayCommons | database(PathwayCommons)  | xref_pathwaycommons |
| PlantReactome  |  database(PlantReactome)  | xref_plantreactome  |
|    Reactome    |    database(Reactome)     |    xref_reactome    |
|    SABIO-RK    |    database(SABIO-RK)     |    xref_sabio-rk    |
|   SignaLink    |    database(SignaLink)    |   xref_signalink    |
|     SIGNOR     |     database(SIGNOR)      |     xref_signor     |
|   UniPathway   |   database(UniPathway)    |   xref_unipathway   |

## Miscellaneous

|    **Label\***    |  **Legacy Returned Field**  |    **Returned Field**     |
| :---------------: | :-------------------------: | :-----------------------: |
|   BioGRID-ORCS    |   database(BioGRID-ORCS)    |     xref_biogrid-orcs     |
|      ChiTaRS      |      database(ChiTaRS)      |       xref_chitars        |
| EvolutionaryTrace | database(EvolutionaryTrace) |  xref_evolutionarytrace   |
|     GeneWiki      |     database(GeneWiki)      |       xref_genewiki       |
|    GenomeRNAi     |    database(GenomeRNAi)     |      xref_genomernai      |
|      Pharos       |      database(Pharos)       |        xref_pharos        |
|     PHI-base      |     database(PHI-base)      | **See Organism-specific** |
|        PRO        |        database(PRO)        |         xref_pro          |
|       RNAct       |       database(RNAct)       |        xref_rnact         |

## Gene expression

|   **Label\***   | **Legacy Returned Field** |  **Returned Field**  |
| :-------------: | :-----------------------: | :------------------: |
|      Bgee       |      database(Bgee)       |      xref_bgee       |
|    CollecTF     |    database(CollecTF)     |    xref_collectf     |
| ExpressionAtlas | database(ExpressionAtlas) | xref_expressionatlas |
|   Genevisible   |   database(Genevisible)   |   xref_genevisible   |
|     CleanEx     |            NA             |     xref_cleanex     |

## Family and domain

| **Label\*** | **Legacy Returned Field** |      **Returned Field**      |
| :---------: | :-----------------------: | :--------------------------: |
|     CDD     |       database(CDD)       |           xref_cdd           |
|   DisProt   |     database(DisProt)     |         xref_disprot         |
|   Gene3D    |     database(Gene3D)      |         xref_gene3d          |
|    HAMAP    |      database(HAMAP)      |          xref_hamap          |
|    IDEAL    |      database(IDEAL)      | **See Protein family/group** |
|  InterPro   |    database(InterPro)     |        xref_interpro         |
|   PANTHER   |     database(PANTHER)     |         xref_panther         |
|    Pfam     |      database(Pfam)       |          xref_pfam           |
|    PIRSF    |      database(PIRSF)      |          xref_pirsf          |
|   PRINTS    |     database(PRINTS)      |         xref_prints          |
|   ProDom    |            NA             |         xref_prodom          |
|   PROSITE   |     database(PROSITE)     |         xref_prosite         |
|    SFLD     |      database(SFLD)       |          xref_sfld           |
|    SMART    |      database(SMART)      |          xref_smart          |
|   SUPFAM    |     database(SUPFAM)      |         xref_supfam          |
|  TIGRFAMs   |    database(TIGRFAMs)     |        xref_tigrfams         |
