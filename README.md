# Single Source Publishing Example for HTML, ePub, RTF, PDF, and Mobi Formats

## About

This is an example set-up for generating multiple output formats, most notably ePub, from a single input format. It's based on software authoring tools and using a command line interface (cli) so will likely be a bad fit unless you have familiarity with these tools.

Specifics are:
* Input file format is Markdown
* Output formats are HTML, ePub, RTF, PDF, and Mobi
* Multiple input files are supported, so large writing projects can be broken into logical segments (e.g. chapters or sections)

This example is entirely based on the set-up used by [Addy Osmani](http://addyosmani.com) for his book [Developing Backbone.js Applications](http://addyosmani.github.io/backbone-fundamentals/).

## Building

The output files are generated with the command `make` or `make -f Makefile`. This will create the HTML, ePub, Mobi, PDF and RTF versions of your input file(s). 

### Dependencies

* Make
* [Pandoc](https://github.com/jgm/pandoc)
* pdflatex (and recommended latex fonts)
