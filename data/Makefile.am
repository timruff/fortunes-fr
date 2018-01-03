SUBDIRS = bd cinema droit humoristes humour fr.rec.photo GDP haiku informatique litterature_etrangere litterature_francaise mysoginie personnalites philosophie politique proverbes religion sciences

EXTRA_DIST = Makefile.common

CLEANFILES = .count *~

update_makefile.common:	
	for i in $(SUBDIRS) ; do \
		cp -f Makefile.common $$i/Makefile.am ; \
	done

count:
	@$(RM) -f .count
	@for i in $(SUBDIRS) ; do \
		$(MAKE) -C $$i count-recursive ; \
	done
	@$(AWK) '{printf("%-40s %4i\n", $$1, $$2); count += $$2} END {printf("---------------------------------------------\n%-40s %4i\n", "TOTAL", count)}' .count
	@$(RM) -f .count
					
verify:
	@for i in $(SUBDIRS) ; do \
		$(MAKE) -C $$i verify ; \
	done
