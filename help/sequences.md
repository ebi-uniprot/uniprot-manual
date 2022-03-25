---
title: Sequences
categories: Sequence,manual
---

This section displays by default the [canonical protein sequence](https://www.uniprot.org/help/canonical%5Fand%5Fisoforms) and upon request all isoforms described in the entry. It also includes information pertinent to the sequence(s), including [length](https://www.uniprot.org/help/sequence%5Flength) and molecular weight.

The protein sequence displayed by default is the protein sequence to which all positional annotation refers. We call it the 'canonical' sequence.

We use the official [IUPAC](http://www.iupac.org/) amino acid one-letter code. For the amino acids selenocysteine (Sec; U) and pyrrolysine (Pyl; O), we follow the proposed nomenclature.

For each isoform, the name of the isoform is provided, as well as its length and molecular mass in Daltons. The mass is calculated on the basis of the amino acid composition of the entire sequence. It does not take into account PTMs, thus excluding any proteolytic processing.

The checksum of the displayed sequence is also given. Currently the checksum is a 64-bit CRC (Cyclic Redundancy Check) value ('CRC64') based on a algorithm described in the ISO 3309 standard. The generator polynomial used is x64 + x4 + x3 + x + 1 (See reference). Although in theory two different sequences could have the same CRC64 value, the likelihood that this would happen is extremely low.

References:

[Nomenclature and symbolism for amino acids and peptides (Recommendation 1983)(IUPAC)](http://www.iupac.org/publications/pac/1984/pdf/5605x0595.pdf)

[IUPAC-IUBMB Joint Commission on Biochemical Nomenclature (JCBN) and Nomenclature Committee of IUBMB (NC-IUBMB), newsletter 1999](http://dx.doi.org/doi:10.1046/j.1432-1327.1999.news99.x)

Press W.H., Flannery B.P., Teukolsky S.A., Vetterling W.T.  
["Numerical recipes in C", 2nd ed., pp896-902, Cambridge University Press (1993)](http://www.nrbook.com/a/bookcpdf.php)

#### Related documents

[Where do the UniProtKB protein sequences come from?](https://www.uniprot.org/help/sequence%5Forigin)

[What are UniProtKB's criteria for defining a CDS as a protein?](https://www.uniprot.org/help/cds%5Fprotein%5Fdefinition)

[What is the canonical sequence? Are all isoforms described in one entry? How can I retrieve them?](https://www.uniprot.org/help/canonical%5Fand%5Fisoforms)

[Does UniProtKB contain all protein sequences?](https://www.uniprot.org/help/uniprotkb%5Fcoverage)

[How do I get the nucleotide sequence that corresponds to the canonical UniProtKB sequence?](https://www.uniprot.org/help/canonical%5Fnucleotide)

[How to retrieve a complete set of protein sequences?](https://www.uniprot.org/help/retrieve%5Fsets)

[Non-standard residue](https://www.uniprot.org/help/non%5Fstd)
