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

| Label  | Returned Field | Has full version |
| ------ | -------------- | ---------------- |
| CCDS   | xref_ccds      | no               |
| EMBL   | xref_embl      | yes              |
| PIR    | xref_pir       | yes              |
| RefSeq | xref_refseq    | yes              |

## 3D structure

| Label  | Returned Field | Has full version |
| ------ | -------------- | ---------------- |
| BMRB   | xref_bmrb      | no               |
| EMDB   | xref_emdb      | no               |
| PCDDB  | xref_pcddb     | no               |
| PDB    | xref_pdb       | yes              |
| PDBsum | xref_pdbsum    | no               |
| SASBDB | xref_sasbdb    | no               |
| SMR    | xref_smr       | no               |

## Protein-protein interaction

| Label         | Returned Field     | Has full version |
| ------------- | ------------------ | ---------------- |
| BioGRID       | xref_biogrid       | yes              |
| ComplexPortal | xref_corum         | no               |
| CORUM         | xref_complexportal | yes              |
| DIP           | xref_dip           | no               |
| ELM           | xref_elm           | no               |
| IntAct        | xref_intact        | yes              |
| MINT          | xref_mint          | no               |
| STRING        | xref_string        | no               |

## Chemistry

| Label               | Returned Field           | Has full version |
| ------------------- | ------------------------ | ---------------- |
| BindingDB           | xref_bindingdb           | no               |
| ChEMBL              | xref_chembl              | no               |
| DrugBank            | xref_drugbank            | yes              |
| DrugCentral         | xref_drugcentral         | no               |
| GuidetoPHARMACOLOGY | xref_guidetopharmacology | no               |
| SwissLipids         | xref_swisslipids         | no               |

## Protein family/group

| Label        | Returned Field    | Has full version |
| ------------ | ----------------- | ---------------- |
| Allergome    | xref_allergome    | yes              |
| CAZy         | xref_cazy         | yes              |
| CLAE         | xref_clae         | no               |
| ESTHER       | xref_esther       | yes              |
| IDEAL        | xref_ideal        | no               |
| IMGT_GENE-DB | xref_imgt_gene-db | no               |
| MEROPS       | xref_merops       | no               |
| MoonDB       | xref_moondb       | yes              |
| MoonProt     | xref_moonprot     | no               |
| PeroxiBase   | xref_peroxibase   | yes              |
| REBASE       | xref_rebase       | yes              |
| TCDB         | xref_tcdb         | yes              |
| UniLectin    | xref_unilectin    | no               |

## PTM

| Label           | Returned Field       | Has full version |
| --------------- | -------------------- | ---------------- |
| CarbonylDB      | xref_carbonyldb      | no               |
| DEPOD           | xref_depod           | no               |
| GlyConnect      | xref_glyconnect      | yes              |
| GlyGen          | xref_glygen          | yes              |
| iPTMnet         | xref_iptmnet         | no               |
| MetOSite        | xref_metosite        | no               |
| PhosphoSitePlus | xref_phosphositeplus | no               |
| SwissPalm       | xref_swisspalm       | no               |
| UniCarbKB       | xref_unicarbkb       | no               |

## Genetic variation/Polymorphism and mutation

| Label   | Returned Field | Has full version |
| ------- | -------------- | ---------------- |
| BioMuta | xref_biomuta   | no               |
| dbSNP   | xref_dbsnp     | no               |
| DMDM    | xref_dmdm      | no               |

## 2D gel

| Label               | Returned Field           | Has full version |
| ------------------- | ------------------------ | ---------------- |
| COMPLUYEAST-2DPAGE  | xref_compluyeast-2dpage  | no               |
| DOSAC-COBS-2DPAGE   | xref_dosac-cobs-2dpage   | no               |
| OGP                 | xref_ogp                 | no               |
| REPRODUCTION-2DPAGE | xref_reproduction-2dpage | no               |
| SWISS-2DPAGE        | xref_swiss-2dpage        | no               |
| UCD-2DPAGE          | xref_ucd-2dpage          | no               |
| World-2DPAGE        | xref_world-2dpage        | no               |

## Proteomic

