```markdown
# Consistency Tax and Epistemic Thermodynamics

This repository contains the reference implementation of the **Consistency Tax (CT)** framework.

## Contents

- `MainPaper.tex` — main article (compilable with `pdflatex` + `biber`).
- `Supplement.tex` — extended proofs, derivations, simulations, and protocol details.
- `references.bib` — bibliography (with some CT-internal entries marked as To-verify).
- `ExecutiveOverview.md` — one-page, non-technical summary.
- `ReleaseNotes.md` — originality, conjectures, and extension guidance.
- `ReproducibilityChecklist.md` — step-by-step requirements for replication.
- `FigurePlan.md` — figure list, data sources, and TikZ/pgfplots stubs.
- `AuthorNote.txt` — personal handoff statement.
- `LICENSE.md` — licensing for text and code.
- `CITATION.cff` — citation metadata.

## How to Compile

1. Ensure a standard LaTeX environment with:
   - `latexmk`, `pdflatex` or `lualatex`,
   - `biber`,
   - required packages: `geometry`, `hyperref`, `amsmath`, `amssymb`, `amsthm`,
     `bm`, `siunitx`, `booktabs`, `graphicx`, `tikz`, `pgfplots`,
     `cleveref`, `csquotes`, `biblatex`.
2. Run:
   ```bash
   latexmk -pdf MainPaper.tex
   biber MainPaper
   latexmk -pdf MainPaper.tex
3. Repeat similarly for Supplement.tex if desired.