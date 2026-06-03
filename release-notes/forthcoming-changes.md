---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

**Table of contents**

   * [UniParc XML changes](#uniparc-xml-changes) - **With release 2026_02**
   * [UniParc API changes](#uniparc-api-changes) - **With release 2026_02**
   * [Planned automatic annotation service developments](#planned-automatic-annotation-service-developments) - **From release 2026_02**


# UniParc XML changes

In Uniparc XML, the ```proteome_id``` and ```component``` properties have been retired. In their place, a new property type, ```proteomeid_component``` has been introduced. Its value is a concatenation of the ProteomeID and Component, joined by a colon. 
This property type is multi-valued and can appear multiple times with distinct entries.
e.g
```
<property type="proteomeid_component" value="UP000179299:Segment"/>
<property type="proteomeid_component" value="UP000179429:Genome"/>
```

# UniParc API changes
## Consolidation of ```proteomeId``` and ```component``` fields in the UniParc databases endpoint.

In the UniParc databases endpoint response for the two existing fields ```proteomeId``` and ```component``` will be removed and replaced with ```list of proteomes``` each proteome in the response will have the fields ```id``` and ```component```.
e.g
```
{
  "proteomes": [
    {
      "id": "proteome1",
      "component": "component1"
    },
    {
      "id": "proteome2",
      "component": "component2"
    }
  ]
}
```
## Searching UniParc using the proteomes component
Users searching UniParc for a proteome component using the API will need to enter the fully qualified name of the proteome component in the form of <proteome_id>:<component_name> when submitting the query.
User using the website advanced search functionality will be able to carry out the same query using the search fields ```proteome_id``` and ```component_name```.

```proteomecomponent:'UP000008269:Segment'```


# Planned automatic annotation service developments
We aim to provide a better automatic annotation service, both in UniParc and as a downloadable tool, through [UniFIRE](https://gitlab.ebi.ac.uk/uniprot-public/unifire).
