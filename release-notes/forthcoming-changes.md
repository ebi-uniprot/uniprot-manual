---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---


**Table of contents**

   * Change of URIs for the HAMAP database - **On April 09, 2025**

### Change of URIs for the HAMAP database

For historic reasons, UniProt had to generate URIs to cross-reference databases that did not have an RDF representation or did not provide stable URIs such as [PURLs](https://en.wikipedia.org/wiki/Persistent_uniform_resource_locator) (permanent uniform resource locators). The SIB Swiss Institute of Bioinformatics has now committed to provide stable URIs for the resources that it supports, and the first database to adopt this is HAMAP. We will change the HAMAP URIs accordingly:
 
* The links to HAMAP signatures (used in UniProtKB cross-references and in UniParc) will change from:  
    ```
    http://purl.uniprot.org/hamap/MF_00012
    ```  
  to:  
    ```
    https://purl.expasy.org/hamap/signature/MF_00012
    ```

* The links to HAMAP annotation rules (used in UniProtKB attributions) will change from:  
    ```
    http://purl.uniprot.org/hamap-rule/MF_00012
    ```  
  to:  
    ```
    https://purl.expasy.org/hamap/rule/MF_00012
    ```
