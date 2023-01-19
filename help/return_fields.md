---
title: UniProtKB return fields
type: help
categories: Text_search,Technical,Website,help
---

# UniProtKB column names for programmatic access

This document lists the differences between the returned columns by RESTful APIs.
User can ask required columns returned by an API by passing the _Returned Field_ in the request url
and the response will have those requested fields.

A specific page listing cross-reference fields can be found here: [Return Fields Databases](https://www.uniprot.org/help/return_fields_databases).

For example, to get UniProtKB entry with accession and proteomes in new API run the below `curl` command:

```bash
curl https://rest.uniprot.org/uniprotkb/search?query=human&fields=accession,xref_proteomes
```

The `Label` is the readable name of the returned field. The `Label` is shown on the website/TSV or in Excel format.

# Names & Taxonomy

|        **Label\***         | **Legacy Returned Field** | **Returned Field** |
| :------------------------: | :-----------------------: | :----------------: |
|           Entry            |            id             |     accession      |
|         Entry Name         |        entry name         |         id         |
|         Gene Names         |           genes           |     gene_names     |
|    Gene Names (primary)    |     genes(PREFERRED)      |    gene_primary    |
|    Gene Names (synonym)    |    genes(ALTERNATIVE)     |    gene_synonym    |
| Gene Names (ordered locus) |        genes(OLN)         |      gene_oln      |
|      Gene Names (ORF)      |        genes(ORF)         |      gene_orf      |
|          Organism          |         organism          |   organism_name    |
|        Organism ID         |        organism-id        |    organism_id     |
|       Protein names        |       protein names       |    protein_name    |
|         Proteomes          |         proteome          |   xref_proteomes   |
|     Taxonomic lineage      |       lineage(ALL)        |      lineage       |
|  Taxonomic lineage (IDs)   |       lineage(ALL)        |    lineage_ids     |
|        Virus hosts         |        virus hosts        |    virus_hosts     |

_\* Label in the old and new API unless otherwise specified_

# Sequences

|           **Label\***           |        **Legacy Returned Field**         |   **Returned Field**    |
| :-----------------------------: | :--------------------------------------: | :---------------------: |
|      Alternative products       |      comment(ALTERNATIVE PRODUCTS)       | cc_alternative_products |
|      Alternative sequence       |      feature(ALTERNATIVE SEQUENCE)       |       ft_var_seq        |
| Erroneous gene model prediction | comment(ERRONEOUS GENE MODEL PREDICTION) |    error_gmodel_pred    |
|            Fragment             |                 fragment                 |        fragment         |
|         Gene encoded by         |                encodedon                 |        organelle        |
|             Length              |                  length                  |         length          |
|              Mass               |                   mass                   |          mass           |
|        Mass spectrometry        |        comment(MASS SPECTROMETRY)        |  cc_mass_spectrometry   |
|         Natural variant         |         feature(NATURAL VARIANT)         |       ft_variant        |
|      Non-adjacent residues      |      feature(NON ADJACENT RESIDUES)      |       ft_non_cons       |
|      Non-standard residue       |      feature(NON STANDARD RESIDUE)       |       ft_non_std        |
|      Non-terminal residue       |      feature(NON TERMINAL RESIDUE)       |       ft_non_ter        |
|          Polymorphism           |          comment(POLYMORPHISM)           |     cc_polymorphism     |
|           RNA editing           |           comment(RNA EDITING)           |     cc_rna_editing      |
|            Sequence             |                 sequence                 |        sequence         |
|        Sequence caution         |        comment(SEQUENCE CAUTION)         |   cc_sequence_caution   |
|        Sequence conflict        |        feature(SEQUENCE CONFLICT)        |       ft_conflict       |
|      Sequence uncertainty       |      feature(SEQUENCE UNCERTAINTY)       |        ft_unsure        |
|        Sequence version         |            version(sequence)             |    sequence_version     |

# Function

|      **Label\***       |    **Legacy Returned Field**    |   **Returned Field**   |
| :--------------------: | :-----------------------------: | :--------------------: |
|       Absorption       |       comment(ABSORPTION)       |       absorption       |
|      Active site       |      feature(ACTIVE SITE)       |      ft_act_site       |
|  Activity regulation   |  comment(ACTIVITY REGULATION)   | cc_activity_regulation |
|      Binding site      |      feature(BINDING SITE)      |       ft_binding       |
|    Calcium binding     |              chebi              |       ft_ca_bind       |
|   Catalytic activity   |    chebi(Catalytic activity)    | cc_catalytic_activity  |
|        Cofactor        |         chebi(Cofactor)         |      cc_cofactor       |
|      DNA binding       |      feature(DNA BINDING)       |      ft_dna_bind       |
|       EC number        |               ec                |           ec           |
|     Function [CC]      |        comment(FUNCTION)        |      cc_function       |
|        Kinetics        |        comment(KINETICS)        |        kinetics        |
|     Metal binding      |     feature(METAL BINDING)      |        ft_metal        |
|   Nucleotide binding   |        feature(NP BIND)         |       ft_np_bind       |
|        Pathway         |        comment(PATHWAY)         |       cc_pathway       |
|     pH dependence      |     comment(PH DEPENDENCE)      |     ph_dependence      |
|    Redox potential     |    comment(REDOX POTENTIAL)     |    redox_potential     |
|        Rhea ID         |             rhea-id             |          rhea          |
|          Site          |          feature(SITE)          |        ft_site         |
| Temperature dependence | comment(TEMPERATURE DEPENDENCE) |    temp_dependence     |

# Miscellaneous

|    **Label\***     | **Legacy Returned Field** | **Returned Field** |
| :----------------: | :-----------------------: | :----------------: |
|     Annotation     |     annotation score      |  annotation_score  |
|      Caution       |     comment(CAUTION)      |     cc_caution     |
|   Comment Count    |    \<does not exist\>     |   comment_count    |
|      Features      |         features          |   feature_count    |
|     Keyword ID     |        keyword-id         |     keywordid      |
|      Keywords      |         keywords          |      keyword       |
|    Matched text    |          context          | \<does not exist\> |
| Miscellaneous [CC] |  comment(MISCELLANEOUS)   |  cc_miscellaneous  |
| Protein existence  |         existence         | protein_existence  |
|      Reviewed      |         reviewed          |      reviewed      |
|       Tools        |           tools           |       tools        |
|      UniParc       |         uniparcid         |     uniparc_id     |

# Interaction

|      **Label\***      | **Legacy Returned Field** | **Returned Field** |
| :-------------------: | :-----------------------: | :----------------: |
|    Interacts with     |        interactor         |   cc_interaction   |
| Subunit structure[CC] |     comment(SUBUNIT)      |     cc_subunit     |

# Expression

|     **Label\***     |  **Legacy Returned Field**   |   **Returned Field**   |
| :-----------------: | :--------------------------: | :--------------------: |
| Developmental stage | comment(DEVELOPMENTAL STAGE) | cc_developmental_stage |
|      Induction      |      comment(INDUCTION)      |      cc_induction      |
| Tissue specificity  | comment(TISSUE SPECIFICITY)  | cc_tissue_specificity  |

# Gene Ontology (GO)

|            **Label\***             | **Legacy Returned Field** | **Returned Field** |
| :--------------------------------: | :-----------------------: | :----------------: |
| Gene ontology (biological process) |  go(biological process)   |        go_p        |
| Gene ontology (cellular component) |  go(cellular component)   |        go_c        |
|         Gene ontology (GO)         |            go             |         go         |
| Gene ontology (molecular function) |  go(molecular function)   |        go_f        |
|         Gene ontology IDs          |           go-id           |       go_id        |

# Pathology & Biotech

|      **Label\***       |   **Legacy Returned Field**   |   **Returned Field**    |
| :--------------------: | :---------------------------: | :---------------------: |
| Allergenic properties  |       comment(ALLERGEN)       |       cc_allergen       |
|  Biotechnological use  |    comment(BIOTECHNOLOGY)     |    cc_biotechnology     |
|  Disruption phenotype  | comment(DISRUPTION PHENOTYPE) | cc_disruption_phenotype |
| Involvement in disease |       comment(DISEASE)        |       cc_disease        |
|      Mutagenesis       |     feature(MUTAGENESIS)      |       ft_mutagen        |
|   Pharmaceutical use   |    comment(PHARMACEUTICAL)    |    cc_pharmaceutical    |
|       Toxic dose       |      comment(TOXIC DOSE)      |      cc_toxic_dose      |

# Subcellular location

|       **Label\***        |   **Legacy Returned Field**   |   **Returned Field**    |
| :----------------------: | :---------------------------: | :---------------------: |
|      Intramembrane       |    feature(INTRAMEMBRANE)     |       ft_intramem       |
| Subcellular location[CC] | comment(SUBCELLULAR LOCATION) | cc_subcellular_location |
|    Topological domain    |  feature(TOPOLOGICAL DOMAIN)  |       ft_topo_dom       |
|      Transmembrane       |    feature(TRANSMEMBRANE)     |       ft_transmem       |

# PTM / Processsing

|           **Label\***           |   **Legacy Returned Field**   | **Returned Field** |
| :-----------------------------: | :---------------------------: | :----------------: |
|              Chain              |        feature(CHAIN)         |      ft_chain      |
|           Cross-link            |      feature(CROSS LINK)      |    ft_crosslnk     |
|         Disulfide bond          |    feature(DISULFIDE BOND)    |    ft_disulfid     |
|          Glycosylation          |    feature(GLYCOSYLATION)     |    ft_carbohyd     |
|      Initiator methionine       | feature(INITIATOR METHIONINE) |    ft_init_met     |
|           Lipidation            |      feature(LIPIDATION)      |      ft_lipid      |
|        Modified residue         |   feature(MODIFIED RESIDUE)   |     ft_mod_res     |
|             Peptide             |       feature(PEPTIDE)        |     ft_peptide     |
| Post-translational modification |         comment(PTM)          |       cc_ptm       |
|           Propeptide            |      feature(PROPEPTIDE)      |     ft_propep      |
|         Signal peptide          |        feature(SIGNAL)        |     ft_signal      |
|         Transit peptide         |       feature(TRANSIT)        |     ft_transit     |

# Structure

| **Label\*** | **Legacy Returned Field** | **Returned Field** |
| :---------: | :-----------------------: | :----------------: |
|     3D      |            3d             |    structure_3d    |
| Beta strand |   feature(BETA STRAND)    |     ft_strand      |
|    Helix    |      feature(HELIX)       |      ft_helix      |
|    Turn     |       feature(TURN)       |      ft_turn       |

# Publications

|   **Label\***    | **Legacy Returned Field** | **Returned Field** |
| :--------------: | :-----------------------: | :----------------: |
| Mapped PubMed ID |      citationmapping      | \<does not exist\> |
|    PubMed ID     |         citation          |   lit_pubmed_id    |

# Date of

|            **Label\***             | **Legacy Returned Field** |   **Returned Field**   |
| :--------------------------------: | :-----------------------: | :--------------------: |
|          Date of creation          |          created          |      date_created      |
|     Date of last modification      |       last-modified       |     date_modified      |
| Date of last sequence modification |     sequence-modified     | date_sequence_modified |
|           Entry version            |      version(entry)       |        version         |

# Family & Domains

|      **Label\***      |  **Legacy Returned Field**  | **Returned Field** |
| :-------------------: | :-------------------------: | :----------------: |
|      Coiled coil      |    feature(COILED COIL)     |     ft_coiled      |
|  Compositional bias   | feature(COMPOSITIONAL BIAS) |    ft_compbias     |
|      Domain[CC]       |       comment(DOMAIN)       |     cc_domain      |
|      Domain[FT]       |   feature(DOMAIN EXTENT)    |     ft_domain      |
|         Motif         |       feature(MOTIF)        |      ft_motif      |
|   Protein families    |          families           |  protein_families  |
|        Region         |       feature(REGION)       |     ft_region      |
|        Repeat         |       feature(REPEAT)       |     ft_repeat      |
| Sequence similarities |     comment(SIMILARITY)     | \<does not exist\> |
|      Zinc finger      |    feature(ZINC FINGER)     |     ft_zn_fing     |

# Sequence Databases

| **Label\*** | **Legacy Returned Field** | **Returned Field** |
| :---------: | :-----------------------: | :----------------: |
|    CCDS     |      database(CCDS)       |     xref_ccds      |
|    EMBL     |      database(EMBL)       |     xref_embl      |
|     PIR     |       database(PIR)       |      xref_pir      |
|   RefSeq    |     database(RefSeq)      |    xref_refseq     |

# 3D Structure Databases

| **Label\*** | **Legacy Returned Field** | **Returned Field** |
| :---------: | :-----------------------: | :----------------: |
| AlphaFoldDB |   database(AlphaFoldDB)   |  xref_alphafolddb  |
|    BMRB     |      database(BMRB)       |     xref_bmrb      |
|    PCDDB    |      database(PCDDB)      |     xref_pcddb     |
|     PDB     |       database(PDB)       |      xref_pdb      |
|   PDBsum    |     database(PDBsum)      |    xref_pdbsum     |
|   SASBDB    |     database(SASBDB)      |    xref_sasbdb     |
|     SMR     |       database(SMR)       |      xref_smr      |

# Protein-Protein Interaction Databases

|  **Label\***  | **Legacy Returned Field** | **Returned Field** |
| :-----------: | :-----------------------: | :----------------: |
|    BioGRID    |     database(BioGRID)     |    xref_biogrid    |
|     CORUM     |      database(CORUM)      |     xref_corum     |
| ComplexPortal |  database(ComplexPortal)  | xref_complexportal |
|      DIP      |       database(DIP)       |      xref_dip      |
|      ELM      |       database(ELM)       |      xref_elm      |
|    IntAct     |     database(IntAct)      |    xref_intact     |
|     MINT      |      database(MINT)       |     xref_mint      |
|    STRING     |     database(STRING)      |    xref_string     |

# Chemistry Databases

|     **Label\***     |   **Legacy Returned Field**   |    **Returned Field**    |
| :-----------------: | :---------------------------: | :----------------------: |
|      BindingDB      |      database(BindingDB)      |      xref_bindingdb      |
|       ChEMBL        |       database(ChEMBL)        |       xref_chembl        |
|      DrugBank       |      database(DrugBank)       |      xref_drugbank       |
|     DrugCentral     |     database(DrugCentral)     |     xref_drugcentral     |
| GuidetoPHARMACOLOGY | database(GuidetoPHARMACOLOGY) | xref_guidetopharmacology |
|     SwissLipids     |     database(SwissLipids)     |     xref_swisslipids     |

# Protein Family/Group Databases

| **Label\***  | **Legacy Returned Field** | **Returned Field** |
| :----------: | :-----------------------: | :----------------: |
|  Allergome   |    database(Allergome)    |   xref_allergome   |
|     CAZy     |      database(CAZy)       |     xref_cazy      |
|     CLAE     |      database(CLAE)       |     xref_clae      |
|    ESTHER    |     database(ESTHER)      |    xref_esther     |
| IMGT_GENE-DB |  database(IMGT GENE-DB)   | xref_imgt_gene-db  |
|    MEROPS    |     database(MEROPS)      |    xref_merops     |
|    MoonDB    |     database(MoonDB)      |    xref_moondb     |
|   MoonProt   |    database(MoonProt)     |   xref_moonprot    |
|  PeroxiBase  |   database(PeroxiBase)    |  xref_peroxibase   |
|    REBASE    |     database(REBASE)      |    xref_rebase     |
|     TCDB     |      database(TCDB)       |     xref_tcdb      |
|  UniLectin   |    database(UniLectin)    |   xref_unilectin   |

# Ptm Databases

|   **Label\***   | **Legacy Returned Field** |  **Returned Field**  |
| :-------------: | :-----------------------: | :------------------: |
|   CarbonylDB    |   database(CarbonylDB)    |   xref_carbonyldb    |
|      DEPOD      |      database(DEPOD)      |      xref_depod      |
|   GlyConnect    |   database(GlyConnect)    |   xref_glyconnect    |
|     GlyGen      |     database(GlyGen)      |     xref_glygen      |
|    MetOSite     |    database(MetOSite)     |    xref_metosite     |
| PhosphoSitePlus | database(PhosphoSitePlus) | xref_phosphositeplus |
|    SwissPalm    |    database(SwissPalm)    |    xref_swisspalm    |
|    UniCarbKB    |    \<does not exist\>     |    xref_unicarbkb    |
|     iPTMnet     |     database(iPTMnet)     |     xref_iptmnet     |

# Genetic Variation Databases

| **Label\*** | **Legacy Returned Field** | **Returned Field** |
| :---------: | :-----------------------: | :----------------: |
|   BioMuta   |     database(BioMuta)     |    xref_biomuta    |
|    DMDM     |      database(DMDM)       |     xref_dmdm      |
|    dbSNP    |      database(dbSNP)      |     xref_dbsnp     |

# 2D Gel Databases

|     **Label\***     |   **Legacy Returned Field**   |    **Returned Field**    |
| :-----------------: | :---------------------------: | :----------------------: |
| COMPLUYEAST-2DPAGE  | database(COMPLUYEAST-2DPAGE)  | xref_compluyeast-2dpage  |
|  DOSAC-COBS-2DPAGE  |  database(DOSAC-COBS-2DPAGE)  |  xref_dosac-cobs-2dpage  |
|         OGP         |         database(OGP)         |         xref_ogp         |
| REPRODUCTION-2DPAGE | database(REPRODUCTION-2DPAGE) | xref_reproduction-2dpage |
|    SWISS-2DPAGE     |    database(SWISS-2DPAGE)     |    xref_swiss-2dpage     |
|     UCD-2DPAGE      |     database(UCD-2DPAGE)      |     xref_ucd-2dpage      |
|    World-2DPAGE     |    database(World-2DPAGE)     |    xref_world-2dpage     |

# Proteomic Databases

|    **Label\***    |  **Legacy Returned Field**  |   **Returned Field**   |
| :---------------: | :-------------------------: | :--------------------: |
|       CPTAC       |       database(CPTAC)       |       xref_cptac       |
|        EPD        |        database(EPD)        |        xref_epd        |
|      MassIVE      |      database(MassIVE)      |      xref_massive      |
|       MaxQB       |       database(MaxQB)       |       xref_maxqb       |
|       PRIDE       |       database(PRIDE)       |       xref_pride       |
|       PaxDb       |       database(PaxDb)       |       xref_paxdb       |
|   PeptideAtlas    |   database(PeptideAtlas)    |   xref_peptideatlas    |
|      ProMEX       |      database(ProMEX)       |      xref_promex       |
|   ProteomicsDB    |   database(ProteomicsDB)    |   xref_proteomicsdb    |
| TopDownProteomics | database(TopDownProteomics) | xref_topdownproteomics |
|       jPOST       |       database(jPOST)       |       xref_jpost       |

# Protocols And Materials Databases

|  **Label\***  | **Legacy Returned Field** | **Returned Field** |
| :-----------: | :-----------------------: | :----------------: |
|     ABCD      |      database(ABCD)       |     xref_abcd      |
| Antibodypedia |  database(Antibodypedia)  | xref_antibodypedia |
|     CPTC      |      database(CPTC)       |     xref_cptc      |
|     DNASU     |      database(DNASU)      |     xref_dnasu     |

# Genome Annotation Databases

|         **Label\***         | **Legacy Returned Field** |        **Returned Field**        |
| :-------------------------: | :-----------------------: | :------------------------------: |
|           Ensembl           |     database(Ensembl)     |           xref_ensembl           |
|       EnsemblBacteria       | database(EnsemblBacteria) |       xref_ensemblbacteria       |
|        EnsemblFungi         |  database(EnsemblFungi)   |        xref_ensemblfungi         |
|       EnsemblMetazoa        | database(EnsemblMetazoa)  |       xref_ensemblmetazoa        |
|        EnsemblPlants        |  database(EnsemblPlants)  |        xref_ensemblplants        |
|       EnsemblProtists       | database(EnsemblProtists) |       xref_ensemblprotists       |
|           GeneID            |     database(GeneID)      |           xref_geneid            |
|           Gramene           |     database(Gramene)     |           xref_gramene           |
|            KEGG             |      database(KEGG)       |            xref_kegg             |
|         MANE-Select         |   database(MANE-Select)   |         xref_mane-select         |
|           PATRIC            |     database(PATRIC)      |           xref_patric            |
|            UCSC             |      database(UCSC)       |            xref_ucsc             |
|         VectorBase          |    \<does not exist\>     |         xref_vectorbase          |
|         WBParaSite          |   database(WBParaSite)    |         xref_wbparasite          |
| WBParaSiteTranscriptProtein |    \<does not exist\>     | xref_wbparasitetranscriptprotein |

# Organism-Specific Databases

|  **Label\***  | **Legacy Returned Field** | **Returned Field** |
| :-----------: | :-----------------------: | :----------------: |
| ArachnoServer |  database(ArachnoServer)  | xref_arachnoserver |
|    Araport    |     database(Araport)     |    xref_araport    |
|      CGD      |       database(CGD)       |      xref_cgd      |
|      CTD      |       database(CTD)       |      xref_ctd      |
|  ConoServer   |   database(ConoServer)    |  xref_conoserver   |
|   DisGeNET    |    database(DisGeNET)     |   xref_disgenet    |
|   EchoBASE    |    database(EchoBASE)     |   xref_echobase    |
|    FlyBase    |     database(FlyBase)     |    xref_flybase    |
|   GeneCards   |    database(GeneCards)    |   xref_genecards   |
|  GeneReviews  |   database(GeneReviews)   |  xref_genereviews  |
|     HGNC      |      database(HGNC)       |     xref_hgnc      |
|      HPA      |       database(HPA)       |      xref_hpa      |
|   LegioList   |    database(LegioList)    |   xref_legiolist   |
|    Leproma    |     database(Leproma)     |    xref_leproma    |
|      MGI      |       database(MGI)       |      xref_mgi      |
|      MIM      |       database(MIM)       |      xref_mim      |
|   MaizeGDB    |    database(MaizeGDB)     |   xref_maizegdb    |
|   MalaCards   |    database(MalaCards)    |   xref_malacards   |
|    NIAGADS    |     database(NIAGADS)     |    xref_niagads    |
|  OpenTargets  |   database(OpenTargets)   |  xref_opentargets  |
|   Orphanet    |    database(Orphanet)     |   xref_orphanet    |
|   PharmGKB    |    database(PharmGKB)     |   xref_pharmgkb    |
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
|   dictyBase   |    database(dictyBase)    |   xref_dictybase   |
|    euHCVdb    |     database(euHCVdb)     |    xref_euhcvdb    |
|   neXtProt    |    database(neXtProt)     |   xref_nextprot    |

# Phylogenomic Databases

| **Label\*** | **Legacy Returned Field** | **Returned Field** |
| :---------: | :-----------------------: | :----------------: |
|  GeneTree   |    database(GeneTree)     |   xref_genetree    |
|   HOGENOM   |     database(HOGENOM)     |    xref_hogenom    |
| InParanoid  |   database(InParanoid)    |  xref_inparanoid   |
|     KO      |    \<does not exist\>     |      xref_ko       |
|     OMA     |       database(OMA)       |      xref_oma      |
|   OrthoDB   |     database(OrthoDB)     |    xref_orthodb    |
|  PhylomeDB  |    database(PhylomeDB)    |   xref_phylomedb   |
|   TreeFam   |     database(TreeFam)     |    xref_treefam    |
|   eggNOG    |     database(eggNOG)      |    xref_eggnog     |

# Enzyme And Pathway Databases

|  **Label\***   | **Legacy Returned Field** | **Returned Field**  |
| :------------: | :-----------------------: | :-----------------: |
|     BRENDA     |     database(BRENDA)      |     xref_brenda     |
|     BioCyc     |     database(BioCyc)      |     xref_biocyc     |
| PathwayCommons | database(PathwayCommons)  | xref_pathwaycommons |
| PlantReactome  |  database(PlantReactome)  | xref_plantreactome  |
|    Reactome    |    database(Reactome)     |    xref_reactome    |
|    SABIO-RK    |    database(SABIO-RK)     |    xref_sabio-rk    |
|     SIGNOR     |     database(SIGNOR)      |     xref_signor     |
|   SignaLink    |    database(SignaLink)    |   xref_signalink    |
|   UniPathway   |   database(UniPathway)    |   xref_unipathway   |

# Miscellaneous Databases

|    **Label\***    |  **Legacy Returned Field**  |   **Returned Field**   |
| :---------------: | :-------------------------: | :--------------------: |
|   BioGRID-ORCS    |   database(BioGRID-ORCS)    |   xref_biogrid-orcs    |
|      ChiTaRS      |      database(ChiTaRS)      |      xref_chitars      |
| EvolutionaryTrace | database(EvolutionaryTrace) | xref_evolutionarytrace |
|     GeneWiki      |     database(GeneWiki)      |     xref_genewiki      |
|    GenomeRNAi     |    database(GenomeRNAi)     |    xref_genomernai     |
|     PHI-base      |     database(PHI-base)      |     xref_phi-base      |
|        PRO        |        database(PRO)        |        xref_pro        |
|      Pharos       |      database(Pharos)       |      xref_pharos       |
|       RNAct       |       database(RNAct)       |       xref_rnact       |

# Gene Expression Databases

|   **Label\***   | **Legacy Returned Field** |  **Returned Field**  |
| :-------------: | :-----------------------: | :------------------: |
|      Bgee       |      database(Bgee)       |      xref_bgee       |
|     CleanEx     |    \<does not exist\>     |     xref_cleanex     |
|    CollecTF     |    database(CollecTF)     |    xref_collectf     |
| ExpressionAtlas | database(ExpressionAtlas) | xref_expressionatlas |
|   Genevisible   |   database(Genevisible)   |   xref_genevisible   |

# Family And Domain Databases

| **Label\*** | **Legacy Returned Field** | **Returned Field** |
| :---------: | :-----------------------: | :----------------: |
|     CDD     |       database(CDD)       |      xref_cdd      |
|   DisProt   |     database(DisProt)     |    xref_disprot    |
|   Gene3D    |     database(Gene3D)      |    xref_gene3d     |
|    HAMAP    |      database(HAMAP)      |     xref_hamap     |
|    IDEAL    |      database(IDEAL)      |     xref_ideal     |
|  InterPro   |    database(InterPro)     |   xref_interpro    |
|   PANTHER   |     database(PANTHER)     |    xref_panther    |
|    PIRSF    |      database(PIRSF)      |     xref_pirsf     |
|   PRINTS    |     database(PRINTS)      |    xref_prints     |
|   PROSITE   |     database(PROSITE)     |    xref_prosite    |
|    Pfam     |      database(Pfam)       |     xref_pfam      |
|   ProDom    |    \<does not exist\>     |    xref_prodom     |
|    SFLD     |      database(SFLD)       |     xref_sfld      |
|    SMART    |      database(SMART)      |     xref_smart     |
|   SUPFAM    |     database(SUPFAM)      |    xref_supfam     |
|  TIGRFAMs   |    database(TIGRFAMs)     |   xref_tigrfams    |
