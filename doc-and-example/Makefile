html_include_dir=html-build
epub_include_dir=epub-build
source=chapters/*.md
title='Single Source eDocs Documentation and Example'
filename='doc-and-example'


all: html epub rtf pdf

markdown:
	awk 'FNR==1{print ""}{print}' $(source) > $(filename).md

html: markdown
	pandoc -s $(filename).md -t html5 -o index.html -c $(html_include_dir)/style.css \
		--include-in-header $(html_include_dir)/head.html \
		--include-before-body $(html_include_dir)/include-before.html \
		--include-after-body $(html_include_dir)/include-after.html \
		--title-prefix $(title) \
		--normalize \
		--smart \
		--toc

epub: markdown
	pandoc -s $(filename).md --normalize --smart -t epub -o $(filename).epub \
		--epub-metadata $(epub_include_dir)/metadata.xml \
		--epub-stylesheet $(epub_include_dir)/epub.css \
		--epub-cover-image img/cover.jpg \
		--title-prefix $(title) \
		--normalize \
		--smart \
		--toc

rtf: markdown
	pandoc -s $(filename).md -o $(filename).rtf \
		--title-prefix $(title) \
		--normalize \
		--smart

pdf: markdown
	# You need `pdflatex`
	# OS X: http://www.tug.org/mactex/
	# Then find its path: find /usr/ -name "pdflatex"
	# Then symlink it: ln -s /path/to/pdflatex /usr/local/bin
	pandoc -s $(filename).md -o $(filename).pdf \
		--title-prefix $(title) \
		--normalize \
		--smart \
		--toc \
		--latex-engine=`which xelatex` 

#mobi: epub
	# Download: http://www.amazon.com/gp/feature.html?ie=UTF8&docId=1000765211
	# Symlink bin: ln -s /path/to/kindlegen /usr/local/bin
	#kindlegen $(filename).epub
