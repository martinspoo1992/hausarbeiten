LATEX=latex
PDFLATEX=pdflatex
BIBTEX=bibtex
TARGET=sachunterricht
TEXSRC=$(TARGET).tex aufgaben.tex declaration.tex experiment.tex introduction.tex perspektivrahmen.tex reflection.tex title.tex
PICTURES=
BIBSRC=$(TARGET).bib

.PHONY:	all clean pdf dvi

all:	dvi pdf

clean:
	-rm -f *.aux *.bbl *.blg *.log *.out *.toc
	-rm -f *.dvi *.pdf

dvi:	$(TARGET).dvi

pdf:	$(TARGET).pdf

$(TARGET).pdf:	$(TEXSRC) $(BIBSRC) $(PICTURES:.eps=.pdf)
	$(PDFLATEX) $(TARGET)
	$(BIBTEX) $(TARGET)
	$(PDFLATEX) $(TARGET).tex
	$(PDFLATEX) $(TARGET).tex

$(TARGET).dvi:	$(TEXSRC) $(BIBSRC) $(PICTURES)
	$(LATEX) $(TARGET).tex
	$(BIBTEX) $(TARGET)
	$(LATEX) $(TARGET).tex
	$(LATEX) $(TARGET).tex
