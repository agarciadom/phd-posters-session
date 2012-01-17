MAIN=poster-ucase
IMAGES=logo.pdf logo_esi_noshadow.pdf logo_uca.pdf qrcode_web_ucase.pdf
BIB=
.PHONY: all clean review install-packages

all: $(MAIN).pdf

$(MAIN).pdf: $(MAIN).tex $(IMAGES) $(BIB)
	latexmk -pdf $<

%.pdf: %.svg
	inkscape $< -A $@

review: $(IMAGES)
	latexmk -pvc -pdf $(MAIN)

clean:
	latexmk -pdf -C $(MAIN) $(SUMMARY)
	$(RM) *~

install-packages:
	sudo aptitude install inkscape latexmk texlive-latex-extra
