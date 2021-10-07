# uniprot-manual

UniProt help pages uses GitHub wiki ([here](https://github.com/ebi-uniprot/uniprot-manual/wiki))
Once a page has been added/updated, they should be available through the [help section](https://beta.uniprot.org/help) of the website within a few minutes.

## Adding a new page
There is a "New Page" button at the top right of the wiki homepage https://github.com/ebi-uniprot/uniprot-manual/wiki
1. Click the "New page" button
2. Give your page a title. This title won't be displayed but will be what appears in the url for the help article (eg )
3. Paste the meta-data snippet below at the top of your page.
```
---
title:
categories:
---
```
4. The `title:` will be the title displayed on the page in the help centre.
5. `categories:` is a list of categories, or tags, which are used to filter the data in the help centre. It is comma separated. (e.g. `categories: Entry_information,manual`)
6. You can then write the page content underneath the meta-data snippet using markdown (see [here](https://guides.github.com/features/mastering-markdown/) for a guide).

## Adding an image
1. Head over to [the images directory](https://github.com/ebi-uniprot/uniprot-manual/tree/main/images)
2. You can drag and drop the image you would like to upload
3. Once the image has finished uploading, copy its url (right click>copy link address)
4. You can then add that image to your article using [markdown syntax](https://guides.github.com/features/mastering-markdown/).

## Editing categories
Categories are used to group help articles, and are used to define filters in the search user interface. They are part of the meta-data snippet at the top of every page. Before adding or editing a category, check the syntax by looking at another article from the same category.
