---
title: Gene Ontology (GO)
type: help
categories: Ontology,Subcellular_location,Function,manual
---

The [Gene Ontology (GO)](http://www.geneontology.org/) project provides a set of hierarchical controlled vocabulary split into 3 categories:

- Biological process
- Molecular function
- Cellular component

UniProtKB lists selected terms derived from the GO project. The GO terms derived from the 'Biological process' and Molecular function' categories are listed in the 'Function' section; the GO terms derived from the 'Cellular component' category are listed in the 'Subcellular location' section.

GO terms can be manually or electronically assigned to a UniProtKB entry:

- Manually assigned GO terms found in UniProtKB/Swiss-Prot are associated with one of 15 [GO evidence codes](http://www.geneontology.org/GO.evidence.shtml?all), as well as with a link to the relevant publication, when available. These GO annotations are tagged with a yellow source/evidence label.

- Electronically assigned GO terms are found in UniProtKB/TrEMBL, but to some extent also in UniProtKB/Swiss-Prot, and are associated with the GO evidence code 'IEA', which means 'inferred from electronic annotation'. These GO annotations are tagged with a blue source/evidence label.

Note that many UniProtKB keywords are manually mapped to GO terms (see document ' [Controlled vocabulary of keywords](https://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/docs/keywlist.txt) '), but the resulting GO annotations in UniProtKB appear with a blue label as "inferred from electronic annotation".

# List of GO evidence codes found in UniProtKB

- EXP: Inferred from Experiment  
  Used when experimental results indicate a gene product's function, process involvement or subcellular location.

- IBA: Inferred from Biological Aspect of Ancestor  
  Used when an aspect of a descendent is inferred through the characterization of an aspect of a ancestral gene.

- IC: Inferred by Curator  
  Used when annotation is not supported by any evidence, but can be reasonably inferred by a curator from other GO annotations for which evidence is available.

- IDA: Inferred from Direct Assay  
  Used when a direct assay for the function, process or component indicated by the GO term is available.

- HDA: High-throughput Direct Assay

- IEA: Inferred from Electronic Annotation  
  Used when annotation derives from computation or automated transfer from a database. These annotations have not been manually checked.

- IEP: Inferred from Expression Pattern  
  Used when annotation is inferred from the timing or site of expression of a gene.

- HEP: High-throughput Expression Pattern

- IGC: Inferred from Genomic Context  
  Used when information about the genomic context of a gene product forms part of the evidence for a particular annotation. Genomic context includes, but is not limited to, such things as identity of neighboring genes (i.e. synteny), operon structure, and phylogenetic or other whole genome analysis.

- IGI: Inferred from Genetic Interaction  
  Used to describe "traditional" genetic interactions, such as suppressors and synthetic lethals, as well as other techniques, such as functional complementation, rescue experiments, or inferences about a gene drawn from the phenotype of a mutation in a different gene.

- HGI: High-throughput Genetic Interaction

- IMP: Inferred from Mutant Phenotype  
  Used to describe the observations of variations or changes in a gene product, such as mutations or abnormal levels. This includes techniques, such as knockouts, overexpression, anti-sense experiments and use of specific protein inhibitors.

- HMP: High-throughput Mutant Phenotype

- IPI: Inferred from Physical Interaction  
  Used to cover physical interactions between the gene product of interest and another molecule (ion, complex, etc.).

- ISA: Inferred from Sequence Alignment  
  Used when the primary piece of evidence is a pairwise or multiple sequence alignment.

- ISM: Inferred from Sequence Model  
  Used when any kind of sequence modeling method (e.g. Hidden Markov Models) is the primary piece of evidence

- ISO: Inferred from Sequence Orthology  
  Used when the assertion of orthology between the gene product and an experimentally characterized gene product in another organism is the main basis of the annotation

- ISS: Inferred from Sequence or Structural Similarity  
  Used for any analysis based on sequence alignment, structure comparison, or evaluation of sequence features, such as composition.

- NAS: Non-traceable Author Statement  
  Used for statements found in a published article that cannot be traced back to another publication.

- TAS: Traceable Author Statement  
  Used for information obtained from published articles, mostly reviews, as well as text books or dictionaries, where the original experiments are traceable.

Additional information:

- [GO evidence codes](http://www.geneontology.org/GO.evidence.shtml?all)
- [Evidences](https://www.uniprot.org/help/evidences)

# Related documents

[Controlled vocabulary of keywords](https://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/docs/keywlist.txt)

[What are the differences between UniProtKB keywords and the GO terms?](https://www.uniprot.org/help/keywords_vs_go)

[What is the difference between the GO annotation included in UniProtKB's 'Ontologies' section, and the information accessible via the link 'Complete GO annotation'?](https://www.uniprot.org/help/complete_go_annotation)
