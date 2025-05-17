BIN := bin

presentation: presentation.tex
	latexmk \
		-synctex=1 \
		-interaction=nonstopmode \
		-pdf \
		-outdir=${BIN} \
		$<

.PHONY: clean presentation

clean:
	rm -r ${BIN}/*
