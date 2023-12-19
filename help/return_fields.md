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

| Label                      | Returned Field |
| -------------------------- | -------------- |
| Entry                      | accession      |
| Entry Name                 | id             |
| Gene Names                 | gene_names     |
| Gene Names (primary)       | gene_primary   |
| Gene Names (synonym)       | gene_synonym   |
| Gene Names (ordered locus) | gene_oln       |
| Gene Names (ORF)           | gene_orf       |
| Organism                   | organism_name  |
| Organism ID                | organism_id    |
| Protein names              | protein_name   |
| Proteomes                  | xref_proteomes |
| Taxonomic lineage          | lineage        |
| Taxonomic lineage (IDs)    | lineage_ids    |
| Virus hosts                | virus_hosts    |

# Sequences

| Label                           | Returned Field          |
| ------------------------------- | ----------------------- |
| Alternative products            | cc_alternative_products |
| Alternative sequence            | ft_var_seq              |
| Erroneous gene model prediction | error_gmodel_pred       |
| Fragment                        | fragment                |
| Gene encoded by                 | organelle               |
| Length                          | length                  |
| Mass                            | mass                    |
| Mass spectrometry               | cc_mass_spectrometry    |
| Natural variant                 | ft_variant              |
| Non-adjacent residues           | ft_non_cons             |
| Non-standard residue            | ft_non_std              |
| Non-terminal residue            | ft_non_ter              |
| Polymorphism                    | cc_polymorphism         |
| RNA editing                     | cc_rna_editing          |
| Sequence                        | sequence                |
| Sequence caution                | cc_sequence_caution     |
| Sequence conflict               | ft_conflict             |
| Sequence uncertainty            | ft_unsure               |
| Sequence version                | sequence_version        |

# Function

| Label                  | Returned Field         |
| ---------------------- | ---------------------- |
| Absorption             | absorption             |
| Active site            | ft_act_site            |
| Activity regulation    | cc_activity_regulation |
| Binding site           | ft_binding             |
| Catalytic activity     | cc_catalytic_activity  |
| Cofactor               | cc_cofactor            |
| DNA binding            | ft_dna_bind            |
| EC number              | ec                     |
| Function [CC]          | cc_function            |
| Kinetics               | kinetics               |
| Pathway                | cc_pathway             |
| pH dependence          | ph_dependence          |
| Redox potential        | redox_potential        |
| Rhea ID                | rhea                   |
| Site                   | ft_site                |
| Temperature dependence | temp_dependence        |

# Miscellaneous

| Label              | Returned Field    |
| ------------------ | ----------------- |
| Annotation         | annotation_score  |
| Caution            | cc_caution        |
| Comment Count      | comment_count     |
| Features           | feature_count     |
| Keyword ID         | keywordid         |
| Keywords           | keyword           |
| Miscellaneous [CC] | cc_miscellaneous  |
| Protein existence  | protein_existence |
| Reviewed           | reviewed          |
| Tools              | tools             |
| UniParc            | uniparc_id        |

# Interaction

| Label                  | Returned Field |
| ---------------------- | -------------- |
| Interacts with         | cc_interaction |
| Subunit structure [CC] | cc_subunit     |

# Expression

| Label               | Returned Field         |
| ------------------- | ---------------------- |
| Developmental stage | cc_developmental_stage |
| Induction           | cc_induction           |
| Tissue specificity  | cc_tissue_specificity  |

# Gene Ontology (GO)

| Label                              | Returned Field |
| ---------------------------------- | -------------- |
| Gene Ontology (biological process) | go_p           |
| Gene Ontology (cellular component) | go_c           |
| Gene Ontology (GO)                 | go             |
| Gene Ontology (molecular function) | go_f           |
| Gene Ontology IDs                  | go_id          |

# Pathology & Biotech

| Label                  | Returned Field          |
| ---------------------- | ----------------------- |
| Allergenic properties  | cc_allergen             |
| Biotechnological use   | cc_biotechnology        |
| Disruption phenotype   | cc_disruption_phenotype |
| Involvement in disease | cc_disease              |
| Mutagenesis            | ft_mutagen              |
| Pharmaceutical use     | cc_pharmaceutical       |
| Toxic dose             | cc_toxic_dose           |

# Subcellular location

| Label                     | Returned Field          |
| ------------------------- | ----------------------- |
| Intramembrane             | ft_intramem             |
| Subcellular location [CC] | cc_subcellular_location |
| Topological domain        | ft_topo_dom             |
| Transmembrane             | ft_transmem             |

# PTM / Processsing

| Label                           | Returned Field |
| ------------------------------- | -------------- |
| Chain                           | ft_chain       |
| Cross-link                      | ft_crosslnk    |
| Disulfide bond                  | ft_disulfid    |
| Glycosylation                   | ft_carbohyd    |
| Initiator methionine            | ft_init_met    |
| Lipidation                      | ft_lipid       |
| Modified residue                | ft_mod_res     |
| Peptide                         | ft_peptide     |
| Post-translational modification | cc_ptm         |
| Propeptide                      | ft_propep      |
| Signal peptide                  | ft_signal      |
| Transit peptide                 | ft_transit     |

