---
title: UniProtKB return fields
type: help
categories: Text_search,Technical,Website,help
---

# UniProtKB column names for programmatic access

This document lists the differences between the returned columns by RESTful APIs.
User can ask required columns returned by an API by passing the _Returned Field_ in the request url
and the response will have those requested fields.

For example, to get UniProtKB entry with accession and proteomes in new API run the below `curl` command:

```bash
curl https://rest.uniprot.org/uniprotkb/search?query=human&fields=accession,xref_proteomes
```

Equivalent request in the current website would be :

```
https://www.uniprot.org/uniprotkb?query=human&columns=id,proteome
```

The `Label` is the readable name of the returned field. The `Label` is shown on the website/TSV or in Excel format.

Previous refers to UniProt pre 2022-05.

# Names & Taxonomy

|         **Label**          | **Previous Returned Field** | **Current Returned Field** |
| :------------------------: | :-------------------------: | :------------------------: |
|           Entry            |             id              |         accession          |
|         Entry name         |         entry name          |             id             |
|         Gene names         |            genes            |         gene_names         |
|    Gene names (primary)    |      genes(PREFERRED)       |        gene_primary        |
|    Gene names (synonym)    |     genes(ALTERNATIVE)      |        gene_synonym        |
| Gene names (ordered locus) |         genes(OLN)          |          gene_oln          |
|      Gene names (ORF)      |         genes(ORF)          |          gene_orf          |
|          Organism          |          organism           |       organism_name        |
|        Organism ID         |         organism-id         |        organism_id         |
|       Protein names        |        protein names        |        protein_name        |
|         Proteomes          |          proteome           |       xref_proteomes       |
|     Taxonomic lineage      |        lineage(ALL)         |          lineage           |
|        Virus hosts         |         virus hosts         |        virus_hosts         |

_ Label in old and new API unless otherwise specified_

# Sequences

|            **Label**            |       **Previous Returned Field**        | **Current Returned Field** |
| :-----------------------------: | :--------------------------------------: | :------------------------: |
|      Alternative products       |      comment(ALTERNATIVE PRODUCTS)       |  cc_alternative_products   |
|      Alternative sequence       |      feature(ALTERNATIVE SEQUENCE)       |         ft_var_seq         |
| Erroneous gene model prediction | comment(ERRONEOUS GENE MODEL PREDICTION) |     error_gmodel_pred      |
|            Fragment             |                 fragment                 |          fragment          |
|         Gene encoded by         |                encodedon                 |         organelle          |
|             Length              |                  length                  |           length           |
|              Mass               |                   mass                   |            mass            |
|        Mass spectrometry        |        comment(MASS SPECTROMETRY)        |    cc_mass_spectrometry    |
|         Natural variant         |         feature(NATURAL VARIANT)         |         ft_variant         |
|      Non-adjacent residues      |      feature(NON ADJACENT RESIDUES)      |        ft_non_cons         |
|      Non-standard residue       |      feature(NON STANDARD RESIDUE)       |         ft_non_std         |
|      Non-terminal residue       |      feature(NON TERMINAL RESIDUE)       |         ft_non_ter         |
|          Polymorphism           |          comment(POLYMORPHISM)           |      cc_polymorphism       |
|           RNA editing           |           comment(RNA EDITING)           |       cc_rna_editing       |
|            Sequence             |                 sequence                 |          sequence          |
|        Sequence caution         |        comment(SEQUENCE CAUTION)         |    cc_sequence_caution     |
|        Sequence conflict        |        feature(SEQUENCE CONFLICT)        |        ft_conflict         |
|      Sequence uncertainty       |      feature(SEQUENCE UNCERTAINTY)       |         ft_unsure          |
|        Sequence version         |            version(sequence)             |      sequence_version      |

# Function

