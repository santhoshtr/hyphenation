DESTDIR = 
hyphdir = /usr/share/hyphen/
dictdir = /usr/share/myspell/dicts/
ooo_info_dir = /usr/share/myspell/infos/ooo/
docdir = /usr/share/doc/openoffice.org-hyphenation-hi/


dict_files = hyph_hi_IN.dic
doc_files = README ChangeLog COPYING
extra_files = Makefile
ooo_info_file = openoffice.org-hyphenation-hi
version = 0.5.3

distdir=hyphenation-hi-in_${version}

all: ${doc_files} ${dict_files}

install: all
	mkdir -p ${DESTDIR}${ooo_info_dir}
	cp ${ooo_info_file}  ${DESTDIR}${ooo_info_dir}
	mkdir -p ${DESTDIR}${docdir}
	cp ${doc_files} ${DESTDIR}${docdir}
	mkdir -p ${DESTDIR}${hyphdir}
	cp ${dict_files} ${DESTDIR}${hyphdir}
	chmod 644 ${DESTDIR}${hyphdir}${dict_files}	
	mkdir -p ${DESTDIR}${dictdir}
	ln -s ${DESTDIR}${hyphdir}${dict_files} ${DESTDIR}${dictdir}${dict_files}
	update-openoffice-dicts 
	
	
uninstall:
	-cd ${DESTDIR}${dictdir}/ && rm ${dict_files}
	-cd ${DESTDIR}${docdir}/ && rm ${doc_files}
	-cd ${DESTDIR}${ooo_info_dir}/ && rm ${ooo_info_file}
	-cd ${DESTDIR}${hyphdir}/ && rm ${dict_files}
	
clean:
	-rm -rf ${distdir}.tar.bz2 ${distdir}	
	
dist:
	-rm -rf ${distdir}.tar.bz2 ${distdir}
	mkdir ${distdir}
	cp -p ${dict_files}  ${doc_files} ${ooo_info_file}  ${extra_files} ${distdir}/
	tar cf ${distdir}.tar ${distdir}/
	bzip2 -9 ${distdir}.tar
	rm -rf ${distdir}/


