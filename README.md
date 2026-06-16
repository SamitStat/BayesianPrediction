# BayesianPrediction

An interactive, from-scratch explainer for the **loading prior** in the Run-2 Bayesian SAWS model:

```
λ_pk = τ_k · z_pk ,   z_pk ~ Normal(0,1) ,   τ_k ~ HalfNormal(0.3)
```

It builds the equation one piece at a time (what a prior is → centering at 0 → spread → one shared spread per mechanism → the `τ·z` rewrite → `z` as pattern → the half-normal → what `0.3` means → putting it together → the full matrix), with a live interactive plot in every section.

## How to view

Open **`index.html`** in any web browser (double-click it). It is fully self-contained — no internet, no build step, no dependencies — and adapts to light/dark mode.

## What's inside

- A mechanism selector (capacity, aged, corroded, aged×corroded) that drives the middle sections.
- Shared `τ` and `z` controls that stay in sync across sections.
- A final view of the complete 10×4 loading matrix Λ.

## About the numbers

The loadings shown are the **real Run-2 fitted posterior means** (effect-coded contrasts on the log scale; multiplier = `e^λ`), taken from the model output `layerB_effects.csv`. The per-mechanism `τ` and `z` displayed are an exact decomposition of those fitted loadings — `τ` is each column's root-mean-square and `z = loading ÷ τ` — so `τ·z` always reproduces the real value while keeping `z` at spread ≈ 1, as the model intends.

Headline result it lands on: corroded → r2 ≈ +0.82 on the log scale ≈ **×2.34** (corrosion more than doubles the post-peak slope).
