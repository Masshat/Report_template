TEX=root
FIG=echeancier.fig

$(TEX).pdf: $(TEX).tex figpdf
	pdflatex $(TEX)
	pdflatex $(TEX)
	evince $(TEX).pdf

figeps:;for i in $(FIG);do $(MAKE) epspdf/`echo $$i|sed 's|....$$||'`.eps; done
figpdf:;for i in $(FIG);do $(MAKE) epspdf/`echo $$i|sed 's|....$$||'`.pdf; done
epspdf/%.eps : %.fig ; fig2dev -L eps $< > $@
epspdf/%.eps : %.dia ; dia --nosplash --export=$@ $< 
epspdf/%.eps : %.gif ; convert $< $@
epspdf/%.pdf : epspdf/%.eps ; epstopdf $<

clean:
	rm $(TEX).aux $(TEX).log $(TEX).nav $(TEX).out $(TEX).pdf $(TEX).snm
