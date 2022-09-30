---
title: Protein Embeddings
type: help
categories: UniProtKB,Automatic_annotation,help
---

Protein embeddings is a way to encode functional and structural properties of a protein, mostly from its 
sequence only, in a machine-friendly format (vector representation). Embeddings are computationally expensive, 
however once computed they can be leveraged for different tasks such as sequence similarity search, sequence 
clustering, and sequence classification.

UniProt is providing raw embeddings (per-protein and per-residue using ProtT5 model) for UniProtKB/Swiss-Prot and some 
reference proteomes of model organisms (such as Homo sapiens, Sars-CoV-2, and E.coli) with every release.

**Note:** Proteins longer than 12k residues are excluded due to limitation of GPU memory (only a handful of proteins 
are excluded). 

## Sample code
The embeddings h5 files store the embeddings as key-value-pairs. The key is the protein accession and the value is 
the embeddings vector. The following code snippet shows how to read and iterate over an embeddings file in python.

```python
import numpy as np
import h5py

with h5py.File("path/to/embeddings.h5", "r") as file:
    print(f"number of entries: {len(file.items())}")
    for sequence_id, embedding in file.items():
        print(
            f"  id: {sequence_id}, "
            f"  embeddings shape: {embedding.shape}, "
            f"  embeddings mean: {np.array(embedding).mean()}"
        )
```

##### SARS-CoV-2 embeddings sample output (as per 2022_04 release)
###### per-protein file:

```
number of entries: 17
  id: A0A663DJA2,   embeddings shape: (1024,),   embeddings mean: 0.0006136894226074219
  id: P0DTC1,   embeddings shape: (1024,),   embeddings mean: 0.0011968612670898438
  id: P0DTC2,   embeddings shape: (1024,),   embeddings mean: 0.001041412353515625
  ...
```

###### per-residue file:

```
number of entries: 17
  id: A0A663DJA2,   embeddings shape: (38, 1024),   embeddings mean: 0.0006127357482910156
  id: P0DTC1,   embeddings shape: (4405, 1024),   embeddings mean: 0.00119781494140625
  id: P0DTC2,   embeddings shape: (1273, 1024),   embeddings mean: 0.001041412353515625
  ...
```