---
title: Downloaded data seems incomplete or corrupted - how can I get help with download problems?
type: help
categories: Download,Technical,faq
---

# FTP downloads

Every folder on our [FTP server](https://ftp.uniprot.org/) contains a file called RELEASE.metalink that specifies the size and MD5 checksum of every file in that folder, e.g.  
<https://ftp.uniprot.org/pub/databases/uniprot/knowledgebase/complete/RELEASE.metalink>

[Metalink](http://en.wikipedia.org/wiki/Metalink) is an extensible metadata file format that describes one or more computer files available for download. It facilitates file verification and recovery from data corruption and lists alternate download sources (mirror URIs).

Various command line download tools, e.g. [cURL](http://curl.haxx.se/) version 7.30 or higher and [aria2](http://aria2.sourceforge.net/), support metalink.

Example: The following command will download all files in the `current_release/` folder and verify their MD5 checksums:

    curl --metalink https://ftp.uniprot.org/pub/databases/uniprot/current_release/RELEASE.metalink

They will be downloaded from one of the alternative locations mentioned in the metalink file. If one FTP server goes down during a download, programs can automatically switch to another mirror location. Some programs can also download segments from several FTP locations at the same time, which can make downloads much faster.

Please note that UniProt can be downloaded from the consortium member FTP sites at three different geographical locations:

USA: <https://ftp.uniprot.org/pub/databases/uniprot>  
UK: <https://ftp.ebi.ac.uk/pub/databases/uniprot>  
Switzerland: <https://ftp.expasy.org/databases/uniprot>

# HTTP downloads

Due to HTTP transport unreliability (HTTP streams tend to fail after a while due to packet loss), large downloads should be split into smaller chunks using the "offset" and "limit" functions. These are described in our API help page [Retrieving entries via queries](https://www.uniprot.org/help/api_queries).

1\) Start by retrieving the number of results in your query by checking the "X-Total-Results" header like in the example [Download all UniProt sequences for a given organism in FASTA format](https://www.uniprot.org/help/programmatic_access#downloading).

2\) If the number of results x is greater than 50000, repeat your query and append the following to the URL:

    &offset=0&limit=50000
    &offset=50000&limit=50000
    &offset=100000&limit=50000 etc.

Also use `compress=yes`

e.g. (using 50 instead of 50000 to make the file more manageable in the browser)

    https://www.uniprot.org/uniprot/?query=organism:%22Homo%20sapiens%20(Human)%20%5B9606%5D%22&fil=&offset=0&limit=50&compress=yes&format=fasta
    https://www.uniprot.org/uniprot/?query=organism:%22Homo%20sapiens%20(Human)%20%5B9606%5D%22&fil=&offset=50&limit=50&compress=yes&format=fasta
    https://www.uniprot.org/uniprot/?query=organism:%22Homo%20sapiens%20(Human)%20%5B9606%5D%22&fil=&offset=100&limit=50&compress=yes&format=fasta

etc.

3\) Once you have your download, use `gzip -t` to check the integrity of your file. Uncompress the chunks and concatenate them into a single download file.
