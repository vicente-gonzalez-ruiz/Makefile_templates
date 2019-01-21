## .fig -> .eps
%.eps: %.fig
	fig2dev -L pstex $*.fig > $*.eps
	fig2dev -L pstex_t -f sf -p $*.eps $< > $*.tex
	latex -jobname $* << EOF \
\\documentclass{article} \
\\usepackage{epsfig} \
\\usepackage{amsmath} \
\\usepackage{amssymb} \
\\usepackage{color} \
\\input{local_packages} \
\\begin{document} \
\\sffamily \
\\def\\normalfont{\\sffamily} \
\\renewcommand{\\familydefault}{cmss} \
\\pagestyle{empty} \
\\thispagestyle{empty} \
\\resizebox{1.0\\textwidth}{!}{\\input{$*}} \
\\end{document} \
EOF
	dvips $*.dvi
	ps2eps --loose < $*.ps > $*.eps
	rm $*.ps
	rm $*.dvi
	rm $*.tex
	rm $*.aux
	rm $*.log