# Structure

| Label       | Returned Field |
| ----------- | -------------- |
| 3D          | structure_3d   |
| Beta strand | ft_strand      |
| Helix       | ft_helix       |
| Turn        | ft_turn        |

# Publications

| Label     | Returned Field |
| --------- | -------------- |
| PubMed ID | lit_pubmed_id  |

# Date of

| Label Returned Field               |
| ---------------------------------- | ---------------------- |
| Date of creation                   | date_created           |
| Date of last modification          | date_modified          |
| Date of last sequence modification | date_sequence_modified |
| Entry version                      | version                |

# Family & Domains

| Label              | Returned Field   |
| ------------------ | ---------------- |
| Coiled coil        | ft_coiled        |
| Compositional bias | ft_compbias      |
| Domain[CC]         | cc_domain        |
| Domain[FT]         | ft_domain        |
| Motif              | ft_motif         |
| Protein families   | protein_families |
| Region             | ft_region        |
| Repeat             | ft_repeat        |
| Zinc finger        | ft_zn_fing       |

# Sequence Databases

| Label  | Returned Field |
| ------ | -------------- |
| CCDS   | xref_ccds      |
| EMBL   | xref_embl      |
| PIR    | xref_pir       |
| RefSeq | xref_refseq    |

# 3D Structure Databases

| Label       | Returned Field   |
| ----------- | ---------------- |
| AlphaFoldDB | xref_alphafolddb |
| BMRB        | xref_bmrb        |
| PCDDB       | xref_pcddb       |
| PDB         | xref_pdb         |
| PDBsum      | xref_pdbsum      |
| SASBDB      | xref_sasbdb      |
| SMR         | xref_smr         |

# Protein-Protein Interaction Databases

| Label         | Returned Field     |
| ------------- | ------------------ |
| BioGRID       | xref_biogrid       |
| CORUM         | xref_corum         |
| ComplexPortal | xref_complexportal |
| DIP           | xref_dip           |
| ELM           | xref_elm           |
| IntAct        | xref_intact        |
| MINT          | xref_mint          |
| STRING        | xref_string        |

# Chemistry Databases

| Label               | Returned Field           |
| ------------------- | ------------------------ |
| BindingDB           | xref_bindingdb           |
| ChEMBL              | xref_chembl              |
| DrugBank            | xref_drugbank            |
| DrugCentral         | xref_drugcentral         |
| GuidetoPHARMACOLOGY | xref_guidetopharmacology |
| SwissLipids         | xref_swisslipids         |

# Protein Family/Group Databases

| Label        | Returned Field    |
| ------------ | ----------------- |
| Allergome    | xref_allergome    |
| CAZy         | xref_cazy         |
| CLAE         | xref_clae         |
| ESTHER       | xref_esther       |
| IMGT_GENE-DB | xref_imgt_gene-db |
| MEROPS       | xref_merops       |
| MoonDB       | xref_moondb       |
| MoonProt     | xref_moonprot     |
| PeroxiBase   | xref_peroxibase   |
| REBASE       | xref_rebase       |
| TCDB         | xref_tcdb         |
| UniLectin    | xref_unilectin    |

# PTM Databases

| Label           | Returned Field       |
| --------------- | -------------------- |
| CarbonylDB      | xref_carbonyldb      |
| DEPOD           | xref_depod           |
| GlyCosmos       | xref_glycosmos       |
| GlyConnect      | xref_glyconnect      |
| GlyGen          | xref_glygen          |
| MetOSite        | xref_metosite        |
| PhosphoSitePlus | xref_phosphositeplus |
| SwissPalm       | xref_swisspalm       |
| iPTMnet         | xref_iptmnet         |

# Genetic Variation Databases

| Label   | Returned Field |
| ------- | -------------- |
| BioMuta | xref_biomuta   |
| DMDM    | xref_dmdm      |
| dbSNP   | xref_dbsnp     |

# 2D Gel Databases

| Label               | Returned Field           |
| ------------------- | ------------------------ |
| COMPLUYEAST-2DPAGE  | xref_compluyeast-2dpage  |
| DOSAC-COBS-2DPAGE   | xref_dosac-cobs-2dpage   |
| OGP                 | xref_ogp                 |
| REPRODUCTION-2DPAGE | xref_reproduction-2dpage |
| SWISS-2DPAGE        | xref_swiss-2dpage        |
| UCD-2DPAGE          | xref_ucd-2dpage          |
| World-2DPAGE        | xref_world-2dpage        |

# Proteomic Databases

| Label             | Returned Field         |
| ----------------- | ---------------------- |
| CPTAC             | xref_cptac             |
| EPD               | xref_epd               |
| MassIVE           | xref_massive           |
| MaxQB             | xref_maxqb             |
| PRIDE             | xref_pride             |
| PaxDb             | xref_paxdb             |
| PeptideAtlas      | xref_peptideatlas      |
| ProMEX            | xref_promex            |
| ProteomicsDB      | xref_proteomicsdb      |
| TopDownProteomics | xref_topdownproteomics |
| jPOST             | xref_jpost             |

