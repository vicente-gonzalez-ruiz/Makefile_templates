# .tex -> .eps
%.eps: %.tex
	echo -e "Default \e[92mCompiling $*\e[0m"
	latex $*
	dvips $*.dvi
	ps2eps --loose < $*.ps > $*.eps
	rm $*.ps
	rm $*.dvi
	rm $*.aux
	rm $*.log
