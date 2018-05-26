%.png:	%.pdf
	convert -density 300 $*.pdf $*.svg

PDFs := $(wildcard *.pdf)
TMPs += $(PDFs:%.pdf=%.png)
