> **Superseded.** The current data and code for this paper (version 1.1, corresponding to the second revision of the manuscript) are archived on Zenodo: https://doi.org/10.5281/zenodo.24443151. This repository holds the earlier version (v1.0-resubmission) and is no longer maintained.

# Digital Maturity and Technical Efficiency in NHS Acute Trusts

Code and data for:

> Ercole A. *Digital Maturity and Technical Efficiency in NHS Acute Trusts: Cross-Sectional Evidence from England.* PLOS ONE (under review, PONE-D-26-31236).

Bayesian stochastic frontier analysis (PyMC, marginalised half-normal likelihood with JLMS recovery of trust-level inefficiency) of 111 general acute NHS trusts in England, 2024/25, relating NHS England Digital Maturity Assessment scores to technical efficiency.

## Contents

| File | Description |
|---|---|
| `digital_maturity_technical_efficiency.ipynb` | Full analysis, executed: data assembly, Models A to C, translog and CES, robustness, sensitivity and validation analyses S0 to S9 |
| **Source data (redistributed)** | |
| `nhs-oversight-framework-acute-trust-league-table.csv` | Trust list, subtype, region |
| `Digital_Maturity_Assessment_Results_Data_File_v2.xlsx` | DMA 2024/25 results |
| `nhs-acute-hospital-trust-catchment-populations-data_tables-april-2026_table_6.csv` | Catchment IMD scores |
| **Derived data** | |
| `digital_maturity_with_ods.csv` | DMA acute provider scores matched to ODS codes |
| `tac_lookup.csv` | Trust-level figures extracted from the NHS provider accounts (TAC) |
| `model_data_tac.csv` | Assembled trust-level dataset; input to all models |
| **Results** | |
| `zenodo_deposit/analytical_dataset_111_trusts.csv` | Analytical sample with posterior technical efficiency |
| `zenodo_deposit/data_dictionary.csv` | Variable definitions and sources |
| `results_summary.json` | Every number reported in the paper |
| `model_results_tac.csv`, `model_results_ces_tac.csv`, `efficiency_rankings_tac.csv` | Trust-level model outputs |
| `prior_sweep.csv`, `posterior_predictive_checks.csv`, `deficit_specifications.csv` | Sensitivity and validation tables |
| `figures/` | Figures as produced by the notebook |

Three source datasets are too large for GitHub and are not included: the National Cost Collection 2024/25 organisation file, NHS Workforce Statistics (September 2024), and the TAC provider accounts workbooks. See `SOURCES.md`. Posterior traces (about 1.7 GB) are also omitted; they will be archived on Zenodo with the accepted version, and rerunning the notebook regenerates them.

## Reproducing the results

1. `conda env create -f environment.yml && conda activate dm-sfa`
2. **Models only:** `model_data_tac.csv` is included, so every modelling cell (from "Primary models" onward) runs without the large source files. Skip the four data-assembly cells at the top.
3. **Full pipeline:** download the files in `SOURCES.md` to the paths given there and run the notebook top to bottom.

All sampling uses `random_seed=42`. A full run takes several hours on a workstation CPU.

## Licence

Code: MIT (`LICENSE`). Derived data and results: CC BY 4.0. Source data contain public sector information licensed under the Open Government Licence v3.0.

## Citation

See `CITATION.cff`. A Zenodo DOI will be added on acceptance.
