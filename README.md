# Acid–Base Titration Simulator

An interactive web-based titration simulator that generates detailed titration curves with labeled key points. Built as a single-page application — no build tools or dependencies to install.

**Live Site:** `https://<your-username>.github.io/<repo-name>/`

---

## Features

- **6 titration types** — weak acid + strong base, strong acid + strong base, weak base + strong acid, strong acid + weak base, strong base + weak acid, strong base + strong acid
- **Common substance library** — preloaded Ka/Kb values for acids (HCl, HNO₃, CH₃COOH, HF, etc.) and bases (NaOH, KOH, NH₃, etc.)
- **Custom Ka/Kb input** — enter any dissociation constant with automatic pKa/pKb display
- **Adjustable parameters** — analyte concentration (M), analyte volume (mL), titrant concentration (M)
- **Detailed titration curve** with:
  - Labeled axes with units (pH vs. Volume of Titrant in mL)
  - **Equivalence point** marked and labeled
  - **½ Equivalence point** marked and labeled (for weak acid/base titrations)
  - **Buffer region** highlighted (10%–90% of equivalence volume)
  - pH 7 reference line
- **Results panel** — initial pH, equivalence volume/pH, half-equivalence volume/pH, pKa/pKb, buffer region range

## How to Host on GitHub Pages

1. Create a new repository on GitHub
2. Upload `index.html` (and optionally `README.md`, `LICENSE`) to the root of the repo
3. Go to **Settings → Pages**
4. Under **Source**, select **Deploy from a branch**
5. Choose the `main` branch and `/ (root)` folder
6. Click **Save**
7. Your site will be live at `https://<username>.github.io/<repo-name>/` within a few minutes

## Tech Stack

- Vanilla HTML / CSS / JavaScript (no frameworks, no build step)
- [Chart.js 4](https://www.chartjs.org/) — chart rendering
- [chartjs-plugin-annotation](https://www.chartjs.org/chartjs-plugin-annotation/) — equivalence point markers, buffer region overlay
- Google Fonts (JetBrains Mono, DM Sans)

## Chemistry Notes

The simulator uses standard aqueous equilibrium calculations at 25 °C (Kw = 1.0 × 10⁻¹⁴):

| Region | Method |
|---|---|
| Initial point | ICE table / quadratic for weak species; direct −log[H⁺] for strong |
| Buffer region | Henderson–Hasselbalch equation |
| ½ Equivalence | pH = pKa (weak acid) or pOH = pKb (weak base) |
| Equivalence | Hydrolysis of conjugate species |
| Post-equivalence | Excess strong acid/base dominates |

All concentrations assume monoprotic behavior. Polyprotic acids (H₂SO₄, H₃PO₄) use only their first dissociation as an approximation.

## License

MIT — see [LICENSE](LICENSE) for details.
