TARGET = main
VISAK = *.aux *.idx *.log *.toc *.out *.dvi *.bbl *.blg *.synctex.gz *.ilg *.lof *.nlo *.nls

quick: ${TARGET}.tex
	pdflatex ${TARGET}.tex

all: ${TARGET}.tex
	pdflatex ${TARGET}.tex > make.log
	makeindex ${TARGET}.nlo -s nomencl.ist -o ${TARGET}.nls
	bibtex ${TARGET}.aux >> make.log
	pdflatex ${TARGET}.tex > /dev/null
	pdflatex ${TARGET}.tex | grep Warning || true
	cp main.pdf ../thesis.pdf

clean:
	-rm -f ${VISAK}

cleanAll:
	-rm -rf ${VISAK} ${TARGET}.pdf

