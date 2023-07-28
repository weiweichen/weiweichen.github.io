PROJECT = curriculum_vitae
#PROJECTWEB = curriculum_vitae_web

ALL	=	$(PROJECT).pdf

# --- environment --------------------------------------------------------

TEXINPUTS =	TEXINPUTS=.:MACROS:

TEXENV	=	$(TEXINPUTS)

# --- commands -----------------------------------------------------------

FIGPS	=	fig2dev -L ps
PRN2EPS	=	PATH=bin:$$PATH prn2eps
LATEX	=	latex
BIBTEX	=	bibtex
DVIPS	=	dvips -Z -D 600 -t letter -Ppdf
PS2PDF	=	ps2pdf -dEmbedAllFonts=true -dPDFSETTINGS=/printer -dSubsetFonts=true
PSSEL	=	psselect
TAR	=	gtar cvzf
RM	=	rm -f
MV	=	mv -f
MAKEIDX	=	makeindex
GV	=	ghostview
CHMOD	=	chmod -f
CHGRP	=	chgrp -f
ECHO	=	echo
GREP	=	grep
WC	=	wc
CD	=	cd
CAT	=	cat
XLESS	=	xless
SPELL	=	nspell -t
SORT	=	sort -f
CP	=	cp
DISTILL =       GS_OPTIONS="-dAutoFilterColorImages=false \
                            -dColorImageFilter=/FlateEncode" ps2pdf14
THUMBPDF=       thumbpdf --modes=dvips

all:
	$(LATEX) $(PROJECT).tex 
#	$(BIBTEX) $(PROJECT)
	$(LATEX) $(PROJECT).tex 
	$(LATEX) $(PROJECT).tex 
	$(DVIPS) $(PROJECT).dvi
	$(PS2PDF) $(PROJECT).ps
	$(LATEX) $(PROJECT).tex 
#	$(BIBTEX) $(PROJECT)
	$(LATEX) $(PROJECT).tex 
	$(LATEX) $(PROJECT).tex 
	$(DVIPS) $(PROJECT).dvi
	$(PS2PDF) $(PROJECT).ps
	$(CP) $(PROJECT).pdf CV_CHENWW_2021_Fall.pdf
	
spell:
	$(SPELL) $(PROJECT).tex
clean:
	$(RM) $(PROJECT).ps
	$(RM) *.dvi
	$(RM) *.toc *.lot *.lof *.aux *.log *.synctex.gz
	$(RM) *.idx *.ind *.ilg
	$(RM) *.inx *.srt
	$(RM) *.blg *.bbl
	$(RM) *.out
	$(RM) *.BAK *.bak *~
	$(RM) MACROS/*.BAK MACROS/*.bak MACROS/*~
