
---
title: Natural variant
categories: Sequence,manual
---

This subsection of the 'Sequence' section describes natural variant(s) of the protein sequence.

We annotate natural variants, including polymorphisms, variations between strains, isolates or cultivars, disease-associated mutations and RNA editing events. We report the nature of the amino acid change, the name of the variant (or allele), when available, and the effect(s) of the variation on the protein, the cell or the complete organism.

Note that mutations that induce major changes in the protein sequence, such as frameshifts or premature stops, are not annotated: their deleterious effects on protein function are often obvious. While these mutations cannot be described in this subsection, the phenotype, if known, will be reported in the '[Polymorphism](http://www.uniprot.org/manual/polymorphism)' or '[Involvement in disease](http://www.uniprot.org/manual/involvement_in_disease)' subsections.

### 1\. Polymorphisms

The sequence displayed by default in the entry (also called the canonical sequence) is usually the most common polymorphic variant or the most conserved in orthologous species. All polymorphisms are described with regard to this canonical sequence.

Most naturally occurring polymorphisms (also called single amino acid polymorphisms or SAPs) are due to a single nucleotide change (SNP) at the codon level. When a polymorphism results from more than one nucleotide change, it is indicated in the 'Description' field.  
  
Example: [Q96CV9](http://www.uniprot.org/uniprot/Q96CV9#sequences)

Validated human polymorphisms from the NCBI [dbSNP](http://www.uniprot.org/www.ncbi.nlm.nih.gov/projects/SNP/) database are annotated and tagged with the dbSNP identifier in the 'Description' field.  
  
Example: [P15516](http://www.uniprot.org/uniprot/P15516#sequences)

Additional information, such as the cell type or tissue of origin of the variant, the distribution or the frequency of the allele in a given population, is indicated in the 'Description' field, when available.  
  
Examples: [P30154](http://www.uniprot.org/uniprot/P30154#sequences), [O14896](http://www.uniprot.org/uniprot/O14896#sequences)  
  
When several natural variants exist for a single position, they are annotated in distinct 'Natural variant' subsections.  
  
Example: [Q8NET6](http://www.uniprot.org/uniprot/Q8NET6#sequences)

Additional information concerning individual polymorphisms can be reported in the ['Polymorphism'](http://www.uniprot.org/manual/polymorphism) subsection.  
  
Example: [P15516](http://www.uniprot.org/uniprot/P15516#sequences)

Note that polymorphisms are by definition naturally occurring variants. Mutations resulting from (large-scale) mutagenesis screens of genetically tractable organisms, such as yeast or fly, are not considered as natural variants and are described in the ['Mutagenesis'](http://www.uniprot.org/manual/mutagen) subsection of the 'Pathology and Biotech' section.

Related keyword: [Polymorphism](http://www.uniprot.org/keywords/621)

### 2\. Disease-associated mutations

Information on disease-associated mutations is mostly restricted to human proteins and is usually found in the 'Pathology and Biotech' section. We describe the amino acid change, the abbreviation of the associated disease and the effect(s) of the variation on the protein, the cell and/or the organism, if known. Additional information about the disease itself is provided in the ['Involvement in disease'](http://www.uniprot.org/manual/involvement_in_disease) subsection of the 'Pathology and Biotech' section.  
  
Examples: [O43593](http://www.uniprot.org/uniprot/O43593#pathology_and_biotech), [P26439](http://www.uniprot.org/uniprot/P26439#pathology_and_biotech)

Validated human disease-associated polymorphisms from the NCBI [dbSNP](http://www.uniprot.org/www.ncbi.nlm.nih.gov/projects/SNP/) database are annotated and tagged with the dbSNP identifier in the 'Description' field. These SAPs are relatively rare as many disease-associated mutations have too low frequencies to be reported in [dbSNP](http://www.ncbi.nlm.nih.gov/projects/SNP/).  
  
Example: [O43593](http://www.uniprot.org/uniprot/O43593#sequences)

Remark:  
  
Nucleotide insertion/deletion are not described in detail in UniProtKB/Swiss-Prot as they usually produce a non functional protein. Additional information can be found by following links to the OMIM database.  
  
Example: [P51681](http://www.uniprot.org/uniprot/P51681#pathology_and_biotech) and allele 'delta32 deletion' ( [OMIM](http://www.ncbi.nlm.nih.gov/entrez/dispomim.cgi?id=601373&a=601373_AllelicVariant0001) )

Related keyword: [Disease mutation](http://www.uniprot.org/keywords/225)

### 3\. RNA editing

RNA editing events include conversion, insertion and deletion of nucleotides. We annotate only those RNA editing events that change the protein sequence. Silent events are not annotated. For partial RNA editing events, we show the translation of the underlying genomic DNA sequence and indicate the potential amino acid change due to RNA editing in the 'Natural variant' subsection.  
  
Example: [P28335](http://www.uniprot.org/uniprot/P28335#sequences)

Additional information on RNA editing events can be found in the ['RNA editing'](http://www.uniprot.org/manual/rna_editing) subsection.

Related keyword: [RNA editing](http://www.uniprot.org/keywords/691)

### 4\. Variations between strains, isolates or cultivars

Variations between strains, isolates or cultivars (cv) are described and the strain/isolate/cultivar exhibiting the variation is indicated in the 'Description' field.  
  
Examples: [Q8MMF9](http://www.uniprot.org/uniprot/Q8MMF9#sequences), [Q9QNF7](http://www.uniprot.org/uniprot/Q9QNF7#sequences), [Q8W4J9](http://www.uniprot.org/uniprot/Q8W4J9#sequences)

#### Related documents

[List of human entries with polymorphisms or mutations](http://www.uniprot.org/docs/humpvar)  
  
[Index of human polymorphisms and disease mutations](http://www.uniprot.org/docs/humsavar)  
  
[Controlled vocabulary of strains](http://www.uniprot.org/docs/strains)  
  
[Amino acid altering variants imported from Ensembl Variation databases, tab-delimited download](ftp://ftp.uniprot.org/pub/databases/uniprot/current%5Frelease/knowledgebase/variants/)
        