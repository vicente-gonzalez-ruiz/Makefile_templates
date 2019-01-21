%.pdf: %.fig
	fig2dev -L pdftex $*.fig > $*_tmp.pdf
	fig2dev -L pdftex_t -f sf -p $*_tmp.pdf $< > $*.tex
	pdflatex -jobname $* << EOF \
\\documentclass[portrait,a3,final]{a0poster} \
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
\\input{$*} \
\\end{document} \
EOF
	#mv a0poster.pdf $*.pdf
	rm $*_tmp.pdf
	rm $*.tex
	rm $*.aux
	rm $*.log
	#mv a0poster.dvi $*.dvi
	#dvips $*.dvi -o $*.ps
	#ps2eps --loose < $*.ps > /tmp/$*.eps
	#epstopdf /tmp/$*.eps
	#mv /tmp/$*.pdf $*.pdf
	#rm $*.ps
	#rm tmp.eps
	#rm $*.dvi
	#rm $*.eps
	#rm tmp.tex
	#rm a0poster.aux
	#rm a0poster.log
	#rm a0header.ps

# Original files
#FIGs := $(wildcard *.fig)

# Temporal files
#TMPs += $(FIGs:%.fig=%.pdf)
