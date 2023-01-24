.PHONY: main clean help


# .tex --> .pdf via latexmk. 
%.pdf: %.tex references.bib
	latexmk -pdf -g $<


main: main.pdf 

clean:
	latexmk -c

help:
	@echo "usage:"
	@echo "  make: build or update main.pdf"
	@echo "  make -B: rebuild main.pdf from scratch"
	@echo "  make clean: remove auxiliary LaTeX files (*.aux, *.log, etc.)"
	@echo "  make help: see this message and exit"
