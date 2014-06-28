# asg

asciidoc site generator

## usage

        asg <config> [-o <dir>] [--watch]

### config.yaml

describes the site

         ---
         layouts: [<dir>...]
         content: [<dir>|<file>...]


## process

There are two types of generated documents: Content documents and
template documents. Content documents are generated from source
documents, written in Markdown or Asciidoc. The Markdown documents
have a YAML header, the Asciidoc documents may or may not. It is also
possible to set metadata for a particular content document in the
configuration file.

Template documents are documents that don't have a specific source
document, but are generated into some kind of aggregate document. This
could be things like the frontpage, an article archive or the Atom
feed.

Layouts consist of templates that include other partial templates to
describe how to generate the final document.

There are couple of magic layouts:

* `layouts/_default.html`

  This document is used to generate all pages by default. Documents
  can specify a different layout to be used using the front matter.


Processing has to be done in two steps: First read all the documents
and their metadata and organize them into a big hierarchy, then
process the templates for all source documents (ends with .md or
.txt), then process all meta documents (ends with .html or .xml).

## front matter

  * `title`
  * `date`
  * `slug`
    for source document content/<category>/<page>.txt, replace <page>
  * `url`
    desired destination url (if it ends with /, automatically gen /index.html)
  * `layout`
  * `author`
  * `email`
  * `category`
  * `tags`


## variables

These variables are available to templates

  * site -- container with site-wide attributes
  * site.title
  * site.lang -- language code for site
  * site.charset -- charset encoding of content on site
  * site.url -- root url for site
  * site.author -- author of site
  * site.email -- email of site author
  * site.description -- description of site
  * site.uuid -- identifier used for atom feeds
  * site.favicon
  * site.feedurl
  * site.feedtype -- application/atom+xml
  * newest -- reference to the page with the most recent date
  * pages -- list of all pages
  * stylesheets -- list of all stylesheets available for site
  * categories -- dict of lists of pages for each category
    (a subfolder is an automatic category)
  * tags -- dict of lists of pages for each tag
  * page.title
  * page.author
  * page.email
  * page.date
  * page.uuid
  * page.url
  * page.content