| Label             | Returned Field         | Has full version |
| ----------------- | ---------------------- | ---------------- |
| CPTAC             | xref_cptac             | no               |
| EPD               | xref_epd               | no               |
| jPOST             | xref_massive           | no               |
| MassIVE           | xref_maxqb             | no               |
| MaxQB             | xref_pride             | no               |
| PaxDb             | xref_paxdb             | no               |
| PeptideAtlas      | xref_peptideatlas      | no               |
| PRIDE             | xref_promex            | no               |
| ProMEX            | xref_proteomicsdb      | no               |
| ProteomicsDB      | xref_topdownproteomics | no               |
| TopDownProteomics | xref_jpost             | no               |

## Protocols and materials

| Label         | Returned Field     | Has full version |
| ------------- | ------------------ | ---------------- |
| ABCD          | xref_abcd          | yes              |
| Antibodypedia | xref_antibodypedia | yes              |
| CPTC          | xref_cptc          | yes              |
| DNASU         | xref_dnasu         | no               |

## Genome annotation

| Label           | Returned Field       | Has full version |
| --------------- | -------------------- | ---------------- |
| Ensembl         | xref_ensembl         | yes              |
| EnsemblBacteria | xref_ensemblbacteria | yes              |
| EnsemblFungi    | xref_ensemblfungi    | yes              |
| EnsemblMetazoa  | xref_ensemblmetazoa  | yes              |
| EnsemblPlants   | xref_ensemblplants   | yes              |
| EnsemblProtists | xref_ensemblprotists | yes              |
| GeneDB          | xref_genedb          | no               |
| GeneID          | xref_geneid          | no               |
| Gramene         | xref_gramene         | yes              |
| KEGG            | xref_kegg            | no               |
| PATRIC          | xref_patric          | yes              |
| UCSC            | xref_ucsc            | yes              |
| VectorBase      | xref_vectorbase      | yes              |
| WBParaSite      | xref_wbparasite      | yes              |

## Organism-specific

| Label         | Returned Field     | Has full version |
| ------------- | ------------------ | ---------------- |
| ArachnoServer | xref_arachnoserver | yes              |
| Araport       | xref_araport       | no               |
| CGD           | xref_cgd           | yes              |
| ConoServer    | xref_conoserver    | yes              |
| CTD           | xref_ctd           | no               |
| dictyBase     | xref_dictybase     | yes              |
| DisGeNET      | xref_disgenet      | no               |
| EchoBASE      | xref_echobase      | no               |
| euHCVdb       | xref_euhcvdb       | no               |
| FlyBase       | xref_flybase       | yes              |
| GeneCards     | xref_genecards     | no               |
| GeneReviews   | xref_genereviews   | no               |
| HGNC          | xref_hgnc          | yes              |
| HPA           | xref_hpa           | yes              |
| JaponicusDB   | xref_japonicus_db  | yes              |
| LegioList     | xref_legiolist     | no               |
| Leproma       | xref_leproma       | no               |
| MaizeGDB      | xref_maizegdb      | no               |
| MalaCards     | xref_malacards     | no               |
| MGI           | xref_mgi           | yes              |
| MIM           | xref_mim           | yes              |
| neXtProt      | xref_nextprot      | no               |
| NIAGADS       | xref_niagads       | no               |
| OpenTargets   | xref_opentargets   | no               |
| Orphanet      | xref_orphanet      | yes              |
| PharmGKB      | xref_pharmgkb      | no               |
| PHI-base      | xref_phi-base      | no               |
| PomBase       | xref_pombase       | no               |
| PseudoCAP     | xref_pseudocap     | no               |
| RGD           | xref_rgd           | yes              |
| SGD           | xref_sgd           | yes              |
| TAIR          | xref_tair          | yes              |
| TubercuList   | xref_tuberculist   | no               |
| VEuPathDB     | xref_veupathdb     | no               |
| VGNC          | xref_vgnc          | yes              |
| WormBase      | xref_wormbase      | yes              |
| Xenbase       | xref_xenbase       | yes              |
| ZFIN          | xref_zfin          | yes              |

## Phylogenomic

| Label      | Returned Field  | Has full version |
| ---------- | --------------- | ---------------- |
| eggNOG     | xref_eggnog     | yes              |
| GeneTree   | xref_genetree   | no               |
| HOGENOM    | xref_hogenom    | no               |
| InParanoid | xref_inparanoid | no               |
| KO         | xref_ko         | no               |
| OMA        | xref_oma        | yes              |
| OrthoDB    | xref_orthodb    | no               |
| PhylomeDB  | xref_phylomedb  | no               |
| TreeFam    | xref_treefam    | no               |

