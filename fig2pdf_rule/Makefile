%.pdf: %.fig
	fig2dev -L pdftex $*.fig > /tmp/$*.pdf
	fig2dev -L pdftex_t -f sf -p /tmp/$*.pdf $< > /tmp/$*.tex
	pdflatex  -halt-on-error -output-directory /tmp -jobname $*_raw << EOF \
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
\\input{/tmp/$*} \
\\end{document} \
EOF
	pdfcrop /tmp/$*_raw.pdf /tmp/$*_crop.pdf
	#dvips /tmp/$*.dvi -o /tmp/$*.ps
	#ps2eps --loose < /tmp/$*.ps > /tmp/$*.eps
	#epstopdf /tmp/$*.eps
	mv /tmp/$*_crop.pdf $*.pdf
