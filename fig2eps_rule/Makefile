#No rula
%.eps: %.fig
	@echo -e "\e[92mCompiling $*.fig\e[0m"
	fig2dev -L epstex $*.fig > /tmp/$*.eps
	fig2dev -L epstex_t -f sf -p /tmp/$*.eps $< > /tmp/$*.tex
	pdflatex  -halt-on-error -output-directory /tmp -jobname $*_raw << EOF \
\\documentclass[portrait,a0,final]{a0poster} \
\\usepackage{epsfig} \
\\usepackage{amsmath} \
\\usepackage{amssymb} \
\\usepackage{color} \
\\begin{document} \
\\sffamily \
\\def\\normalfont{\\sffamily} \
\\renewcommand{\\familydefault}{cmss} \
\\pagestyle{empty} \
\\thispagestyle{empty} \
\\input{/tmp/$*} \
\\end{document} \
EOF > /tmp/$*_raw.log
#	pdfcrop /tmp/$*_raw.pdf /tmp/$*_crop.pdf >> /tmp/$*_raw.log
#	mv /tmp/$*_crop.pdf $*.pdf
