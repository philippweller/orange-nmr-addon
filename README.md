# Oranjenmr — NMR Preprocessing for Orange3

Custom Orange3 add-on with preprocessing widgets for 1D NMR spectra
(e.g. 1H), aimed at multivariate analysis (chemometrics).

## Widgets

| Widget | Purpose |
|--------|---------|
| **NMR Binning** | Reduce spectral resolution (avg/sum/max buckets) |
| **NMR Normalization** | Total area / max / L2 / reference-region |
| **NMR Baseline Correction** | Polynomial fit or Asymmetric Least Squares (ALS) |
| **NMR Filter** | Savitzky-Golay smoothing + derivatives |
| **NMR Region Exclusion** | Remove solvent / artifact ppm ranges |
| **NMR Reference & Alignment** | Peak-based shift alignment |

Spectral data follows the Orange/Spectroscopy convention: attribute names
encode the x-axis (ppm) values.

## Installation (any Orange3 ≥ 3.40)

Use **Orange's own Python**, not `/usr/bin/python3`.

### macOS (Orange.app)

```bash
/Applications/Orange.app/Contents/Frameworks/Python.framework/Versions/Current/bin/python3 -m pip install .
```

### Windows (Orange Command Prompt) / Linux / conda

```bash
python -m pip install .
```

### With Spectroscopy integration (optional, enables `getx` fallback)

```bash
python -m pip install ".[full]"
```

Widgets appear on the next canvas open — no Orange restart needed.

## License

MIT