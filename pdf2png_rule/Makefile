%.png:	%.pdf
	@echo -e "\e[92mCompiling $*.png\e[0m"
#	convert -density 300 $*.pdf $*.png
	gs -dNOPAUSE -dBATCH -sDEVICE=png16m -r300 -sOutputFile=$*.png $*.pdf > /tmp/$*.log
