---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

# Changes in UniProt website REST API for UniParc

**On November 27th, 2024**

UniParc entries may contain ten thousands of cross-references. This information is not relevant for all users and can make data downloads slow. For these reasons we will make the following changes to our API:

- **New endpoint for UniParc core data** (sequence and InterPro matches):
  
  - `/uniparc/{upi}/light`  

- **New endpoints for UniParc cross-references**:
  
  - `/uniparc/{upi}/databases`
  - `/uniparc/{upi}/databases/stream`

- **Changes to existing endpoints**:
  
  The responses of the following endpoints will no longer include cross-references:
  
  - `/uniparc/search`
  - `/uniparc/stream`
  - `/uniparc/upis`
  
  All current search fields will still be supported for querying.

- **Backward compatibility**:
  
  - `/uniparc/{upi}` will continue to return the full UniParc entry, including all cross-references.

Note: We will adapt the [uniparc.xsd](https://ftp.uniprot.org/pub/databases/uniprot/current_release/uniparc/uniparc.xsd) to support the new endpoint for UniParc core data by making the `entry` element's child element `dbReference` optional. The UniParc XML files on our [FTP site](https://ftp.uniprot.org/pub/databases/uniprot/current_release/uniparc/xml/all/) will remain unchanged.

If you have questions about these changes, please do not hesitate to contact our [our helpdesk](https://www.uniprot.org/contact).