## Enzyme and pathway

| Label          | Returned Field      | Has full version |
| -------------- | ------------------- | ---------------- |
| BioCyc         | xref_biocyc         | no               |
| BRENDA         | xref_brenda         | yes              |
| PathwayCommons | xref_pathwaycommons | no               |
| PlantReactome  | xref_plantreactome  | yes              |
| Reactome       | xref_reactome       | no               |
| SABIO-RK       | xref_sabio-rk       | no               |
| SignaLink      | xref_signalink      | no               |
| SIGNOR         | xref_signor         | no               |
| UniPathway     | xref_unipathway     | yes              |

## Miscellaneous

| Label             | Returned Field         | Has full version |
| ----------------- | ---------------------- | ---------------- |
| BioGRID-ORCS      | xref_biogrid-orcs      | yes              |
| ChiTaRS           | xref_chitars           | yes              |
| EvolutionaryTrace | xref_evolutionarytrace | no               |
| GeneWiki          | xref_genewiki          | no               |
| GenomeRNAi        | xref_genomernai        | no               |
| Pharos            | xref_pharos            | no               |
| PRO               | xref_pro               | no               |
| RNAct             | xref_rnact             | yes              |

## Gene expression

| Label           | Returned Field       | Has full version |
| --------------- | -------------------- | ---------------- |
| Bgee            | xref_bgee            | yes              |
| CollecTF        | xref_collectf        | no               |
| ExpressionAtlas | xref_expressionatlas | yes              |
| Genevisible     | xref_genevisible     | yes              |
| CleanEx         | xref_cleanex         | no               |

## Family and domain

| Label    | Returned Field | Has full version |
| -------- | -------------- | ---------------- |
| CDD      | xref_cdd       | yes              |
| DisProt  | xref_disprot   | no               |
| Gene3D   | xref_gene3d    | yes              |
| HAMAP    | xref_hamap     | yes              |
| InterPro | xref_interpro  | yes              |
| NCBIfam  | xref_ncbifam   | yes              |
| PANTHER  | xref_panther   | yes              |
| Pfam     | xref_pfam      | yes              |
| PIRSF    | xref_pirsf     | yes              |
| PRINTS   | xref_prints    | yes              |
| PROSITE  | xref_prosite   | yes              |
| SFLD     | xref_sfld      | yes              |
| SMART    | xref_smart     | yes              |
| SUPFAM   | xref_supfam    | yes              |

# Full version

The format of our existing [UniProtKB return fields for cross-references](https://www.uniprot.org/help/return_fields_databases) in a result table consists of the primary identifier of the external resource and, optionally, the [UniProt isoform identifier in square brackets](https://www.uniprot.org/help/isoform_crossreferences). When an entry has several cross-references to the same external resources, these cross-references are separated by a semi-colon.

Since [release 2023_05](https://www.uniprot.org/release-notes/2023-11-08-release), a new variant to these return fields has been added for all cross-references that have additional identifiers or other information. The format of an individual cross-reference is identical to the format used in the UniProtKB text format (with multiple fields being separated by semi-colons). In order to continue to separate multiple cross-references to the same external resource with a semi-colon, each individual cross-reference is enclosed in double quotes.

Example: [A0JNW5 Ensembl cross-references](https://rest.uniprot.org/uniprotkb/A0JNW5.tsv?fields=xref_ensembl)

Existing return field `xref_ensembl`:

```
ENST00000279907.12 [A0JNW5-1];ENST00000356828.7 [A0JNW5-2];
```

New return field `xref_ensembl_full`:

```
"ENST00000279907.12; ENSP00000279907.7; ENSG00000111647.13. [A0JNW5-1]";"ENST00000356828.7; ENSP00000349285.3; ENSG00000111647.13. [A0JNW5-2]";
```

Example: [A0JNW5 InterPro cross-references](https://rest.uniprot.org/uniprotkb/A0JNW5.tsv?fields=xref_interpro)

Existing return field `xref_interpro`:

```
IPR026728;IPR026854;
```

New return field `xref_interpro_full`:

```
"IPR026728; BLTP3A/B.";"IPR026854; VPS13-like_N."
```

