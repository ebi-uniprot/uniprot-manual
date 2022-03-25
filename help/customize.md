---
title: Customize display options
categories: Website,Text_search,Technical,help
---

Searches in the Protein Knowledgebase (UniProtKB) display results in a tabular format.  
You can configure which columns are shown in the result table, and have your selection reflected in the **download** of your data in form of a tab-separated file. You can also use the resulting URL [programmatically](https://www.uniprot.org/help/api).

When you click on "Columns", or on the pencil icon at the far left of your result table header, you will obtain a screen containing two sections:

1.  **Columns to be displayed**  
    shows your current selection (or the default columns if you have not yet configured anything). You can drag and drop the text elements to change the column order, and remove columns by clicking on the "x". There is also a link to reset to the default settings.
2.  **Add more columns**  
    lists all available columns, grouped in the same way as the corresponding data is grouped in the entry view. You can browse through the options, or use the search box to find a column name.

You can add columns by clicking in the relevant checkboxes.  
You can remove columns by unselecting the relevant checkboxes, or by clicking on the "x" under "Columns to be displayed".

Your column selection can be used to produce a **tab-separated output** containing the same set of columns, e.g. for use in a spreadsheet program such as Excel (c): Once you are happy with your table layout, click on "Download" and select one of tab-separated or Excel formats.

These column settings will be stored in a cookie, and applied to all subsequent queries until you change your settings, delete your cookies or use a different computer.

In some cases, e.g. in an ID mapping or batch retrieval result, or if you have bookmarked (or received from a colleague) an URL that specifies column settings different from your own current settings, you may see an additional section **"Unsaved columns"** (in addition to **"Columns to be displayed"** and **"Add more columns"** ).

In case of an ID mapping or batch retrieval result, this allows you to customize your result and decide whether you wish to keep the column containing your submitted identifiers for future result views.

The same applies if you have an URL originating from a previous bookmark or shared by a colleague. Such URLs may contain some information about column settings that differ from your current settings ( [example](https://www.uniprot.org/uniprotkb/?query=database:%28type:hgnc%29&sort=score&columns=id,entry%20name,reviewed,genes,database%28HGNC%29) ), and using the column customization interface allows you to merge the columns specified in the URL with your current settings.

See also:

-   [UniProtKB tutorial/video](https://www.youtube.com/watch?v=ado1r8IDm3U)
-   [UniProtKB column names for programmatic access](https://www.uniprot.org/help/uniprotkb%5Fcolumn%5Fnames)
-   [Customise and share your search results (UniProt blog)](https://insideuniprot.blogspot.com/2015/03)
