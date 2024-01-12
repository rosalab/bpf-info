# BPF Info 

A static site serving as our internal documentation for BPF and ROSA projects.

## Adding to this site
There are two ways to add content to the site: you can either modify existing pages, or create new pages.
To modify an exisitng page, simply add your text to the corresponding markdown file.

Creating a new page is slightly more complicated.
First create your markdown file in the `docs` directory.
Then, if you want your page to be accessible from the global nav bar on the left, add an entry in `mkdocs.yml` that looks like:

```
nav:
...     # These are the other entires
 - Page Name: pagefile.md
...
```



## MkDocs Command Reference

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
