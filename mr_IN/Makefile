DESTDIR = 
hyphdir = /usr/share/hyphen/
dictdir = /usr/share/myspell/dicts/
docdir = /usr/share/doc/hyphen-mr/


dict_files = hyph_mr_IN.dic
doc_files = README ChangeLog MIT-LICENSE.txt
extra_files = Makefile
version = 0.9.0

distdir=hyphen-mr-${version}

all: ${doc_files} ${dict_files}

install: all
	mkdir -p ${DESTDIR}${docdir}
	cp ${doc_files} ${DESTDIR}${docdir}
	mkdir -p ${DESTDIR}${hyphdir}
	cp ${dict_files} ${DESTDIR}${hyphdir}
	chmod 644 ${DESTDIR}${hyphdir}${dict_files}	
	mkdir -p ${DESTDIR}${dictdir}
	ln -s ${hyphdir}${dict_files} ${DESTDIR}${dictdir}${dict_files}
	
uninstall:
	-cd ${DESTDIR}${dictdir}/ && rm ${dict_files}
	-cd ${DESTDIR}${docdir}/ && rm ${doc_files}
	-cd ${DESTDIR}${hyphdir}/ && rm ${dict_files}
	
clean:
	-rm -rf ${distdir}.tar.bz2 ${distdir}	
	
dist:
	-rm -rf ${distdir}.tar.bz2 ${distdir}
	mkdir ${distdir}
	cp -p ${dict_files}  ${doc_files}  ${extra_files} ${distdir}/
	tar cf ${distdir}.tar ${distdir}/
	bzip2 -9 ${distdir}.tar
	rm -rf ${distdir}/


