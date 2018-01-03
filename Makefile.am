SUBDIRS = data doc

DISTCLEANFILES = Makefile.in Makefile

EXTRA_DIST = AUTHORS CHANGES COPYING README INSTALL

fortunesdocdir = $(datadir)/doc/fortunes-fr
fortunesdoc_DATA = \
	AUTHORS \
	CHANGES \
	COPYING \
	README

verify:
	@for i in $(SUBDIRS) ; do \
		$(MAKE) -C $$i verify ; \
	done

count:
	@(cd data && make count)
