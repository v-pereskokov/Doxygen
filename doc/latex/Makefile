all: refman.pdf

pdf: refman.pdf

refman.pdf: clean refman.tex
	/usr/local/texlive/2016/bin/x86_64-darwin/pdflatex refman
	/usr/local/texlive/2016/bin/x86_64-darwin/makeindex refman.idx
	/usr/local/texlive/2016/bin/x86_64-darwin/pdflatex refman
	latex_count=8 ; \
	while egrep -s 'Rerun (LaTeX|to get cross-references right)' refman.log && [ $$latex_count -gt 0 ] ;\
	    do \
	      echo "Rerunning latex...." ;\
	      /usr/local/texlive/2016/bin/x86_64-darwin/pdflatex refman ;\
	      latex_count=`expr $$latex_count - 1` ;\
	    done
	/usr/local/texlive/2016/bin/x86_64-darwin/makeindex refman.idx
	/usr/local/texlive/2016/bin/x86_64-darwin/pdflatex refman


clean:
	rm -f *.ps *.dvi *.aux *.toc *.idx *.ind *.ilg *.log *.out *.brf *.blg *.bbl refman.pdf
