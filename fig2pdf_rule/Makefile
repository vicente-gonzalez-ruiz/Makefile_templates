%.pdf: %.fig
	fig2dev -L pdftex $*.fig > $*_fig2dev.pdf
	fig2dev -L pdftex_t -f sf -p $*_fig2dev.pdf $< > $*_fig2dev.tex
	pdflatex -jobname $*_tmp << EOF \
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
	#mv a0poster.pdf $*.pdf
	pdfcrop $*_tmp.pdf $*.pdf
	rm $*_fig2dev.pdf
	rm $*_fig2dev.tex
	rm $*_tmp.pdf
	rm $*_tmp.aux
	rm $*_tmp.log
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
