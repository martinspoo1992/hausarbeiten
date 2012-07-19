LATEX=latex
PDFLATEX=pdflatex
BIBTEX=bibtex
TARGET=synoptischer_vergleich_ss2012
TEXSRC=$(TARGET).tex declaration.tex introduction.tex title.tex
PICTURES=
BIBSRC=

.PHONY:	all clean pdf dvi

all:	dvi pdf

clean:
	-rm -f *.aux *.bbl *.blg *.log *.out *.toc
	-rm -f *.dvi *.pdf

dvi:	$(TARGET).dvi

pdf:	$(TARGET).pdf

$(TARGET).pdf:	$(TARGET).dvi $(PICTURES:.eps=.pdf)
	$(PDFLATEX) $(TARGET)
#	$(BIBTEX) $(TARGET)
	$(PDFLATEX) $(TARGET).tex
	$(PDFLATEX) $(TARGET).tex

$(TARGET).dvi:	$(TEXSRC) $(BIBSRC) $(PICTURES)
	$(LATEX) $(TARGET).tex
#	$(BIBTEX) $(TARGET)
	$(LATEX) $(TARGET).tex
	$(LATEX) $(TARGET).tex
