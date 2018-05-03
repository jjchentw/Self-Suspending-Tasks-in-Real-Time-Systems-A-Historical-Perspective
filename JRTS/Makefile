MAKE = make

.PHONY: all clean diff


MAIN = JRTS

ALL = ${MAIN}.pdf

all: ${ALL}


TEX  := $(shell find ..   -name '*.tex')

%.pdf: ${TEX}
	latexmk -interaction=nonstopmode -f -pdf $*.tex

EXTS  = *~ *.aux *.backup *.blg *.log *.out *.lof *.loa *.lot *.toc *.bbl *.bak *.texshop *.dvi *.fdb_latexmk
TRASH := $(foreach ext,${EXTS},$(shell find . -name '${ext}'))

clean:
	@echo Cleaning  ${EXTS} ${ALL}...
	@rm -f ${TRASH} ${ALL}

#COMPARE_TO ?= HEAD
#COMPARE_TO = d8a396c
#COMPARE_TO = d1b3e65
#COMPARE_TO = 74289f2
#COMPARE_TO = ef21781
#COMPARE_TO = 13eb11a
COMPARE_TO = 3bd267b

diff:
	 git latexdiff  --ignore-latex-errors --whole-tree --main ${MAIN}.tex --latexmk  -o diff-to-${COMPARE_TO}.pdf ${COMPARE_TO} --latexopt --force --latexopt --shell-escape --exclude-textcmd=section --exclude-textcmd=subsection --exclude-textcmd=subsubsection --no-cleanup
