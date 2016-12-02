#STYLE-PATH= ${HOME}/.LaTex/
STYLE-PATH= ${HOME}/Library/tex/texmf/latex/


SOURCE= 00-Organisatorisches-include.tex \
        01a-sprache-sprachwissenschaft-include.tex\
        01b-sprache-sprachwissenschaft-include.tex\
        02-phonetik-include.tex\
	03a-phonologie-include.tex\
	03b-phonologie-include.tex\
	04a-graphematik-include.tex\
	05a-wortbildung-include.tex\
	05b-flexion-include.tex\
	06a-syntax-stefan-include.tex



check: germanisch-check-2x2.pdf

%.pdf: %.tex $(SOURCE) 
	xelatex $*
	bibtex $*
	xelatex $* 
	bibtex $*
	xelatex $* 

# 03bPhonologie-handout.dvi: $(SOURCE2)
# 	latex 03bPhonologie-handout
# 	latex 03bPhonologie-handout
# 	bibtex 03bPhonologie-handout
# 	latex 03bPhonologie-handout 
# 	bibtex 03bPhonologie-handout
# 	latex 03bPhonologie-handout 

# 03bPhonologie-slides.dvi: $(SOURCE2)
# 	latex 03bPhonologie-slides
# 	latex 03bPhonologie-slides
# 	bibtex 03bPhonologie-slides
# 	latex 03bPhonologie-slides 
# 	bibtex 03bPhonologie-slides
# 	latex 03bPhonologie-slides 


03b-phonologie-handout-2x2.pdf: 03b-phonologie-handout.pdf
	beamer2handout $?


silben: 03b-phonologie-handout-2x2.pdf

silben-slides: 03b-phonologie-slides.pdf
silben-handout: 03b-phonologie-handout-2x2.pdf

slides: grundkurs-slides.pdf
handout: grundkurs-handout-2x2.pdf


grundkurs-handout-2x2.pdf: grundkurs-handout.pdf
	beamer2handout $?


o-public: grundkurs-handout-2x2.pdf
	scp -p $? home.hpsg.fu-berlin.de:/home/stefan/public_html/PS/



clean:
	find . -name \*\.bak -exec \rm {} \;
	find . -name \*~ -exec \rm {} \;
	rm -f *.bak *.toc *.bbl *.blg *~ *.log *.aux *.*pk *.cut *.tmp *.out *.nav *.snm


realclean: clean
	rm -f *.dvi *.ps *.pdf


