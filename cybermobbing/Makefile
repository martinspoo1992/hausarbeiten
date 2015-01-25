LATEX=latex
PDFLATEX=pdflatex
BIBTEX=bibtex
TARGET=cybermobbing
TEXSRC=$(TARGET).tex declaration.tex definition.tex evaluation.tex introduction.tex language.tex similarities.tex speech_act.tex
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
