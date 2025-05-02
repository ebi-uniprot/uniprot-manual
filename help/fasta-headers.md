---
title: FASTA headers
type: help
categories: Technical,Sequence,help
---

The following is a description of FASTA headers for UniProtKB (including alternative isoforms), UniRef, UniParc (both generic and for proteomes) and archived UniProtKB versions. NCBI's program formatdb (in particular its -o option) is compatible with the UniProtKB fasta headers.

Note that in the document below square brackets `[ ]` indicate optional fields.

# UniProtKB

    >db|UniqueIdentifier|EntryName ProteinName OS=OrganismName OX=OrganismIdentifier[ GN=GeneName] PE=ProteinExistence SV=SequenceVersion

Where:

- _db_ is 'sp' for UniProtKB/Swiss-Prot and 'tr' for UniProtKB/TrEMBL.
- _UniqueIdentifier_ is the primary [accession number](https://www.uniprot.org/help/accession_numbers) of the UniProtKB entry.
- _EntryName_ is the [entry name](https://www.uniprot.org/help/entry_name) of the UniProtKB entry.
- _ProteinName_ is the [recommended name](https://www.uniprot.org/help/protein_names) of the UniProtKB entry as annotated in the `RecName` field. For UniProtKB/TrEMBL entries without a `RecName` field, the `SubName` field is used. In case of multiple `SubNames`, the first one is used. The 'precursor' attribute is excluded, 'Fragment' is included with the name if applicable.
- _OrganismName_ is the [scientific name of the organism](https://www.uniprot.org/help/organism-name) of the UniProtKB entry.
- _OrganismIdentifier_ is the [unique identifier of the source organism, assigned by the NCBI](https://www.uniprot.org/help/taxonomic_identifier).
- _GeneName_ is the first [gene name](https://www.uniprot.org/help/gene_name) of the UniProtKB entry. If there is no gene name, `OrderedLocusName` or `ORFname`, the `GN` field is not listed.
- _ProteinExistence_ is the numerical value describing the [evidence for the existence](https://www.uniprot.org/help/protein_existence) of the protein.
- _SequenceVersion_ is the [version number](https://www.uniprot.org/help/entry_history) of the sequence.

Examples:

    >sp|Q8I6R7|ACN2_ACAGO Acanthoscurrin-2 (Fragment) OS=Acanthoscurria gomesiana OX=115339 GN=acantho2 PE=1 SV=1
    >sp|P27748|ACOX_CUPNH Acetoin catabolism protein X OS=Cupriavidus necator (strain ATCC 17699 / H16 / DSM 428 / Stanier 337) OX=381666 GN=acoX PE=4 SV=2
    >sp|P04224|HA22_MOUSE H-2 class II histocompatibility antigen, E-K alpha chain OS=Mus musculus OX=10090 PE=1 SV=1

    >tr|Q3SA23|Q3SA23_9HIV1 Protein Nef (Fragment) OS=Human immunodeficiency virus 1  OX=11676 GN=nef PE=3 SV=1
    >tr|Q8N2H2|Q8N2H2_HUMAN cDNA FLJ90785 fis, clone THYRO1001457, moderately similar to H.sapiens protein kinase C mu OS=Homo sapiens OX=9606 PE=2 SV=1

## Alternative isoforms (this only applies to UniProtKB/Swiss-Prot):

    >sp|IsoID|EntryName Isoform IsoformName of ProteinName OS=OrganismName OX=OrganismIdentifier[ GN=GeneName]

Where:

- _IsoID_ is the isoform identifier as assigned in the [ALTERNATIVE PRODUCTS](https://www.uniprot.org/help/alternative_products) section of the UniProtKB entry.
- _IsoformName_ is the isoform name as annotated in the ALTERNATIVE PRODUCTS `Name` field of the UniProtKB entry.

_ProteinExistence_ and _SequenceVersion_ do not apply to alternative isoforms (_ProteinExistence_ is dependent on the number of cDNA sequences, which is not known for individual isoforms).

Example:

    >sp|Q4R572-2|1433B_MACFA Isoform Short of 14-3-3 protein beta/alpha OS=Macaca fascicularis OX=9541 GN=YWHAB

# UniRef

    >UniqueIdentifier ClusterName n=Members Tax=TaxonName TaxID=TaxonIdentifier RepID=RepresentativeMember

Where:

- _UniqueIdentifier_ is the primary accession number of the UniRef cluster.
- _ClusterName_ is the name of the UniRef cluster.
- _Members_ is the number of UniRef cluster members.
- _TaxonName_ is the scientific name of the lowest common taxon shared by all UniRef cluster members.
- _TaxonIdentifier_ is the NCBI taxonomy identifier of the lowest common taxon shared by all UniRef cluster members.
- _RepresentativeMember_ is the entry name of the representative member of the UniRef cluster.

Example:

    >UniRef50_Q9K794 Putative AgrB-like protein n=2 Tax=Bacillus TaxID=1386 RepID=AGRB_BACHD

# UniParc
## Generic UniParc

    >UniqueIdentifier status=Status

Where:

- _UniqueIdentifier_ is the primary accession number of the UniParc entry.
- _Status_ is 'active' if the UniParc entry has at least one active cross-reference, and 'inactive' if it does not have any active cross-references.

Example:

    >UPI0000000005 status=active

## UniParc for Proteomes
    
    >UniqueIdentifier[ ProteinNameList][ OS=OrganismName][ OX=OrganismIdentifier][ GN=GeneNameList][ AC=UniProtKBAcList][ SS=SourceAcList][ PC=(Proteome:Component)List]

Where:

- _UniqueIdentifier_ is the primary accession number of the UniParc entry.
- _ProteinNameList_ is a list of protein names.
- _OrganismName_ is the organism name.
- _OrganismIdentifier_ is the NCBI taxonomy ID or organism identifier.
- _GeneNameList_ is a list of gene names.
- _UniProtKBAcList_ is a list of associated UniProtKB accessions.
- _SourceAcList_ is a list of source accessions.
- _(Proteome:Component)List_ is a list of proteome and component pairs in the format _ProteomeID:Component_.

Additional Notes
- Fields with multiple values are separated by the pipe symbol `|`.

Examples:

    >UPI0000000AE5 IS30 family transposase OS=Escherichia coli str. K-12 substr. MG1655 OX=511145 GN=insI2|insI3 SS=EMBL:AAC74486|EMBL:AAC77240 PC=UP000000625:Chromosome
    >UPI0000038DD7 Pantothenate kinase OS=Escherichia coli str. K-12 substr. MG1655 OX=511145 GN=coaA SS=EMBL:AAC76952 PC=UP000000625:Chromosome

# Archived UniProtKB sequence versions

    >db|UniqueIdentifier archived from Release ReleaseNumber ReleaseDate SV=SequenceVersion

Where:

- _db_ is 'sp' for UniProtKB/Swiss-Prot and 'tr' for UniProtKB/TrEMBL.
- _UniqueIdentifier_ is the primary accession number of the UniProtKB entry.
- _ReleaseNumber_ refers to the release from which the sequence was archived (Swiss-Prot or TrEMBL release numbers for releases prior to the first UniProt release, and both UniProt and Swiss-Prot or TrEMBL release numbers for releases after the first UniProt release).
- _ReleaseDate_ is the date of the release form which the sequence was archived.
- _SequenceVersion_ is the version number of the sequence.

Examples:

'pre-UniProt':

    >sp|P05067 archived from Release 18.0 01-MAY-1991 SV=3
    >tr|Q55167 archived from Release 17.0 01-JUN-2001 SV=1

'post-UniProt':

    >sp|P05067 archived from Release 9.2/51.2 28-NOV-2006 SV=3
    >tr|A0RTJ8 archived from Release 11.0/36.0 29-MAY-2007 SV=1

Related terms: FASTA header, FASTA format, FASTA comment
