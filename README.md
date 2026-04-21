# medcurveR

**Tail-aware visualization and sparse-tail diagnostics for Kaplan-Meier and restricted cubic spline figures in medical research**

medcurveR is an R package for generating publication-oriented Kaplan-Meier (KM) and restricted cubic spline (RCS) figures with explicit sparse-tail handling and diagnostic traceability.

## Overview

In medical research, the late follow-up region of a Kaplan-Meier curve and the extreme exposure range of a restricted cubic spline plot are often supported by relatively sparse data. In routine manuscript preparation, these regions are frequently cropped or visually down-weighted, but the rationale is rarely recorded as part of a reproducible workflow.

medcurveR was developed to make sparse-tail handling explicit, rule-based, and reproducible.

## Main functions

- `km_pretty()` – tail-aware KM plot with confidence intervals, risk table, and cutoff diagnostics
- `km_compare_tail()` – comparison of untruncated, reference, and tail-aware KM outputs
- `rcs_pretty()` – tail-aware RCS plot with confidence bands, sparse-tail shading, and lower distribution panel
- `rcs_compare_tail()` – full-range versus tail-aware RCS comparison under matched y-axis scaling
- `tail_profile()` / `tail_profile_table()` – structured summaries of tail rules, bounds, and sparsity diagnostics

## Key features

- Rule-based sparse-tail handling for KM and RCS figures
- Explicit display cutoffs and visible diagnostic summaries
- Comparison-oriented outputs for transparent figure justification
- Publication-oriented figure generation for medical and epidemiologic studies
- Reproducible plotting workflow with inspectable tail decisions

## Installation

You can install the development version from GitHub with:

```r
# install.packages("remotes")
remotes::install_github("linlin-boo/medcurveR")
```

If you are installing from a local source bundle:

```r
install.packages("path/to/medcurveR", repos = NULL, type = "source")
```

## Minimal usage

```r
library(medcurveR)

# Example function calls (adapt to your own data)
# km_pretty(data = dat, time = "time", event = "event", group = "group")
# rcs_pretty(data = dat, x = "marker", y = "outcome")
```

## Repository structure

This repository is organized to support both standard R package use and SoftwareX submission requirements.

```text
medcurveR/
├─ README.md
├─ LICENSE.txt
├─ DESCRIPTION
├─ NAMESPACE
├─ R/
├─ man/
├─ vignettes/              # optional
├─ inst/                   # optional
├─ tests/                  # optional
├─ figures/                # optional: manuscript figures
└─ repo/
   └─ src/
      └─ medcurveR_source_placeholder.txt
```

### Important note for SoftwareX submission

SoftwareX asks authors to provide source code in a `repo/src` directory. For an R package, the canonical package source usually remains in the standard top-level package structure (`DESCRIPTION`, `NAMESPACE`, `R/`, `man/`, etc.).

To satisfy the journal check more safely, keep the normal R package layout at the repository root **and also place a source snapshot or source bundle in `repo/src/`**. Two practical options are:

1. copy the full package source folder into `repo/src/medcurveR/`, or
2. place a release source archive (for example, the built package tar.gz) in `repo/src/`.

## Reproducibility and manuscript use

The package is intended for manuscript-oriented figure production, especially when visual interpretation may otherwise extend into weakly supported tails. It does **not** introduce a new survival estimator or a new spline estimator; instead, it standardizes how sparse tails are delimited, documented, and compared in figure workflows.

## License

This project is released under the MIT License. See `LICENSE.txt` for details.

## Citation

If you use this software in academic work, please cite the corresponding software paper and the GitHub repository or release record.

## Contact

- **Li Huilin**
- **Yuqing Xue** (corresponding author)
- School of Public Health and Health Science, Tianjin University of Traditional Chinese Medicine, Tianjin, China

GitHub repository: <https://github.com/linlin-boo/medcurveR>
