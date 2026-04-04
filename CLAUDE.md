# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

LaTeX report template for ITESM (Tecnológico de Monterrey) students. Single-file template (`report.tex`) with a professional title page, colored theorem environments, and math macros. Written entirely in Spanish.

## Build

```bash
# Compile the report (requires a TeX distribution with pdflatex)
latexmk -pdf report.tex

# Single pass (faster, may need multiple runs for references/TOC)
pdflatex report.tex

# Clean auxiliary files
latexmk -c
```

## Template Structure

All content lives in `report.tex`. The file is organized into clearly marked sections:

1. **DATOS DEL REPORTE** (lines ~275-295) — The only section users need to edit to customize metadata: `\titulo`, `\titulocorto`, `\facultad`, `\curso`, `\cursocorto`, `\profesor`, `\campus`, `\fecha`, and `\addautor[Major]{Name}{email}` calls for each author (IEEE-style blocks with optional major/career field). Short title/course variants are displayed in page headers.
2. **Packages & config** — Encoding (UTF-8, T1), Spanish babel, geometry, microtype, AMS math, xcolor, tcolorbox, tikz, hyperref+cleveref.
3. **Color palette** — Four semantic colors: `colordef` (definitions), `colorteor` (theorems/lemmas/propositions/corollaries), `colorej` (examples), `colorobs` (observations/exercises).
4. **tcolorbox theorem environments** — `teorema`, `lema`, `proposicion`, `corolario`, `definicion`, `ejemplo`, `observacion`, `ejercicio`. All use `\newtcbtheorem` with shared counter for theorem-like envs. Label prefixes: `thm`, `lem`, `prop`, `cor`, `def`, `ej`, `obs`, `exer`.
5. **Math macros** — Number sets (`\N`, `\Z`, `\Q`, `\R`, `\C`), Greek shortcuts (`\eps`, `\del`), paired delimiters (`\abs`, `\norm`, `\inner`, `\ceil`, `\floor`), Spanish operators (`\sen`, `\tg`).
6. **Section formatting** — Custom `titlesec` styles with `\sffamily` headings and horizontal rule under `\section`.
7. **Header/footer** — `fancyhdr` using `\cursocorto`, `\titulocorto`, and page number.
8. **Bibliography** — `biblatex` with `style=science` and `biber` backend; entries live in `references.bib`.

## Key Conventions

- Language: all content, environment names, cleveref labels, and proof names are in Spanish.
- Cross-references use `cleveref` (`\cref`, `\Cref`) with tcolorbox counter names (e.g., `tcb@cnt@teorema`).
- The `\abs*{}`, `\norm*{}` starred forms produce auto-scaled delimiters (from `mathtools`).
- `logo.png` is the ITESM logo used on the title page.
- The `.gitignore` covers standard LaTeX auxiliary files; `report.pdf` is tracked in git.
