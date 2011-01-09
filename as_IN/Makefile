DESTDIR = 
dictdir = /usr/share/myspell/dicts/
ooo_info_dir = /usr/share/myspell/infos/ooo/
docdir = /usr/share/doc/openoffice.org-hyphenation-as/


dict_files = hyph_as_IN.dic
doc_files = README ChangeLog COPYING
extra_files = Makefile
ooo_info_file = openoffice.org-hyphenation-as
version = 0.5.3

distdir=hyphenation-as-in_${version}

all: ${doc_files} ${dict_files}

install: all
	mkdir -p ${DESTDIR}${dictdir}
	cp ${dict_files} ${DESTDIR}${dictdir}
	cd ${DESTDIR}${dictdir}/ && chmod 644 ${dict_files} 
	mkdir -p ${DESTDIR}${ooo_info_dir}
	cp ${ooo_info_file}  ${DESTDIR}${ooo_info_dir}
	mkdir -p ${DESTDIR}${docdir}
	cp ${doc_files} ${DESTDIR}${docdir}
	update-openoffice-dicts 
	
	
uninstall:
	-cd ${DESTDIR}${dictdir}/ && rm ${dict_files}
	-cd ${DESTDIR}${docdir}/ && rm ${doc_files}
	-cd ${DESTDIR}${ooo_info_dir}/ && rm ${ooo_info_file}
	
clean:
	-rm -rf ${distdir}.tar.bz2 ${distdir}	
	
dist:
	-rm -rf ${distdir}.tar.bz2 ${distdir}
	mkdir ${distdir}
	cp -p ${dict_files}  ${doc_files} ${ooo_info_file}  ${extra_files} ${distdir}/
	tar cf ${distdir}.tar ${distdir}/
	bzip2 -9 ${distdir}.tar
	rm -rf ${distdir}/


