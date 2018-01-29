default:	all
.PHONY:		clean

%.svg:	%.pdf
	pdf2svg $*.pdf $*.svg

PDFs := $(wildcard *.pdf)
TMPs += $(PDFs:%.pdf=%.svg)

all:	$(TMPs)

clean:
	rm -f $(TMPs)
