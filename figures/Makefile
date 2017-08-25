ROOTDIR=$(realpath .)
TMPDIR=$(ROOTDIR)/.tmp
PDFLATEXFLAGS=-interaction=nonstopmode -output-directory=$(TMPDIR)

all: figures

figures: applifecycle.svg

applifecycle.svg: applifecycle.tex
	mkdir -p $(TMPDIR)
	pdflatex $(PDFLATEXFLAGS) $<
	pdf2svg $(TMPDIR)/applifecycle.pdf $@

clean:
	rm -rf $(TMPDIR) applifecycle.pdf

.PHONY: all figures applifecycle.svg clean