|       **Label**        |   **Previous Returned Field**   | **Current Returned Field** |
| :--------------------: | :-----------------------------: | :------------------------: |
|       Absorption       |       comment(ABSORPTION)       |         absorption         |
|      Active site       |      feature(ACTIVE SITE)       |        ft_act_site         |
|  Activity regulation   |  comment(ACTIVITY REGULATION)   |   cc_activity_regulation   |
|      Binding site      |      feature(BINDING SITE)      |         ft_binding         |
|    Calcium binding     |              chebi              |         ft_ca_bind         |
|   Catalytic activity   |    chebi(Catalytic activity)    |   cc_catalytic_activity    |
|        Cofactor        |         chebi(Cofactor)         |        cc_cofactor         |
|      DNA binding       |      feature(DNA BINDING)       |        ft_dna_bind         |
|       EC number        |               ec                |             ec             |
|     Function [CC]      |        comment(FUNCTION)        |        cc_function         |
|        Kinetics        |        comment(KINETICS)        |          kinetics          |
|     Metal binding      |     feature(METAL BINDING)      |          ft_metal          |
|   Nucleotide binding   |        feature(NP BIND)         |         ft_np_bind         |
|        Pathway         |        comment(PATHWAY)         |         cc_pathway         |
|     pH dependence      |     comment(PH DEPENDENCE)      |       ph_dependence        |
|    Redox potential     |    comment(REDOX POTENTIAL)     |      redox_potential       |
|        Rhea ID         |             rhea-id             |          rhea_id           |
|          Site          |          feature(SITE)          |          ft_site           |
| Temperature dependence | comment(TEMPERATURE DEPENDENCE) |      temp_dependence       |

# Miscellaneous

|     **Label**      | **Previous Returned Field** | **Current Returned Field** |
| :----------------: | :-------------------------: | :------------------------: |
|     Annotation     |      annotation score       |      annotation_score      |
|      Caution       |      comment(CAUTION)       |         cc_caution         |
|   Comment Count    |     \<does not exist\>      |       comment_count        |
|      Features      |          features           |          feature           |
|   Feature Count    |     \<does not exist\>      |      feature \_count       |
|     Keyword ID     |         keyword-id          |         keywordid          |
|      Keywords      |          keywords           |          keyword           |
|    Matched text    |           context           |     \<does not exist\>     |
| Miscellaneous [CC] |   comment(MISCELLANEOUS)    |      cc_miscellaneous      |
| Protein existence  |          existence          |     protein_existence      |
|      Reviewed      |          reviewed           |          reviewed          |
|       Tools        |            tools            |           tools            |
|      UniParc       |          uniparcid          |         uniparc_id         |

# Interaction

|       **Label**       | **Previous Returned Field** | **Current Returned Field** |
| :-------------------: | :-------------------------: | :------------------------: |
|    Interacts with     |         interactor          |       cc_interaction       |
| Subunit structure[CC] |      comment(SUBUNIT)       |         cc_subunit         |

# Expression

|      **Label**      | **Previous Returned Field**  | **Current Returned Field** |
| :-----------------: | :--------------------------: | :------------------------: |
| Developmental stage | comment(DEVELOPMENTAL STAGE) |   cc_developmental_stage   |
|      Induction      |      comment(INDUCTION)      |        cc_induction        |
| Tissue specificity  | comment(TISSUE SPECIFICITY)  |   cc_tissue_specificity    |

# Gene Ontology (GO)

|             **Label**              | **Previous Returned Field** | **Current Returned Field** |
| :--------------------------------: | :-------------------------: | :------------------------: |
| Gene ontology (biological process) |   go(biological process)    |            go_p            |
| Gene ontology (cellular component) |   go(cellular component)    |            go_c            |
|         Gene ontology (GO)         |             go              |             go             |
| Gene ontology (molecular function) |   go(molecular function)    |            go_f            |
|         Gene ontology IDs          |            go-id            |           go_id            |

# Pathology & Biotech

|       **Label**        |  **Previous Returned Field**  | **Current Returned Field** |
| :--------------------: | :---------------------------: | :------------------------: |
| Allergenic properties  |       comment(ALLERGEN)       |        cc_allergen         |
|  Biotechnological use  |    comment(BIOTECHNOLOGY)     |      cc_biotechnology      |
|  Disruption phenotype  | comment(DISRUPTION PHENOTYPE) |  cc_disruption_phenotype   |
| Involvement in disease |       comment(DISEASE)        |         cc_disease         |
|      Mutagenesis       |     feature(MUTAGENESIS)      |         ft_mutagen         |
|   Pharmaceutical use   |    comment(PHARMACEUTICAL)    |     cc_pharmaceutical      |
|       Toxic dose       |      comment(TOXIC DOSE)      |       cc_toxic_dose        |

