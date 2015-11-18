
ifeq ($(OS),Windows_NT)
	ASCIIDOC := python C:\asciidoc-8.6.8\asciidoc.py
else
	ASCIIDOC := asciidoc
endif


SRC := $(wildcard *.txt)

OUT := index.html \
	$(addsuffix .html,$(basename $(SRC)))
OUTDIR := ../
FULLOUT := $(addprefix $(OUTDIR)/,$(OUT))


.PHONY: all
all: $(FULLOUT)

$(FULLOUT): Makefile

$(OUTDIR)/%_en.html: %_en.txt all_en.conf
	$(ASCIIDOC) -v -b html5 -f all_en.conf -o $@ $<

$(OUTDIR)/%_ru.html: %_ru.txt all_ru.conf
	$(ASCIIDOC) -v -b html5 -f all_ru.conf -o $@ $<

$(OUTDIR)/index.html: index_ru.txt all_ru.conf
	$(ASCIIDOC) -v -b html5 -f all_ru.conf -o $@ $<
