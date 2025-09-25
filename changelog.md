# Changelog

All notable changes to this project will be documented in this file.  
This project follows a simplified versioning style (`v0.x` during development).

---

## [v0.3.0] - 2025-09-25
### Added
- Exploratory Data Analysis (EDA) notebook (`03_eda_visualization`):
  - Histograms, violin plots, and log-transformed distributions.
  - Correlation heatmap with strong-correlation highlights.
  - Pairwise scatter/regression plots with stakeholder-friendly annotations.
  - PCA projection (PC1 vs PC2) colored by class.
- Updated README with workflow diagram (`fig_0_workflow.png`).
- Conclusions on feasibility: dataset requires enrichment + domain expertise for predictive modeling.

### Changed
- Refined violin plots with legend for mean/median/quartiles.
- Improved class distribution chart with percentages annotated above bars.

---

## [v0.2.0] - 2025-09-24
### Added
- Data QAQC notebook (`02_data_qaqc`):
  - SHA256 checksum to guarantee raw dataset integrity.
  - Handling of missing and truncated values with flags (`_trunc_flag`, `_missing_flag`).
  - Imputation rules (<10%, 10–40%, >40%) with median or DL/√2 substitutions.
  - Export of:
    - `cleaned_data.csv` → full dataset with raw, clean, and flags.
    - `cleaned_data_for_ML.csv` → ML-ready dataset (compact format).
- Summary tables of missing/truncated values per assay.
- First draft of project README with objectives and workflow.

### Changed
- Standardized assay column names with `_clean` suffix.
- Replaced placeholder values (`-999`) with `NaN`.

---

## [v0.1.0] - 2025-09-23
### Added
- Initial commit with raw dataset import (`data_for_distribution.csv`).
- Basic notebook for dataset exploration:
  - Shape, column types, and missing value checks.
  - Initial histograms and violin plots of raw assays.
- Draft project plan and goals.

---
