%.pdf:	%.gpt
	(echo "set terminal cairolatex eps; set output \"/tmp/$*.tex\"" | cat - $*.gpt) | gnuplot
	latex -halt-on-error -output-directory /tmp -jobname $* << EOF \
\\documentclass{minimal} \
\\usepackage{graphicx} \
\\usepackage{amsmath} \
\\usepackage{amssymb} \
\\begin{document} \
\\pagestyle{empty} \
\\thispagestyle{empty} \
\\resizebox{1.0\\textwidth}{!}{\\input{/tmp/$*}} \
\\end{document} \
EOF 
	dvips /tmp/$*.dvi -o /tmp/$*.ps
	ps2eps --loose < /tmp/$*.ps > /tmp/$*.eps
	epstopdf /tmp/$*.eps
	mv /tmp/$*.pdf $*.pdf
