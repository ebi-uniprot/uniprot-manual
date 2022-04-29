---
title: How can I retrieve all UniProtKB entries for which the 3D structure is known?
type: help
categories: UniProtKB,3D_structure,Text_search,faq
---

# Retrieve all UniProtKB entries for which the 3D structure is known

Using the query builder:

- Click **Advanced** in the search bar to open the query builder
- Select **Searching in** : `UniProtKB`
- Click the field dropdown and type in : `PDB`
- Select `Cross-references / 3D structure databases / PDB`
- Enter **value** : `*`
- Depending on your interests, choose amongst the following: Show only `reviewed` (UniProtKB/Swiss-Prot) or `unreviewed` (UniProtKB/TrEMBL) entries
- **[Result (reviewed entries only)](https://www.uniprot.org/uniprotkb?query=(database:pdb)%20AND%20(reviewed:true))**.

# Retrieve all proteins with 3D structures determined by Electron microscopy (EM)

Other methods: Model, X-ray, NMR, Neutron (Neutron diffraction), Fiber (Fiber diffraction), IR (Infrared spectroscopy)

Using the query builder:

- Click **Advanced** in the search bar to open the query builder
- Select **Searching in** : `UniProtKB`
- Click the field dropdown and type in : `Spectrometry`
- Select `Sequence / Mass Spectrometry`
- Enter **value** : `*`
- Click **Search**
- Depending on your interests, choose amongst the following: Show only `reviewed` (UniProtKB/Swiss-Prot) or `unreviewed` (UniProtKB/TrEMBL) entries
- **[result (reviewed entries only)](https://www.uniprot.org/uniprotkb?query=(cc_mass_spectrometry:*)%20AND%20(reviewed:true))**.
- You can combine query such as: "myoglobin AND method:X-ray":
- **[result](https://www.uniprot.org/uniprotkb?query=myoglobin+AND+method%3AX-ray)**.
