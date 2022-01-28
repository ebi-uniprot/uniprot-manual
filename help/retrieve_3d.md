
---
title: How can I retrieve all UniProtKB entries for which the 3D structure is known?
categories: UniProtKB,3D_structure,Text_search,faq
---

1 - Retrieve all UniProtKB entries for which the 3D structure is known

Using the query builder:

*   Select **Search in**: `Protein Knowledgebase (UniProtKB)`
*   Click **Advanced Search »** to open the query builder
*   Select **Field**: `Cross-reference [DR]`
*   Select **Database**: `PDB`
*   Click **Add & Search**
*   Depending on your interests, choose amongst the following: Show only `reviewed` (UniProtKB/Swiss-Prot) or `unreviewed` (UniProtKB/TrEMBL) entries
*   **[result (reviewed entries only)](http://www.uniprot.org/uniprot/?query=database%3Apdb+AND+reviewed%3Ayes)**.

2 - Retrieve all proteins with 3D structures determined by Electron microscopy (EM)

Other methods: Model, X-ray, NMR, Neutron (Neutron diffraction), Fiber (Fiber diffraction), IR (Infrared spectroscopy)

Using the query builder:

*   Select **Search in**: `Protein Knowledgebase (UniProtKB)`
*   Type `Method:EM`
*   Click **Search**
*   Depending on your interests, choose amongst the following: Show only `reviewed` (UniProtKB/Swiss-Prot) or `unreviewed` (UniProtKB/TrEMBL) entries
*   **[result (reviewed entries only)](http://www.uniprot.org/uniprot/?query=method%3Aem+AND+reviewed%3Ayes)**.
*   You can combine query such as: "myoglobin AND method:X-ray":
*   **[result](http://www.uniprot.org/uniprot/?query=myoglobin+AND+method%3AX-ray)**.
        