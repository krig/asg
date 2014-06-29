# asg

a site generator

## usage

    asg
    
    Usage:
      asg [-v] [--output=<dir>]
          [--serve|--watch] [--port=<port>]
          [<config>]
    
    Options:
      -h --help          Show this screen.
      --version          Show version.
      -v --verbose       Print debug output.
      -o --output=<dir>  Output directory [default: output/].
      -s --serve         Launch server.
      -w --watch         Launch server, watch content for changes.
      -p --port=<port>   Server port [default: 4763].

## config

See demo.

## TODO

* --watch doesn't work

* metadata override in config file

* URL building / escaping is broken

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

