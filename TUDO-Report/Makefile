
MainFile    = report2
MainTeXFile = $(MainFile).tex
PDFFile     = $(MainTeXFile:%.tex=%.pdf)

TeX_Files = $(MainTeXFile) \
            content/*.tex

.PHONY: all clean pdf

all: pdf

pdf: $(TeX_Files)
	pdflatex $(MainTeXFile)
	bibtex   $(MainFile)
	pdflatex $(MainTeXFile)
	pdflatex $(MainTeXFile)


clean:
	rm -f $(PDFFile)
	rm -f *.aux *.log *.bbl *.blg
