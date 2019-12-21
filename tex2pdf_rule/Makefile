%.pdf: %.tex
	@echo -e "\e[92mCompiling $*.tex\e[0m"
	pdflatex -halt-on-error -output-directory /tmp -jobname $*_raw $*
	pdfcrop /tmp/$*_raw.pdf $*.pdf >> /tmp/$*.log
	rm /tmp/$*_raw.pdf
	rm /tmp/$*_raw.aux
	rm /tmp/$*_raw.log

#TEXs := $(wildcard *.tex)

#TMPs += $(TEXs:%.tex=%.pdf)
