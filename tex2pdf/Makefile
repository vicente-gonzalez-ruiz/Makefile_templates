%.pdf: %.tex
	pdflatex -jobname $*_ << EOF \
\\documentclass{article} \
\\usepackage[a3paper]{geometry} \
\\usepackage{amsmath} \
\\usepackage{amssymb} \
\\usepackage{color} \
\\usepackage{graphicx} \
\\graphicspath{{../FIGs/}} \
\\DeclareGraphicsExtensions{.pdf} \
\\begin{document} \
\\sffamily \
\\def\\normalfont{\\sffamily} \
\\renewcommand{\\familydefault}{cmss} \
\\pagestyle{empty} \
\\thispagestyle{empty} \
\\resizebox{1.0\\textwidth}{!}{\\input{$*}} \
\\end{document} \
EOF
	pdfcrop $*_.pdf $*.pdf
	rm $*_.pdf
	rm $*_.aux
	rm $*_.log

TEXs := $(wildcard *.tex)

TMPs += $(TEXs:%.tex=%.pdf)
