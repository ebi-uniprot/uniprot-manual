---
title: ID Mapping
type: help
categories: Text_search,Technical,Website,help
---

To explore and try out the ID Mapping services, please refer to:
* The [ID Mapping website tool](http://www.uniprot.org/id-mapping)

# Overview

The ID Mapping service can map between the identifiers used in one database, to the identifiers of another, e.g., 
Ensembl to PomBase. If you map to UniProtKB, UniParc or UniRef data, the full entries will be returned to you
for convenience.

This document serves as a basic guide to using the ID Mapping services offered.

# Submitting an ID Mapping job

> POST /idmapping/run

For example, to map UniProtKB entries P21802, P12345, we could POST a request to the above REST end-point as follows: 
   

> **Request**
> ```bash
> % curl --request POST 'https://rest.uniprot.org/idmapping/run' --form 'ids="P21802,P12345"' --form 'from="UniProtKB_AC-ID"' --form 'to="UniRef90"'
> ```
> **Reponse**
> ```bash
> {"jobId":"27a020f6334184c4eb382111fbcad0e848f40300"}
> ```

Be sure to take note of the `jobId`. This will be used later to:

* poll the status of the job
* fetch/download the results
* get details about the job

## Various limits on ID Mapping Job Submission
**Limit**|**Details**
:-----:|:-----:
100,000|Total number of ids allowed in comma separated param `ids` in `/idmapping/run` api
500,000|Total number of "mapped to" ids allowed
100,000|Total number of "mapped to" ids allowed to be enriched by UniProt data
10,000|Total number of "mapped to" ids allowed with filtering

# Polling the status of a job

> GET /idmapping/status/{jobId}

Continuing the above example, we can use the `jobId` to find out the status of the job as follows:

> **Request**
> ```bash
> % curl -i 'https://rest.uniprot.org/idmapping/status/27a020f6334184c4eb382111fbcad0e848f40300'
> ```
> **Response**
> ```bash
> HTTP/1.1 303 
> Server: nginx/1.17.7
> Location: https://rest.uniprot.org/idmapping/uniref/results/27a020f6334184c4eb382111fbcad0e848f40300
> Content-Type: application/json
> Access-Control-Allow-Origin: *
>...
> {"jobStatus":"FINISHED"}
> ```

Note that the `jobStatus` is finished, indicating that the job's results are ready to be fetched. Note also the [HTTP 303](https://httpstatuses.com/303)
header that indicates the results can be retrieved via the URL in the `Location` header. 

# Fetching the results of a job
## Paged results

The results of a job can be retrieved one page at a time using one of following end-points:
      
> GET /idmapping/results/{jobId}<br>
> GET /idmapping/{uniprot_db}/results/{jobId} ## where {uniprot_db} is one of UniParc, UniProtKB or UniRef

For example, when mapping [P21802, P12345 to UniRef90](#example) could do:

> **Request**            
> ```bash
> % curl -s "https://rest.uniprot.org/idmapping/uniref/results/27a020f6334184c4eb382111fbcad0e848f40300"
> ```
> **Response**
> ```bash
> {
>   "results": [
>     {
>       "from": "P21802",
>       "to": {
>         "id": "UniRef90_P21802",
>         "name": "Cluster: Fibroblast growth factor receptor 2",
>         "updated": "2021-06-02",
>         "entryType": "UniRef90",
>  ...
> ```
                                                                                 
Note the `from` and `to` attributes, denoting the source identifiers and corresponding mapped identifier. Also,
since the `to` database is UniRef90, we return also the target entry details.

## Downloading results  

Downloading the results of a job is achieved via one of the following end-points: 

> GET /idmapping/stream/{jobId}<br>
> GET /idmapping/{uniprot_db}/results/stream/{jobId}
                                                     
Continuing our [example above](#example), we would download the results by making a request to the following URL:
   
> **Request**
> ```bash
> % curl -s "https://rest.uniprot.org/idmapping/uniref/results/stream/27a020f6334184c4eb382111fbcad0e848f40300"
> ```
> **Response**
> ```bash
> {
>   "results": [
>     {
>       "from": "P21802",
>       "to": {
>         "id": "UniRef90_P21802",
>         "name": "Cluster: Fibroblast growth factor receptor 2",
>         "updated": "2021-06-02",
>         "entryType": "UniRef90",
>  ...
> ```
       
> **NOTE** to add the content-disposition header, e.g., so that a download file dialogue appears in a browser, include
>          the request parameter, `download=true`.          

# Fetching details about a job

Details of a submitted job, including the `from`, `to` and `ids` to map, can be obtained via this end-point:

> GET /idmapping/details/{jobId}

For example:

> **Request**
> ```bash
> % curl -s "https://rest.uniprot.org/idmapping/uniref/details/27a020f6334184c4eb382111fbcad0e848f40300"
> ```
> **Response**
> ```bash
> {
>   "from": "UniProtKB_AC-ID",
>   "to": "UniRef90",
>   "ids": "P21802,P12345",
>   "taxId": null,
>   "redirectURL": "https://rest.uniprot.org/idmapping/uniref/results/27a020f6334184c4eb382111fbcad0e848f40300"
> }
> ```
# Warnings and errors in various responses

**Problem Type**|**Code**|**Message**
:-----:|:-----:|:-----:
Warning|20|Filters are not supported for mapping results with IDs more than 10,000
Warning|21|UniProt data enrichment is not supported for mapping results with "mapped to" IDs more than 100,000
Error|40|Id Mapping API is not supported for mapping results with "mapped to" IDs more than 500,000
Error|50|\<Actual application error as message\>

# Valid _from_ and _to_ databases pairs

You can map `from` one database `to` another database. To find the name of all the possible valid databases pairs (both from and to), use the below curl command:
         
```bash
% curl https://rest.uniprot.org/configure/idmapping/fields
```
## How to interpret the response                   

The response has two top sections:
- groups
    - items
- rules

Each group represents a logical group of databases, represented as an array of `items`.

The value of `groupName` is used by website user-interface to group together related databases, e.g., Sequence databases
like EMBL/GenBank/DDBJ.

Each item in the `items` array has the following attributes:
- displayName : Used by the [website user-interface](https://www.uniprot.org/id-mapping). It is not used in subsequent 
API calls.
- name : Name of `from` or `to` database to be passed in the API request.
- from: Boolean flag indicating whether `name` can be used as a `from` database. Defaults to false.
- to: Boolean flag indicating whether `name` can be used as a `to` database. Defaults to false.
- ruleId: Refers a rule in the `rules` section to find all possible values of `to` databases.

Each rule in the `rules` array describes all possible `to` databases for a given `from` database.
It has the following attributes:

- ruleId : Unique identifier of the rule. Referred to by individual items within `groups.items`.
- tos: List of possible `to` databases for a given `from` item.
- defaultTo: Used by the website user-interface to be selected by default in its dropdown menu. This field is not 
relevant to standard programmatic users.
- taxonId: Boolean flag indicating whether a third optional param `taxonId`(Taxonomy Id) is allowed in API requests
in addition to the `from` and `to` request parameters.

## Example: finding which databases UniParc identifiers can be mapped to

1. Given the response from the above request and looking within the `groups.items` entities, find an 
item where `displayName` or `name` matches `UniParc` and, importantly, `from` is `true`. The relevant `item` is:

```json
{
  "displayName": "UniParc", 
  "name": "UniParc", 
  "from": true, 
  "to": true, 
  "ruleId": 2
}
```
The important parts of this JSON object to note are: 
- `from`: since this is `true`, we know that the value of `name` (`UniParc`) can be used as the `from` request parameter
in a POST request to [`/idmapping/run`](#submitting-an-id-mapping-job).
- `to`: since this is `true`, we know that the value of `name` (`UniParc`) can be used as the `to` request parameter in 
a POST request to [`/idmapping/run`](#submitting-an-id-mapping-job).
- `ruleId`: take note of the value, `2`, as this will be used to identify *all* valid databases that UniParc identifiers 
can be mapped to.

2. Given the response from the [above request](#example_uniparc) and looking within the `rules` array, find a rule where
`ruleId` is 2. The relevant JSON object is given below:

```json
{
  "ruleId": 2,
  "tos": [
    "UniProtKB",
    "UniProtKB-Swiss-Prot",
    "UniParc"
  ],
  "defaultTo": "UniProtKB",
  "taxonId": false
}
```

The important parts of this object to note are:
- `tos`: this array lists _all possible valid_ `to` values for a POST request to [`/idmapping/run`](#submitting-an-id-mapping-job), when 
`UniParc` is used as `from` request parameter value. Passing anything other than the values listed in `tos` will result
in an error.
- `taxonId`: The `taxonId` flag is set to false, indicating that this `from` and `to` combination does not accept an 
optional `taxonId` (taxonomy identifier) when submitting the job.

3. Putting the findings into practice, we can now construct ID mapping POST requests as follows:

```bash
% curl --request POST 'https://rest.uniprot.org/idmapping/run' \
    --form 'ids="<YOUR UNIPARC ID LIST IN COMMA SEPARATED FORM>"' \ 
    --form 'from="UniParc"' \
    --form 'to="<UniProtKB or UniProtKB-Swiss-Prot or UniParc>"'
```
Giving a concrete example:

```bash
% curl --request POST 'https://rest.uniprot.org/idmapping/run' \ 
   --form 'ids="UPI0000000001,UPI0000000002"' \ 
   --form 'from="UniParc"' \ 
   --form 'to="UniProtKB"'
```
