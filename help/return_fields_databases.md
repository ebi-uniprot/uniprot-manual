---
title: UniProtKB return fields for cross-references
type: help
categories: Text_search,Technical,Website,help
---

# Databases/External links

This document also explains about differences in the names of the returned fields between new and old APIs.
This document is only for external cross-references.

Please see example in [Return Fields](https://www.uniprot.org/help/return_fields) for usage in API.

## Sequences

| Label  | Returned Field |
| ------ | -------------- |
| CCDS   | xref_ccds      |
| EMBL   | xref_embl      |
| PIR    | xref_pir       |
| RefSeq | xref_refseq    |

## 3D structure

| Label  | Returned Field |
| ------ | -------------- |
| BMRB   | xref_bmrb      |
| PCDDB  | xref_pcddb     |
| PDB    | xref_pdb       |
| PDBsum | xref_pdbsum    |
| SASBDB | xref_sasbdb    |
| SMR    | xref_smr       |

## Protein-protein interaction

| Label         | Returned Field     |
| ------------- | ------------------ |
| BioGRID       | xref_biogrid       |
| ComplexPortal | xref_corum         |
| CORUM         | xref_complexportal |
| DIP           | xref_dip           |
| ELM           | xref_elm           |
| IntAct        | xref_intact        |
| MINT          | xref_mint          |
| STRING        | xref_string        |

## Chemistry

| Label               | Returned Field           |
| ------------------- | ------------------------ |
| BindingDB           | xref_bindingdb           |
| ChEMBL              | xref_chembl              |
| DrugBank            | xref_drugbank            |
| DrugCentral         | xref_drugcentral         |
| GuidetoPHARMACOLOGY | xref_guidetopharmacology |
| SwissLipids         | xref_swisslipids         |

## Protein family/group

| Label        | Returned Field    |
| ------------ | ----------------- |
| Allergome    | xref_allergome    |
| CAZy         | xref_cazy         |
| CLAE         | xref_clae         |
| ESTHER       | xref_esther       |
| IDEAL        | xref_ideal        |
| IMGT_GENE-DB | xref_imgt_gene-db |
| MEROPS       | xref_merops       |
| MoonDB       | xref_moondb       |
| MoonProt     | xref_moonprot     |
| PeroxiBase   | xref_peroxibase   |
| REBASE       | xref_rebase       |
| TCDB         | xref_tcdb         |
| UniLectin    | xref_unilectin    |

## PTM

| Label           | Returned Field       |
| --------------- | -------------------- |
| CarbonylDB      | xref_carbonyldb      |
| DEPOD           | xref_depod           |
| GlyConnect      | xref_glyconnect      |
| GlyGen          | xref_glygen          |
| iPTMnet         | xref_iptmnet         |
| MetOSite        | xref_metosite        |
| PhosphoSitePlus | xref_phosphositeplus |
| SwissPalm       | xref_swisspalm       |
| UniCarbKB       | xref_unicarbkb       |

## Genetic variation/Polymorphism and mutation

| Label   | Returned Field |
| ------- | -------------- |
| BioMuta | xref_biomuta   |
| dbSNP   | xref_dbsnp     |
| DMDM    | xref_dmdm      |

## 2D gel

| Label               | Returned Field           |
| ------------------- | ------------------------ |
| COMPLUYEAST-2DPAGE  | xref_compluyeast-2dpage  |
| DOSAC-COBS-2DPAGE   | xref_dosac-cobs-2dpage   |
| OGP                 | xref_ogp                 |
| REPRODUCTION-2DPAGE | xref_reproduction-2dpage |
| SWISS-2DPAGE        | xref_swiss-2dpage        |
| UCD-2DPAGE          | xref_ucd-2dpage          |
| World-2DPAGE        | xref_world-2dpage        |

## Proteomic

| Label             | Returned Field         |
| ----------------- | ---------------------- |
| CPTAC             | xref_cptac             |
| EPD               | xref_epd               |
| jPOST             | xref_massive           |
| MassIVE           | xref_maxqb             |
| MaxQB             | xref_pride             |
| PaxDb             | xref_paxdb             |
| PeptideAtlas      | xref_peptideatlas      |
| PRIDE             | xref_promex            |
| ProMEX            | xref_proteomicsdb      |
| ProteomicsDB      | xref_topdownproteomics |
| TopDownProteomics | xref_jpost             |

## Protocols and materials

| Label         | Returned Field     |
| ------------- | ------------------ |
| ABCD          | xref_abcd          |
| Antibodypedia | xref_antibodypedia |
| CPTC          | xref_cptc          |
| DNASU         | xref_dnasu         |

## Genome annotation

| Label           | Returned Field       |
| --------------- | -------------------- |
| Ensembl         | xref_ensembl         |
| EnsemblBacteria | xref_ensemblbacteria |
| EnsemblFungi    | xref_ensemblfungi    |
| EnsemblMetazoa  | xref_ensemblmetazoa  |
| EnsemblPlants   | xref_ensemblplants   |
| EnsemblProtists | xref_ensemblprotists |
| GeneDB          | xref_genedb          |
| GeneID          | xref_geneid          |
| Gramene         | xref_gramene         |
| KEGG            | xref_kegg            |
| PATRIC          | xref_patric          |
| UCSC            | xref_ucsc            |
| VectorBase      | xref_vectorbase      |
| WBParaSite      | xref_wbparasite      |

## Organism-specific

| Label         | Returned Field     |
| ------------- | ------------------ |
| ArachnoServer | xref_arachnoserver |
| Araport       | xref_araport       |
| CGD           | xref_cgd           |
| ConoServer    | xref_conoserver    |
| CTD           | xref_ctd           |
| dictyBase     | xref_dictybase     |
| DisGeNET      | xref_disgenet      |
| EchoBASE      | xref_echobase      |
| euHCVdb       | xref_euhcvdb       |
| FlyBase       | xref_flybase       |
| GeneCards     | xref_genecards     |
| GeneReviews   | xref_genereviews   |
| HGNC          | xref_hgnc          |
| HPA           | xref_hpa           |
| LegioList     | xref_legiolist     |
| Leproma       | xref_leproma       |
| MaizeGDB      | xref_maizegdb      |
| MalaCards     | xref_malacards     |
| MGI           | xref_mgi           |
| MIM           | xref_mim           |
| neXtProt      | xref_nextprot      |
| NIAGADS       | xref_niagads       |
| OpenTargets   | xref_opentargets   |
| Orphanet      | xref_orphanet      |
| PharmGKB      | xref_pharmgkb      |
| PHI-base      | xref_phi-base      |
| PomBase       | xref_pombase       |
| PseudoCAP     | xref_pseudocap     |
| RGD           | xref_rgd           |
| SGD           | xref_sgd           |
| TAIR          | xref_tair          |
| TubercuList   | xref_tuberculist   |
| VEuPathDB     | xref_veupathdb     |
| VGNC          | xref_vgnc          |
| WormBase      | xref_wormbase      |
| Xenbase       | xref_xenbase       |
| ZFIN          | xref_zfin          |

## Phylogenomic

| Label      | Returned Field  |
| ---------- | --------------- |
| eggNOG     | xref_eggnog     |
| GeneTree   | xref_genetree   |
| HOGENOM    | xref_hogenom    |
| InParanoid | xref_inparanoid |
| KO         | xref_ko         |
| OMA        | xref_oma        |
| OrthoDB    | xref_orthodb    |
| PhylomeDB  | xref_phylomedb  |
| TreeFam    | xref_treefam    |

## Enzyme and pathway

| Label          | Returned Field      |
| -------------- | ------------------- |
| BioCyc         | xref_biocyc         |
| BRENDA         | xref_brenda         |
| PathwayCommons | xref_pathwaycommons |
| PlantReactome  | xref_plantreactome  |
| Reactome       | xref_reactome       |
| SABIO-RK       | xref_sabio-rk       |
| SignaLink      | xref_signalink      |
| SIGNOR         | xref_signor         |
| UniPathway     | xref_unipathway     |

## Miscellaneous

| Label             | Returned Field         |
| ----------------- | ---------------------- |
| BioGRID-ORCS      | xref_biogrid-orcs      |
| ChiTaRS           | xref_chitars           |
| EvolutionaryTrace | xref_evolutionarytrace |
| GeneWiki          | xref_genewiki          |
| GenomeRNAi        | xref_genomernai        |
| Pharos            | xref_pharos            |
| PRO               | xref_pro               |
| RNAct             | xref_rnact             |

## Gene expression

| Label           | Returned Field       |
| --------------- | -------------------- |
| Bgee            | xref_bgee            |
| CollecTF        | xref_collectf        |
| ExpressionAtlas | xref_expressionatlas |
| Genevisible     | xref_genevisible     |
| CleanEx         | xref_cleanex         |

## Family and domain

| Label    | Returned Field |
| -------- | -------------- |
| CDD      | xref_cdd       |
| DisProt  | xref_disprot   |
| Gene3D   | xref_gene3d    |
| HAMAP    | xref_hamap     |
| InterPro | xref_interpro  |
| PANTHER  | xref_panther   |
| Pfam     | xref_pfam      |
| PIRSF    | xref_pirsf     |
| PRINTS   | xref_prints    |
| ProDom   | xref_prodom    |
| PROSITE  | xref_prosite   |
| SFLD     | xref_sfld      |
| SMART    | xref_smart     |
| SUPFAM   | xref_supfam    |
| TIGRFAMs | xref_tigrfams  |
