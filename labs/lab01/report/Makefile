# Makefile for Pandoc conversions

# Find all .md files in the current directory
SOURCE_DOCS := $(wildcard *.md)

# Define the output files we want to create
EXPORTED_DOCS = \
	$(SOURCE_DOCS:.md=.html) \
	$(SOURCE_DOCS:.md=.pdf)  \
	$(SOURCE_DOCS:.md=.docx)

# The Pandoc command and default options
PANDOC = pandoc
PANDOC_OPTIONS = --standalone

# Default target: build all output formats from all source files
all: $(EXPORTED_DOCS)

# Pattern rules for converting one file at a time
%.html: %.md
	$(PANDOC) $(PANDOC_OPTIONS) -t html5 -o $@ $<

%.pdf: %.md
	$(PANDOC) $(PANDOC_OPTIONS) -o $@ $<

%.docx: %.md
	$(PANDOC) $(PANDOC_OPTIONS) -o $@ $<

# Clean up all generated files
clean:
	rm -f $(EXPORTED_DOCS)

# Declare targets that are not files
.PHONY: all clean
