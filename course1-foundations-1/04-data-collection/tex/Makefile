# Makefile for Teaching Materials
# Author: Wanhong Huang
# Description: Compile LaTeX teaching materials with proper cleanup

# Variables
LATEX = xelatex
BIBTEX = bibtex
MAIN = teaching_material
OUTPUT_DIR = build
LATEX_FLAGS = -interaction=nonstopmode -halt-on-error -output-directory=$(OUTPUT_DIR)

# Targets
.PHONY: all clean distclean view help

# Default target
all: $(OUTPUT_DIR)/$(MAIN).pdf

# Create output directory if it doesn't exist
$(OUTPUT_DIR):
	mkdir -p $(OUTPUT_DIR)

# Main compilation target (with bibliography support)
$(OUTPUT_DIR)/$(MAIN).pdf: $(MAIN).tex | $(OUTPUT_DIR)
	$(LATEX) $(LATEX_FLAGS) $(MAIN).tex
	-$(BIBTEX) $(OUTPUT_DIR)/$(MAIN)
	$(LATEX) $(LATEX_FLAGS) $(MAIN).tex
	$(LATEX) $(LATEX_FLAGS) $(MAIN).tex

# Quick compile (single pass, no bibliography)
quick: $(MAIN).tex | $(OUTPUT_DIR)
	$(LATEX) $(LATEX_FLAGS) $(MAIN).tex

# View the PDF
view: $(OUTPUT_DIR)/$(MAIN).pdf
	@if command -v xdg-open > /dev/null; then \
		xdg-open $(OUTPUT_DIR)/$(MAIN).pdf; \
	elif command -v open > /dev/null; then \
		open $(OUTPUT_DIR)/$(MAIN).pdf; \
	else \
		echo "No PDF viewer found. Please open $(OUTPUT_DIR)/$(MAIN).pdf manually."; \
	fi

# Clean auxiliary files but keep PDF
clean:
	rm -f $(OUTPUT_DIR)/*.aux $(OUTPUT_DIR)/*.log $(OUTPUT_DIR)/*.out \
	      $(OUTPUT_DIR)/*.toc $(OUTPUT_DIR)/*.bbl $(OUTPUT_DIR)/*.blg \
	      $(OUTPUT_DIR)/*.nav $(OUTPUT_DIR)/*.snm $(OUTPUT_DIR)/*.vrb \
	      $(OUTPUT_DIR)/*.fls $(OUTPUT_DIR)/*.fdb_latexmk $(OUTPUT_DIR)/*.synctex.gz $(OUTPUT_DIR)/$(MAIN).pdf

# Clean everything including PDF
distclean: clean
	rm -f $(OUTPUT_DIR)/*.pdf
	rmdir $(OUTPUT_DIR) 2>/dev/null || true

# Help message
help:
	@echo "Teaching Materials Makefile"
	@echo "=========================="
	@echo "Available targets:"
	@echo "  make          - Compile the teaching material (default)"
	@echo "  make quick    - Quick compile (single pass, no bibliography)"
	@echo "  make view     - Open the compiled PDF"
	@echo "  make clean    - Remove auxiliary files (keep PDF)"
	@echo "  make distclean- Remove all generated files including PDF"
	@echo "  make help     - Show this help message"
	@echo ""
	@echo "Main file: $(MAIN).tex"
	@echo "Output directory: $(OUTPUT_DIR)/"