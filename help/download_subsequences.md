
---
title: How can I download the sequences corresponding to a specified domain or region from a list of UniProt entries?
categories: UniProtKB,Download,Sequence,Text_search,Family_and_domains,faq
---

Run your query, e.g. to retrieve the UniProtKB entries annotated to contain  
  
[disintegrin domains](http://www.uniprot.org/uniprot/?query=annotation%3a%28type%3a%22positional+domain%22+disintegrin%29&sort=score&format=*), (or alternatively, with a [list of identifiers](http://www.uniprot.org/uniprot/?query=ADA18_HUMAN+or+ADA19_HUMAN+or+ADA21_HUMAN+or+ADA22_HUMAN+or+ADA23_HUMAN&sort=score)).

Then click on "Download" and choose to download the results in [GFF format](http://biowiki.org/GffFormat).  
  
You can modify the GFF file as follows:

Keep only the lines containing your domain/region, (e.g. "Disintegrin", "Cytoplasmic" or "Transit") and ignore all other lines (e.g. using grep). These lines include information about extent of the domains/regions.

Transform the relevant lines (e.g. using a scripting language, or a word processor) from

Q9R158 UniProtKB Domain 392 478 . . . Note=Disintegrin
Q10741 UniProtKB Domain 457 551 . . . Note=Disintegrin
O14672 UniProtKB Domain 457 551 . . . Note=Disintegrin

to

Q9R158\[392-478\]
Q10741\[457-551\]
O14672\[457-551\]

and ignore all other lines.

You will then be able to use the ["Retrieve/ID mapping"](http://www.uniprot.org/uploadlists) service to upload the file you obtained from modifying the GFF, and retrieve the corresponding entries. To download the subsequences, select the format "FASTA (source list)" from the download menu.

If you only have a short list of entries, you can also select the domains manually from the entry views by clicking on "Add to basket" at the right hand side of the feature descriptions in the section "Family and domains" of these entries. When you have finished selecting your domains, open the [basket](http://www.uniprot.org/help/basket) and click on "Download".
        