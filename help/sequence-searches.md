
---
title: Sequence similarity searches
categories: Website,help
---

[Tutorial/Video](https://www.youtube.com/watch?v=UPaConHNP7E)

Select the _Blast_ tab of the toolbar to run a sequence similarity search with the BLAST (Basic Local Alignment Search Tool) program:

1.  Enter either a protein or nucleotide sequence (raw sequence or fasta format) or a UniProt identifier into the form field.
2.  Click the _Blast_ button.

The following kinds of UniProt identifiers are supported:

**P00750**

UniProtKB entry

**P00750-2**

UniProtKB entry isoform sequence

**P00750\[1-20\]**

Part of UniProtKB entry sequence, from its 1st to 20th amino acid residue (inclusive)

**A4\_HUMAN**

UniProtKB entry name

**UPI0000000001**

UniParc entry

**UniRef100\_P00750**

UniRef entry

If you select the _Blast_ tab of the toolbar from a UniProtKB, UniRef or UniParc entry page, the current sequence is prefilled in the form.

Jobs have unique identifiers, which (depending on the job type) can be used in queries (e.g. to get the intersection of two sequence similarity searches). Job identifiers and the related data are kept for 7 days, and are then deleted.

#### Options

**Database**

Database against which the search is performed: UniProtKB or clusters of sequences with 100%, 90% or 50% identity.

**Threshold**

The expectation value (E) threshold is a statistical measure of the number of expected matches in a random database. The lower the e-value, the more likely the match is to be significant. E-values between 0.1 and 10 are generally dubious, and over 10 are unlikely to have biological significance. In all cases, those matches need to be verified manually. You may need to increase the E threshold if you have a very short query sequence, to detect very weak similarities, or similarities in a short region, or if your sequence has a low complexity region and you use the "filter" option

**Matrix**

The matrix assigns a probability score for each position in an alignment. The BLOSUM matrix assigns a probability score for each position in an alignment that is based on the frequency with which that substitution is known to occur among consensus blocks within related proteins. BLOSUM62 is among the best of the available matrices for detecting weak protein similarities. The PAM set of matrices is also available. If "Auto" is set, the matrix will be selected depending on the query sequence length.

**Filtering**

Low-complexity regions (e.g. stretches of cysteine in [Q03751](http://www.uniprot.org/uniprot/Q03751), or hydrophobic regions in membrane proteins) tend to produce spurious, insignificant matches with sequences in the database which have the same kind of low-complexity regions, but are unrelated biologically. If "Filter low complexity regions" is selected, the query sequence will be run through the program SEG, and all amino acids in low-complexity regions will be replaced by X's.

**Gapped**

This will allow gaps to be introduced in the sequences when the comparison is done.

**Hits**

Limits the number of returned alignments.

#### Related services

**[BLAST](http://web.expasy.org/blast/) (ExPASy)**

Sequence similarity search

**[BLAST](https://www.ebi.ac.uk/Tools/sss/ncbiblast/) (EBI)**

Sequence similarity search

**[FASTA](https://www.ebi.ac.uk/Tools/sss/fasta/) (EBI)**

Sequence similarity search

**[iProClass](http://pir.georgetown.edu/iproclass/index.shtml) (PIR)**

Query a sequence against the iProClass database, which contains both sequences and protein families

**[InterProScan](https://www.ebi.ac.uk/interpro/search/sequence/) (EBI)**

Query a sequence against the InterPro database, which contains protein families, domains, and motifs

**[ScanProsite](http://prosite.expasy.org/scanprosite/) (ExPASy)**

Scan a protein sequence for patterns, or use a pattern to scan protein sequences

**[HMMER](https://www.ebi.ac.uk/Tools/hmmer/) (EBI)**

Sequence Similarity Search
        