# Subcellular location

|        **Label**         |  **Previous Returned Field**  | **Current Returned Field** |
| :----------------------: | :---------------------------: | :------------------------: |
|      Intramembrane       |    feature(INTRAMEMBRANE)     |        ft_intramem         |
| Subcellular location[CC] | comment(SUBCELLULAR LOCATION) |  cc_subcellular_location   |
|    Topological domain    |  feature(TOPOLOGICAL DOMAIN)  |        ft_topo_dom         |
|      Transmembrane       |    feature(TRANSMEMBRANE)     |        ft_transmem         |

# PTM / Processsing

|            **Label**            |  **Previous Returned Field**  | **Current Returned Field** |
| :-----------------------------: | :---------------------------: | :------------------------: |
|              Chain              |        feature(CHAIN)         |          ft_chain          |
|           Cross-link            |      feature(CROSS LINK)      |        ft_crosslnk         |
|         Disulfide bond          |    feature(DISULFIDE BOND)    |        ft_disulfid         |
|          Glycosylation          |    feature(GLYCOSYLATION)     |        ft_carbohyd         |
|      Initiator methionine       | feature(INITIATOR METHIONINE) |        ft_init_met         |
|           Lipidation            |      feature(LIPIDATION)      |          ft_lipid          |
|        Modified residue         |   feature(MODIFIED RESIDUE)   |         ft_mod_res         |
|             Peptide             |       feature(PEPTIDE)        |         ft_peptide         |
| Post-translational modification |         comment(PTM)          |           cc_ptm           |
|           Propeptide            |      feature(PROPEPTIDE)      |         ft_propep          |
|         Signal peptide          |        feature(SIGNAL)        |         ft_signal          |
|         Transit peptide         |       feature(TRANSIT)        |         ft_transit         |

# Structure

|  **Label**  | **Previous Returned Field** | **Current Returned Field** |
| :---------: | :-------------------------: | :------------------------: |
|     3D      |             3d              |        structure_3d        |
| Beta strand |    feature(BETA STRAND)     |         ft_strand          |
|    Helix    |       feature(HELIX)        |          ft_helix          |
|    Turn     |        feature(TURN)        |          ft_turn           |

# Publications

|    **Label**     | **Previous Returned Field** | **Current Returned Field** |
| :--------------: | :-------------------------: | :------------------------: |
| Mapped PubMed ID |       citationmapping       |     \<does not exist\>     |
|    PubMed ID     |          citation           |       lit_pubmed_id        |

# Date of

|             **Label**              | **Previous Returned Field** | **Current Returned Field** |
| :--------------------------------: | :-------------------------: | :------------------------: |
|          Date of creation          |           created           |        date_created        |
|     Date of last modification      |        last-modified        |       date_modified        |
| Date of last sequence modification |      sequence-modified      |   date_sequence_modified   |
|           Entry version            |       version(entry)        |          version           |

# Family & Domains

|       **Label**       | **Previous Returned Field** | **Current Returned Field** |
| :-------------------: | :-------------------------: | :------------------------: |
|      Coiled coil      |    feature(COILED COIL)     |         ft_coiled          |
|  Compositional bias   | feature(COMPOSITIONAL BIAS) |        ft_compbias         |
|      Domain[CC]       |       comment(DOMAIN)       |         cc_domain          |
|      Domain[FT]       |   feature(DOMAIN EXTENT)    |         ft_domain          |
|         Motif         |       feature(MOTIF)        |          ft_motif          |
|   Protein families    |          families           |      protein_families      |
|        Region         |       feature(REGION)       |         ft_region          |
|        Repeat         |       feature(REPEAT)       |         ft_repeat          |
| Sequence similarities |     comment(SIMILARITY)     |     \<does not exist\>     |
|      Zinc finger      |    feature(ZINC FINGER)     |         ft_zn_fing         |
