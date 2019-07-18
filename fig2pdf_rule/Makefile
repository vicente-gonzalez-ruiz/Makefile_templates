%.pdf: %.fig
	fig2dev -L pstex $*.fig > $*_fig2dev.eps
	fig2dev -L pstex_t -f sf -p $*_fig2dev.eps $< > $*_fig2dev.tex
	latex  -halt-on-error -output-directory /tmp -jobname $* << EOF \
\\documentclass[portrait,a2,final]{a0poster} \
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
\\input{$*_fig2dev} \
\\end{document} \
EOF
	dvips /tmp/$*.dvi -o /tmp/$*.ps
	ps2eps --loose < /tmp/$*.ps > /tmp/$*.eps
	epstopdf /tmp/$*.eps
	mv /tmp/$*.pdf $*.pdf
