SDATE = 20111020
ODATE = 20111020
HTMLIMG = specumln3.jpg ndataf1.jpg ncharf2.jpg specstc.jpg specu3f.jpg ivoa.jpg
FILES = specrc3mod2.tex specvot.tex fits2.tex specrc3.ps specrc3.pdf specxml2.tex specxml.xsd specrc3.html doug.vot ${HTMLIMG}
HFILES = SpectrumDM-${ODATE}.pdf SpectrumDM-${ODATE}.html specxml.xsd ${HTMLIMG}
NFILES = spec12mod1.tex specvot.tex photvot.tex fits3.tex spec12.ps spec12.pdf specxml4.tex specxml12.xsd spec12mod1.html doug.vot ${HTMLIMG}
NHFILES = SpectrumDM-${SDATE}.pdf SpectrumDM-${SDATE}.html specxml12.xsd ${HTMLIMG}

all:	spec11.tex
	latex spec11
	latex spec11
	dvips -o spec11.ps -P pdf spec11
	ps2pdf spec11.ps spec11.pdf
	cp spec11.pdf  SpectrumDM-${ODATE}.pdf


mall:	spec12mod1.tex
	latex spec12mod1
	latex spec12mod1
	dvips -o spec12.ps -P pdf spec12mod1
	ps2pdf spec12.ps spec12.pdf
	cp spec12.pdf  SpectrumDM-${SDATE}.pdf


oall:	specrc3.tex
	latex specrc3
	latex specrc3
	dvips -o specrc3.ps -P pdf specrc3
	ps2pdf specrc3.ps specrc3.pdf
	cp specrc3.pdf  SpectrumDM-${SDATE}.pdf

html:	
	vohtml specrc3mod2 h
	rm -f SpectrumDM-${SDATE}.html
	cp h/specrc3mod2.html SpectrumDM-${SDATE}.html

nhtml:	
	vohtml spec12mod1 h
	rm -f SpectrumDM-${SDATE}.html
	cp h/spec12mod1.html SpectrumDM-${SDATE}.html

pack:
	tar cvzf /data1/tfr/vospec.tgz ${FILES}

ivoa:   rall html pack
	tar cvzf /data1/tfr/ivoa.tgz ${HFILES} 

npack:
	tar cvzf /data1/tfr/vospec.tgz ${NFILES}

nivoa:   all nhtml npack
	tar cvzf /data1/tfr/ivoa.tgz ${NHFILES} 


