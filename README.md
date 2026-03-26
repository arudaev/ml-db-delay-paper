# ml-db-delay-paper

A Quarto research paper: **Predicting Deutsche Bahn Train Delays**.

Live site: https://arudaev.github.io/ml-db-delay-paper/

---

## How this works

| Layer | File | Purpose |
|---|---|---|
| Computation | `notebooks/analysis.ipynb` | Run once in Google Colab (GPU). Saves 6 PNGs + `results.json`. |
| Paper | `index.qmd` | Quarto document — code shown (`eval:false`), figures from `assets/figures/`. |
| CI | `.github/workflows/deploy.yml` | Renders `index.qmd` with Quarto only (no Python). Deploys to GitHub Pages. |

---

## Regenerating figures (one-time per update)

1. Open [`notebooks/analysis.ipynb`](notebooks/analysis.ipynb) in Google Colab
2. **Runtime → Change runtime type → T4 GPU**
3. Add your Kaggle API token: in the first cell, add `import os; os.environ['KAGGLE_API_TOKEN'] = 'your-token-here'`
4. **Run all cells** (~10–15 min on T4)
5. From the **Files panel** (left sidebar), download:
   - `assets/figures/*.png` (6 files)
   - `assets/results.json`
6. Place them in the repo at the same paths
7. `git add assets/ && git commit -m "Update figures from Colab run" && git push`
8. GitHub Actions deploys the paper in ~15 seconds

---

## Local render (no computation)

```bash
# Install Quarto: https://quarto.org/docs/get-started/
quarto render index.qmd
# Opens _site/index.html
# Note: figures show as broken until assets/ is populated from a Colab run
```

---

## Part of

This repo is a git submodule of [HlexNC/Painfully-Trivial](https://github.com/HlexNC/Painfully-Trivial).