# Protocols And Materials Databases

| Label         | Returned Field     |
| ------------- | ------------------ |
| ABCD          | xref_abcd          |
| Antibodypedia | xref_antibodypedia |
| CPTC          | xref_cptc          |
| DNASU         | xref_dnasu         |

# Genome Annotation Databases

| Label                       | Returned Field                   |
| --------------------------- | -------------------------------- |
| Ensembl                     | xref_ensembl                     |
| EnsemblBacteria             | xref_ensemblbacteria             |
| EnsemblFungi                | xref_ensemblfungi                |
| EnsemblMetazoa              | xref_ensemblmetazoa              |
| EnsemblPlants               | xref_ensemblplants               |
| EnsemblProtists             | xref_ensemblprotists             |
| GeneID                      | xref_geneid                      |
| Gramene                     | xref_gramene                     |
| KEGG                        | xref_kegg                        |
| MANE-Select                 | xref_mane-select                 |
| PATRIC                      | xref_patric                      |
| UCSC                        | xref_ucsc                        |
| VectorBase                  | xref_vectorbase                  |
| WBParaSite                  | xref_wbparasite                  |
| WBParaSiteTranscriptProtein | xref_wbparasitetranscriptprotein |

# Organism-Specific Databases

| Label         | Returned Field     |
| ------------- | ------------------ |
| AGR           | xref_agr           |
| ArachnoServer | xref_arachnoserver |
| Araport       | xref_araport       |
| CGD           | xref_cgd           |
| CTD           | xref_ctd           |
| ConoServer    | xref_conoserver    |
| DisGeNET      | xref_disgenet      |
| EchoBASE      | xref_echobase      |
| FlyBase       | xref_flybase       |
| GeneCards     | xref_genecards     |
| GeneReviews   | xref_genereviews   |
| HGNC          | xref_hgnc          |
| HPA           | xref_hpa           |
| LegioList     | xref_legiolist     |
| Leproma       | xref_leproma       |
| MGI           | xref_mgi           |
| MIM           | xref_mim           |
| MaizeGDB      | xref_maizegdb      |
| MalaCards     | xref_malacards     |
| NIAGADS       | xref_niagads       |
| OpenTargets   | xref_opentargets   |
| Orphanet      | xref_orphanet      |
| PharmGKB      | xref_pharmgkb      |
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
| dictyBase     | xref_dictybase     |
| euHCVdb       | xref_euhcvdb       |
| neXtProt      | xref_nextprot      |

# Phylogenomic Databases

| Label      | Returned Field  |
| ---------- | --------------- |
| GeneTree   | xref_genetree   |
| HOGENOM    | xref_hogenom    |
| InParanoid | xref_inparanoid |
| KO         | xref_ko         |
| OMA        | xref_oma        |
| OrthoDB    | xref_orthodb    |
| PhylomeDB  | xref_phylomedb  |
| TreeFam    | xref_treefam    |
| eggNOG     | xref_eggnog     |

# Enzyme And Pathway Databases

| Label          | Returned Field      |
| -------------- | ------------------- |
| BRENDA         | xref_brenda         |
| BioCyc         | xref_biocyc         |
| PathwayCommons | xref_pathwaycommons |
| PlantReactome  | xref_plantreactome  |
| Reactome       | xref_reactome       |
| SABIO-RK       | xref_sabio-rk       |
| SIGNOR         | xref_signor         |
| SignaLink      | xref_signalink      |
| UniPathway     | xref_unipathway     |

# Miscellaneous Databases

| Label             | Returned Field         |
| ----------------- | ---------------------- |
| BioGRID-ORCS      | xref_biogrid-orcs      |
| ChiTaRS           | xref_chitars           |
| EvolutionaryTrace | xref_evolutionarytrace |
| GeneWiki          | xref_genewiki          |
| GenomeRNAi        | xref_genomernai        |
| PHI-base          | xref_phi-base          |
| PRO               | xref_pro               |
| Pharos            | xref_pharos            |
| RNAct             | xref_rnact             |

# Gene Expression Databases

| Label           | Returned Field       |
| --------------- | -------------------- |
| Bgee            | xref_bgee            |
| CleanEx         | xref_cleanex         |
| CollecTF        | xref_collectf        |
| ExpressionAtlas | xref_expressionatlas |
| Genevisible     | xref_genevisible     |

# Family And Domain Databases

| Label    | Returned Field |
| -------- | -------------- |
| CDD      | xref_cdd       |
| DisProt  | xref_disprot   |
| Gene3D   | xref_gene3d    |
| HAMAP    | xref_hamap     |
| IDEAL    | xref_ideal     |
| InterPro | xref_interpro  |
| PANTHER  | xref_panther   |
| PIRSF    | xref_pirsf     |
| PRINTS   | xref_prints    |
| PROSITE  | xref_prosite   |
| Pfam     | xref_pfam      |
| ProDom   | xref_prodom    |
| SFLD     | xref_sfld      |
| SMART    | xref_smart     |
| SUPFAM   | xref_supfam    |
| TIGRFAMs | xref_tigrfams  |
