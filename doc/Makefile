# Makefile for Spectrum Data Model document.

# short name of your document
DOCNAME = Spectrum

# document version
#   count up; you probably do not want to bother with versions <1.0
DOCVERSION = 1.2

# Publication date, ISO format; update manually for "releases"
DOCDATE = 2022-06-22
SDATE = 20220622

# What is it you're writing: NOTE, WD, PR, REC, PEN, or EN
DOCTYPE = WD

# An e-mail address of the person doing the submission to the document
# repository (can be empty until a make upload is being made)
AUTHOR_EMAIL=

# Source files for the TeX document (but the main file must always
# be called $(DOCNAME).tex
SOURCES = ${DOCNAME}.tex specvot.tex fits2.tex specxml2.tex tab.tex doug.vot

# List of image files to be included in submitted package (anything that
# can be rendered directly by common web browsers)
#FIGURES = role_diagram.svg
FIGURES = role_diagram.eps ivoa.jpg diagrams/specumln3.jpg diagrams/ndataf1.jpg diagrams/ncharf2.jpg diagrams/specstc.jpg diagrams/specu3f.jpg

# List of PDF figures (figures that must be converted to pixel images to
# work in web browsers).
VECTORFIGURES = 

# Additional files to distribute (e.g., CSS, schema files, examples...)
SCHEMA = specxml.xsd
AUX_FILES = ${SCHEMA}

# ================================================================================
FILES = ${SOURCES} ${SCHEMA} specrc3.html ${FIGURES}
HFILES = SpectrumDM-${SDATE}.pdf SpectrumDM-${SDATE}.html ${SCHEMA} ${FIGURES}


doc:	Spectrum.tex
	latex Spectrum
	latex Spectrum
	dvips -o Spectrum.ps -P pdf Spectrum
	ps2pdf Spectrum.ps Spectrum.pdf
	cp Spectrum.pdf  SpectrumDM-${SDATE}.pdf

html:	
	vohtml Spectrum h
	rm -f SpectrumDM-${SDATE}.html
	cp h/Spectrum.html SpectrumDM-${SDATE}.html

pack:
	tar cvzf ${BASEDIR}/vospec.tgz ${FILES}

ivoa:   doc html pack
	tar cvzf ${BASEDIR}/ivoa.tgz ${HFILES} 

