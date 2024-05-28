name = Ahmed Shuaib - Platformata - Game Design with automata theory
file = main.tex
slide = slides.md
svgs = level_1.svg level_2.svg level_3.svg level_4.svg

make:
	xelatex $(file) -interaction=batchmode 

pdflatex:
	pdflatex --shell-escape $(file)

marp:
	marp $(slide) --pdf --allow-local-files

dist:
	pdflatex --shell-escape $(file)
	marp $(slide) --pdf --allow-local-files
	mkdir -p ../dist
	cp main.pdf  "../dist/$(name).pdf"
	cp slides.pdf  "../dist/$(name) - slides.pdf"
	cp $(svgs) ../dist
	tar czf ../Platformata.tar.gz ../dist/*
	mv ../Platformata.tar.gz dist

.SILENT: clean
clean:
	rm *.log *.aux *.pdf
	rm -r svg-inkscape
