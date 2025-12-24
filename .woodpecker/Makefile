authorarchive.zip: ../* ../examples/*.tex
	rm -rf authorarchive 
	mkdir -p authorarchive/examples
	(cd ../examples; for i in *.tex; do pdflatex $$i; pdflatex $$i; pdflatex $$i; done)
	cp ../examples/*.tex authorarchive/examples/
	cp ../examples/*.pdf authorarchive/examples/
	cp ../examples/*.config authorarchive/examples/
	cp -r ../examples/bib authorarchive/examples/
	cp ../*.sty authorarchive
	cp ../LICENSE authorarchive
	cp ../*.md authorarchive
	chmod -R go+u-w authorarchive
	zip -r authorarchive.zip authorarchive
	rm -rf authorarchive 

