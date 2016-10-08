

TEX := $(shell find . -name '*.tex')
PDF = $(patsubst %.tex,%.pdf,$(TEX))

.PHONY: all clean

all: $(PDF)
	
# generate PDF
%.pdf: %.tex
	FILE=$(notdir $*)
	cd $(dir $*); \
	latexmk -pdf -pdflatex="pdflatex --shell-escape -halt-on-error %O %S" $(notdir $*); \
	rm -f *.aux *.end *.fls *.log *.out *.fdb_latexmk *.bbl *.bcf *.blg *-blx.aux *-blx.bib *.brf *.run.xml
	@echo $*

clean:
	latexmk -C
	rm -f *.pdfsync
	rm -rf *~ *.tmp
	rm -f $(PDF) *.aux *.end *.fls *.log *.out *.fdb_latexmk *.bbl *.bcf *.blg *-blx.aux *-blx.bib *.brf *.run.xml

#  Delete any intermediates and end files upon an error
.DELETE_ON_ERROR: 
