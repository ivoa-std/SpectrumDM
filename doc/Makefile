# Makefile for Spectrum Data Model document.

# short name of your document
DOCNAME = Spectrum

# document version
#   count up; you probably do not want to bother with versions <1.0
DOCVERSION = 1.2

# Publication date, ISO format; update manually for "releases"
DOCDATE = 2023-03-17
SDATE = 20230317

# What is it you're writing: NOTE, WD, PR, REC, PEN, or EN
DOCTYPE = WD

# An e-mail address of the person doing the submission to the document
# repository (can be empty until a make upload is being made)
AUTHOR_EMAIL=

# Source files for the TeX document (but the main file must always
# be called $(DOCNAME).tex
SOURCES = ${DOCNAME}.tex specxml.tex specvot.tex specfits.tex fields_table.tex example_xml1.tex example_vot1.tex example_vot2.tex example_fits1.tex 

# List of image files to be included in submitted package (anything that
# can be rendered directly by common web browsers)
#FIGURES = role_diagram.eps ivoa.jpg diagrams/specumln3.jpg diagrams/ndataf1.jpg diagrams/ncharf2.jpg diagrams/specstc.jpg diagrams/specu3f.jpg
FIGURES = role_diagram.eps ivoa.jpg diagrams/spectrum.png diagrams/data.png diagrams/characterization.png diagrams/coordsys.png diagrams/dataset.png diagrams/datatypes.png

# List of PDF figures (figures that must be converted to pixel images to
# work in web browsers).
VECTORFIGURES = 

# Additional files to distribute (e.g., CSS, schema files, examples...)
SCHEMA = ../schema/Spectrum-1.01.xsd
AUX_FILES = ${SCHEMA}

# ================================================================================
FILES = ${SOURCES} ${SCHEMA} specrc3.html ${FIGURES}
HFILES = SpectrumDM-${SDATE}.pdf SpectrumDM-${SDATE}.html ${SCHEMA} ${FIGURES}

clean:
	rm -f Spectrum.pdf Spectrum.ps Spectrum.log Spectrum.dvi Spectrum.out Spectrum.aux Spectrum.toc

doc:	Spectrum.tex
	pdflatex Spectrum
	pdflatex Spectrum
	cp Spectrum.pdf SpectrumDM-${SDATE}.pdf

html:	
	vohtml Spectrum h
	rm -f SpectrumDM-${SDATE}.html
	cp h/Spectrum.html SpectrumDM-${SDATE}.html

pack:
	tar cvzf vospec.tgz ${FILES}

ivoa:   doc html pack
	tar cvzf ivoa.tgz ${HFILES} 

