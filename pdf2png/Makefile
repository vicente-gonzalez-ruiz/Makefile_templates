%.png:	%.pdf
	convert -density 300 $*.pdf $*.png

PDFs := $(wildcard *.pdf)
TMPs += $(PDFs:%.pdf=%.png)
