PDF=transparencias.pdf
LATEXMK_FLAGS=-r latexmkrc.pl -pdf
FIGURES=cc-by-sa.pdf
.PHONY: all install preview clean

$(PDF): $(FIGURES)

all: $(PDF)

install:
	sudo apt-get install latexmk texlive-common inkscape

%.pdf: %.tex
	latexmk $(LATEXMK_FLAGS) $<

%.pdf: %.svg
	inkscape -A $@ $<

preview: $(subst .pdf,.tex,$(PDF))
	latexmk $(LATEXMK_FLAGS) -pvc $<

clean:
	latexmk -C -pdf $<
	$(RM) $(FIGURES) $(PDF) *.synctex.gz cmd.tex
