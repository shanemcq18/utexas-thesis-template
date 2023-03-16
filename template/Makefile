.PHONY: clean help


main.pdf: *.tex utdiss.sty references.bib
	latexmk -pdf -g main.tex

clean:
	latexmk -c -quiet

help:
	@echo "usage:"
	@echo "  make: build or update main.pdf"
	@echo "  make -B: rebuild main.pdf from scratch"
	@echo "  make clean: remove auxiliary LaTeX files (*.aux, *.log, etc.)"
	@echo "  make help: see this message and exit"
