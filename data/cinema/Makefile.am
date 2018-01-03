catdir:=$(shell pwd)
catname=$(shell basename $(catdir))

fortunes := $(shell /bin/ls | $(AWK) '$$0 !~ /^(Makefile($$|\.in$$|\.am$$))|($(catname)($$|.dat$$))|(CVS)/ { print }')

# fortunesdir = $(datadir)/games/fortunes
fortunes_DATA = $(catname) $(catname).dat

CLEANFILES = $(catname) $(catname).dat *~


$(catname): $(fortunes)
	$(AWK) '{print}' $(fortunes) > $(catname)
	if [ "$(CHARSET)" != "default" ]; then \
		$(RECODE) ISO8859-15..$(CHARSET) $(catname) ; \
	fi

$(catname).dat: $(catname)
	strfile $(catname)

count:
	@for i in $(fortunes) ; do \
		$(AWK) '/^%$$/ {sum +=1} END {printf ("%s %i\n", FILENAME, sum); }' $$i ; \
	done | $(AWK) '{printf("%-40s %4i\n", $$1, $$2); count += $$2} END {printf("---------------------------------------------\n%-40s %4i\n", "TOTAL", count)}'

count-recursive:
	@$(AWK) '/^%$$/ {sum +=1} END {printf ("%s %i\n", "$(catname)", sum); }' $(fortunes) >> ../.count

verify:
	@echo -e "\nVérification des fichiers de citations..."
	@for file in $(fortunes) ; do \
		$(AWK) 'BEGIN { start = 1 }; /^%/ {if ($$0 != "%") print FILENAME": "NR": ERREUR: caractères supplémentaires après le %" ; len = (NR - start) ; if (len > 15) print FILENAME": "start": ERREUR: citation trop longue ("len" lignes)"; start = NR ;} END {if ($$0 != "%") print FILENAME": ERREUR: fichier non terminé par un %"}' $$file ; \
		$(AWK) '{if (length($$0) > 72) print FILENAME": "NR": ERREUR: ligne trop longue ("length($$0)" caractères)"}' $$file ; \
		$(AWK) '/^        -/ {print FILENAME": "NR": ERREUR: 8 espaces à remplacer par une tabulation"}' $$file ; \
		$(AWK) '/^[ \t]*$$/ {print FILENAME": "NR": ERREUR: ligne vide"}' $$file ; \
	done
	@ echo -e "\n"

dist-hook:
	for i in $(fortunes) ; do \
		$(CP) --preserve --parents $$i $(distdir) ; \
	done
	$(LN) -sf ../Makefile.common $(distdir)/Makefile.am
