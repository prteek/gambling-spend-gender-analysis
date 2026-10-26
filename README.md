# gambling-spend-gender-analysis

Do boys and girls spend different amounts on gambling, and is weekly spending money linked to how much teenagers
gamble? A regression analysis of a British survey of teenage gambling, written up as the paper
[Gambling Spend ~ Gender, Analysis](https://www.alphaxiv.org/abs/2610.gambling-spend-gender-analysis) on alphaXiv.

```
index.qmd          the paper (R, knitr)
_quarto.yml        PDF format; renders to _output/gambling-spend-gender-analysis.pdf
references.bib     references
_freeze/           frozen results of the R code (tracked)
renv.lock          R package versions (renv)
_wide-tables.lua   fits wide tables to the page in the PDF
gambling.jpeg      thumbnail
```

## Render

```bash
Rscript -e 'renv::restore()'                       # once: install the R packages in renv.lock
QUARTO_R=/opt/homebrew/bin/Rscript quarto render   # -> _output/gambling-spend-gender-analysis.pdf
```

Rendering reuses the frozen results in `_freeze/` until a code chunk changes; the analysis has no random steps,
so re-running it reproduces the same numbers.

Data: `teengamb` from the faraway R package (Ide-Smith & Lea, 1988, *Gambling in Young Adolescents*).
