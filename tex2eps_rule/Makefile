# .tex -> .eps
%.eps: %.tex
	latex $*
	dvips $*.dvi
	ps2eps --loose < $*.ps > $*.eps
	rm $*.ps
	rm $*.dvi
	rm $*.aux
	rm $*.log
