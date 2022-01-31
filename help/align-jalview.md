---
title: Using Jalview and Java Web Start
categories: Technical,help
---

The Jalview application, which is available on alignment result pages via the "Download" dropdown, requires Java Web Start. From the "Download" dropdown, select the "jalview" format. A file with the extension 'jnlp' is downloaded and passed to the program Java Web Start (javaws), which then runs Jalview with the correct data and settings.

Java Web Start is installed with Java. You can download Java at [java.com](http://www.java.com/).  
After installing Java you may still need to associate the '\*.jnlp' files with the program javaws. When selecting jalview from the dropdown, most operating systems will let you open the '\*.jnlp' file with a program or to save it on disk:

-   If presented with an option to [open with](http://www.uniprot.org/use) the dropdown list or file dialog to select javaws (Java Web Start). If it is not present in the list, see below for common locations to find javaws.

<!-- -->

-   If you are only given the option to save the '\*.jnlp' file, do so. After saving you need to manually associate the javaws program with the file extension '\*.jnlp'. How this is done depends on your operating system and desktop environment. Most often it can be done by right-clicking on the downloaded file and choosing "open with".

Java Web Start is often installed in the following locations:

-   Windows: Program Files\\Java\\bin\\javaws
-   Mac: /Library/Java/Home/bin/javaws
-   Linux: /usr/bin/javaws or /opt/java/bin/javaws, else try the command 'which javaws'.

For more information on Java Web Start, see the [java.com faq entry](http://www.java.com/en/download/faq/java%5Fwebstart.xml)
