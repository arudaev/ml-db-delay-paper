# ml-db-delay-paper

A Quarto research paper: **Predicting Deutsche Bahn Train Delays**.

Live site: https://arudaev.github.io/ml-db-delay-paper/

## What's here

- `index.qmd` — the full paper (14 sections, reproducible Python code)
- `_freeze/` — frozen cell outputs; CI renders from these without re-executing Python
- `_quarto.yml` — site configuration (flatly theme, code-fold, TOC)
- `references.bib` — ISLP, sklearn, dataset citations

## Local re-execution

```bash
pip install -r requirements.txt
quarto render index.qmd      # regenerates _freeze/ and _site/
```

Requires a Kaggle API key (`~/.kaggle/kaggle.json`) for the dataset download step.

## Part of

This repo is a git submodule of [HlexNC/Painfully-Trivial](https://github.com/HlexNC/Painfully-Trivial).
