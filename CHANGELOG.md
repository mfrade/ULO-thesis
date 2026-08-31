# Changelog

All notable differences between this fork and the upstream [IPLeiria Thesis](https://github.com/joseareia/ipleiria-thesis) template by José Areia are documented here.

## Branding

- Replaced the Polytechnic of Leiria / IPLeiria ESTG logo with the University of Leiria and Oeste (ULO) / ESTG logo, in both light-background and dark-background (cover) variants.
- Replaced "Polytechnic University of Leiria" with "University of Leiria and Oeste" throughout the metadata, the cover, and the legal declaration text (PT/ES/EN) in the Copyright page.
- Reworked the README: new logo banner, screenshots regenerated from this fork's actual configuration, all links repointed to this repository, and an attribution section crediting the original author and project.

## Renamed files

- `IPLeiriaMain.tex` → `ULOMain.tex`
- `IPLeiriaThesis.cls` → `ULOThesis.cls` (including its internal LaTeX3 namespace, e.g. `\g_IPLeiriaThesis_...` → `\g_ULOThesis_...`)
- `Chapters/Appendices/00-AppendixA.tex` → `Chapters/Appendices/00-AppendixAI.tex`
- Build tooling (`Makefile`, `.latexmkrc`, GitHub Actions workflow) updated to match.

## AI Use Declaration & Appendix

- Strengthened the AI Use Declaration to require documenting AI interactions "to the greatest extent possible," rather than a single illustrative example.
- Moved the sample AI interaction out of the declaration and into its own appendix, now titled "Documented Examples of AI Usage," cross-referenced from the declaration via `\autoref`.
- Replaced the single generic example with six realistic, subject-agnostic examples: grammar/spelling check, improving academic tone, code generation (with a syntax-highlighted listing), literature search support, condensing a section, and generating a LaTeX table (with a syntax-highlighted listing).

## Fixes

- Appendices/Annexes chapter lettering now runs consecutively (A, B, C, ...) instead of Annexes jumping to "L" due to a hardcoded `\setcounter{chapter}{11}` left over from the original template.
- Fixed PDF navigation: clicking a chapter in the Table of Contents or the PDF bookmark panel no longer jumps to an unexpected horizontal scroll position. Root cause was hyperref's default `XYZ`-type destinations; fixed via `pdfview=FitH`.
- Fixed a `\textcolor{}{}` compile error (blank lines aren't allowed inside a macro argument) by switching to the `color` environment for a multi-paragraph credits block.

## Repository

- Detached from the upstream repository and published as a standalone public repository at [github.com/mfrade/ULO-thesis](https://github.com/mfrade/ULO-thesis).
