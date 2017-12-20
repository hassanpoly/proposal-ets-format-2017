main = polymtl_presentation

#texfiles = $(shell ls sections/*.tex)
bakfiles = $(addsuffix .bak, $(texfiles))

all: draft

draft:
	pdflatex -shell-escape $(main).tex
	bibtex $(main).aux
	pdflatex -shell-escape $(main).tex
	pdflatex -shell-escape $(main).tex

final:
	for f in $(texfiles); do aspell -t -p./$(main).dict -c $$f; done
	pdflatex -shell-escape $(main).tex
	bibtex $(main).aux
	pdflatex -shell-escape $(main).tex
	pdflatex -shell-escape $(main).tex
