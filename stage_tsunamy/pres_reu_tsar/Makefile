
.PHONY : slides.tex
all : slides.tex
	pdflatex $<
	pdflatex $<
	rm slides.log slides.aux slides.nav slides.out slides.snm slides.toc
	evince slides.pdf&

