SDATE = 20220622
BASEDIR = /data1/tfr

HTMLIMG = specumln3.jpg ndataf1.jpg ncharf2.jpg specstc.jpg specu3f.jpg ivoa.jpg
SCHEMA = specxml.xsd
FILES = specrc3mod2.tex specvot.tex fits2.tex specrc3.ps specrc3.pdf specxml2.tex doug.vot ${SCHEMA} specrc3.html ${HTMLIMG}
HFILES = SpectrumDM-${SDATE}.pdf SpectrumDM-${SDATE}.html ${SCHEMA} ${HTMLIMG}


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

