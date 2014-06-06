#!gmake

# add the required target .tex files below
SRC  =
SRC += thesis.tex

default:	thesis.dvi

thesis.dvi:	thesis.tex
thesis.dvi:	database.bib

.SUFFIXES:
.SUFFIXES: .pdf .eps .ps .dvi .tex .slitex

DVI_TARGET = $(SRC:.tex=.dvi) $(SRC:.slitex=.dvi)
PS_TARGET  = $(SRC:.tex=.ps) $(SRC:.slitex=.ps)
PDF_TARGET = $(SRC:.tex=.pdf) $(SRC:.slitex=.pdf)

all:	$(DVI_TARGET)

ps:	$(PS_TARGET)

pdf:	$(PDF_TARGET)

clean:
	-rm -f *.aux *.bbl *.blg *.log *.toc *.lof *.lot *.glo *.idx

# DVI_TARGET, PS_TARGET, PDF_TARGET are wrong!!!, don't realclean for instance
realclean:      clean
	-rm -f *.bak *.dvi

# while [ "x`grep Rerun $${logfile}`" != "x" ] ; \
#   the above one may not work sometimes
# while [ "x`grep 'undefined references' $${logfile}`" != "x" ] ; \
#   this one always works but may cause deadlock if there are undefined label

.slitex.dvi:
	slitex $<
	echo make $*.dvi done!

.tex.dvi:
	latex $<
	# bibtex plus "et al. correction" for some bibliography style
	# the minus sign avoids error stopping when no citation encountered
	-bibtex $*
	-sed 's/and {\\it et al\.}/{\\it et al.}/' $*.bbl > $*.tmp
	-mv $*.tmp $*.bbl
	# latex several rounds until no dangling reference
	-logfile=$*.log; \
	while [ "x`egrep 'undefined references|Rerun' $${logfile}`" != "x" ]; \
		do latex $<; \
	done
	echo make $*.dvi done!

.dvi.ps:
	dvips -D 600 $<
	@echo make $*.ps done!

.dvi.eps:
	dvips -E -D 600 $<
	mv $*.ps $*.eps
	@echo make $*.eps done!

.ps.pdf:
	/usr/local/gs/bin/ps2pdf $<
	@echo make $*.pdf done!

