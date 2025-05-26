# Experiments with MSclassifR

This folder contains the code and setup used to reproduce the experimentation section of our study using the [`MSclassifR`](https://github.com/agodmer/MSclassifR) package. All code is intended for academic and non-commercial research use only — please see the [LICENSE](../LICENSE) file for full terms.

## Overview

The main script [`Run_experiments.R`](./Run_experiments.R) performs the full experimental pipeline:

1. Downloads and loads pre-processed mass spectrometry datasets from [Zenodo](https://zenodo.org/).
2. Splits each dataset into training and test subsets using `gS2()`, avoiding information leakage across replicates.
3. Applies different machine learning models and variable selection strategies via `eG()` to assess classification performance.
4. Outputs evaluation metrics including Accuracy and Cohen’s Kappa.

## Reproducibility and Computational Environment

All experiments were run using **R version 4.3.2** on a **Windows 11 x64 system**, with the following key packages:

- `MSclassifR` v0.3.3  
- `caret` v6.0-94  
- `MALDIquant` v1.22.1  
- `MALDIquantForeign` v0.14.1  
- `limma` v3.58.1  
- `Biobase` v2.62.0  
- `ggplot2` v3.5.0  
- Full details available in [`session_info.txt`](./session_info.txt)

The pipeline was executed on a standard workstation equipped with an **Intel Core i7 processor**, **16 GB RAM**, and running **Windows 11 64-bit**.  
While not requiring high-performance computing, faster machines with multi-core capabilities will improve processing time, especially when handling large datasets or cross-validation with many repetitions.

All analyses are intended to be **fully reproducible**, given the provided code, data, and session information.
