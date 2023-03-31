---
title: File Generation & Download
type: help
categories: UniProtKB,help,download,async_download,file_generation
---

# File Generation for Downloading Large Files - BETA Feature 
When users download data from UniProtKB, it is typically treated as a "normal" download, which is offered as a stream.

For larger files (currently files with entries that are more than 10M), a separate file must be generated for download.  
Much like BLAST or IDMapping services at UniProt, this file generation request is sent as a job, and can be viewed [your jobs dashboard](https://www.uniprot.org/tool-dashboard).  
Only after the generation of the file is completed the file is available for download.


## What are the advantages?
The biggest advantage comes from downloading from the website via a browser.  
Users were previously only able to download large files via ftp or programmatic access. Users now have the ability to download large files directly from the browser.  
From here, users will be able to pause and resume downloads on their respective browsers, and this also means that users don't need to restart the download from scratch in the event of a network timeout or disconnection.


## When does UniProt trigger File Generation?
Users must generate a file for downloads on files with more than 10M entries. 
UniProt's download system will let you know if the file you're attempting to download requires file generation.

For files with less than 10M entries, the download will be available directly as normal.


## What are the different file formats and compression?
UniProt's file generation is able to create compressed downloadable files for all file types minus .xlsx files.  
For use in Microsoft Excel, please download as a tab-delimited file (.tsv).  
All files must be compressed (.gz) for download in File Generation. 
Please note that it is not possible to download unzipped files when using File Generation.

## How do you unzip the downloaded files?
You can unzip the file by using a file compression program of your choice, such as WinZip, 7-Zip, or Unarchiver to name a few.

You can also unzip the file using command line prompts.  
If you're using Windows, you can extract GZ files using the `tar` command in Command Prompt.  
On a Mac, use the command `gunzip filename.gz` in a Terminal window.  
If you're using Linux, use `gzip -d filename.gz` to extract the files.  
