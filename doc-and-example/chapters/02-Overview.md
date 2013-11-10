# Overview

## The Big Picture

The overall file structure is not mandated by any of the tools used to build the formatted output. It exists to make the author's life easier by providing a logical organization for the individual files. The structure can be changed to meet different requirements or organizational tastes.

The sources files live in the chapters directory. For ease of authoring and content management the assumption is there is one chapter in each file, but this is a convention. A chapter could be broken into multiple files or multiple chapters placed in a single file. The files are concatinated in alphabetical order to produce a master document. To allow for useful file naming and maintain ordering, the file names are prefixed with numbers.

The formatted output (ePub, HTML, PDF, RTF) is produced by a utility named Pandoc. Pandoc is the heart of this method. It determines what is and is not valid input, and controls the details of what the output looks like.

Images are stored in a seperate image directory named img. Again, this is by convention and can be changed. An image is only used if it is referenced in an input file.

Files specific to a peticular format such as ePub or HMTL are placed in their own directories, epub-build or html-build, respectively.

The commands to create the output documents are contained within the file named Makefile. A command-line utility named make follows the commands. The output documents are placed in the same directory as the Makefile file. 

## Source File Format

This method uses plain-text files for input. The formatting is specified using a markup syntax. The specific markup syntax is whatever Pandoc understands. At the time of writing this was Markdown and subsets of Textile, reStructuredText, HTML, LaTeX, MediaWiki markup, Haddock markup, OPML, and DocBook.

## Output File Formats

The example Makefile produces HTML, ePub, PDF, and RTF output files. There is also sample code for the Kindle mobi format.
