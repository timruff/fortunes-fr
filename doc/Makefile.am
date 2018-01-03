CLEAN_FILES = *~

fortunesdoc_DATA = 16eme_siecle.txt moyen_age.txt
fortunesdocdir = $(datadir)/doc/fortunes-fr

EXTRA_DIST = $(fortunesdoc_DATA)

verify:
	@echo -e "\nVérification des fichiers de documentation..."
	@for file in $(fortunesdoc_DATA) ; do \
		$(AWK) '{if (length($$0) > 78) print FILENAME": "NR": ERREUR: ligne trop longue"}' $$file ; \
	done
	@echo -e "\n"
