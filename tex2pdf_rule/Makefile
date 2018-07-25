%.pdf: %.tex
	echo -e "Default \e[92mCompiling $*\e[0m"
	pdflatex -jobname $*_ $*
	pdfcrop $*_.pdf $*.pdf
	rm $*_.pdf
	rm $*_.aux
	rm $*_.log

#TEXs := $(wildcard *.tex)

#TMPs += $(TEXs:%.tex=%.pdf)
