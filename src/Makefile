TEX = uplatex
DVI = dvipdfmx
sources   = $(wildcard *.tex)
artifacts = $(basename $(sources))

.PHONY: clean pdf view
.PRECIOUS : %.pdf

build: $(artifacts)

pdf: $(artifacts)

view: build
	open $(addsuffix .pdf,$(artifacts))

%.dvi: %.tex
	$(TEX) $<
	$(TEX) $<
	$(TEX) $<

%.pdf: %.dvi
	$(DVI) $<

%: %.pdf
	-$(RM) $@.aux
	-$(RM) $@.log
	-$(RM) $@.ttt

clean:
	$(RM) *.pdf *.dvi *.aux *.log *.ttt
