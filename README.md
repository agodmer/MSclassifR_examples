<h1 align="center">MSclassifR: an R Package for Supervised Classification of Mass Spectra with Machine Learning Methods</h1>

<div align="center" style="margin-top: 10px;">
  <a href="https://cran.r-project.org/web/packages/MSclassifR/index.html"><img src="https://cranlogs.r-pkg.org/badges/grand-total/MSclassifR?color=green" alt="Total Downloads"></a>
  <a href="https://cran.r-project.org/web/packages/MSclassifR/index.html"><img src="https://www.r-pkg.org/badges/version/MSclassifR" alt="Version"></a>
  <a href="https://cran.r-project.org/web/checks/check_results_MSclassifR.html"><img src="https://badges.cranchecks.info/worst/MSclassifR.svg" alt="CRAN Checks"></a>
  <a href="https://www.gnu.org/licenses/gpl-3.0"><img src="https://img.shields.io/badge/License-GPLv3-blue.svg" alt="GPL v3 License"></a>
  <img src="https://visitor-badge.lithub.cc/badge?page_id=lizheming.visitor-badge&left_color=red&right_color=green" alt="Visitor Badge">
</div>

<p align="center">
  <img src="Figures/LogoMSclassifR.jpg" width="430" height="250">
</p>
<p align="center">
  <a href="https://cran.r-project.org/web/packages/MSclassifR/index.html">Click here to download MSclassifR from CRAN</a>
</p>

## 1. Description:

This package provides R functions to classify mass spectra in known categories, and to determine discriminant mass-over-charge values. It was developed with the aim of identifying very similar species or phenotypes of bacteria from  mass spectra obtained by Matrix Assisted Laser Desorption Ionisation - Time Of Flight Mass Spectrometry (MALDI-TOF MS). However, the different functions of this package can also be used to classify other categories associated to mass spectra; or from mass spectra obtained with other mass spectrometry techniques. It includes easy-to-use functions for pre-processing mass spectra, functions to determine discriminant mass-over-charge values (m/z) from a library of mass spectra corresponding to different categories, and functions to predict the category (species, phenotypes, etc.) associated to a mass spectrum from a list of selected mass-over-charge values. 
<p align="center">
  <img src="Figures/screenMsclassifR_page-0001.jpg" width="500" height="500">
</p>

<p align="center">
  <a href="https://doi.org/10.1101/2022.03.14.484252">
    <img src="https://img.shields.io/badge/https://doi.org/10.1101/2022.03.14.484252-blue.svg" alt="DOI Badge">
  </a>
</p>

## 2. Installation:

The installation of the `MSclassifR` package requires the installation of packages from `Bioconductor`, so you you might have to install the latest version of the `BiocManager` package. The `MSclassifR` package imports the other necessary packages from the CRAN. In addition, it is recommended to install the latest version of R.

```
## install BiocManager if not installed
if (!require("BiocManager", quietly = TRUE))
            install.packages("BiocManager")

## Install the mixOmics and multtest packages from Bioconductor
BiocManager::install(c("multtest","mixOmics", "limma", "qvalue", "cp4p"))

## Install MSclassifR package
install.packages("MSclassifR")

## Check after install the `MSclassifR` package:
require(MSclassifR) ## For spectral easy signal processing and machine learning
```

## 3. Your Guide to MSclassifR: step-by-step examples and case studies
- **Understanding the basics:** [a brief introduction concerning machine learning](Documents/ML_intro.md)
- **Exploring MSclassifR:** [a comprehensive overview of a user-friendly tool for mass spectrometry classification](Documents/MSclassifR_summary.md)
- **Hands-on examples:** three vignettes illustrating how to use the functions of this package from real data sets are also available online to help users: 
  - [*Ecrobia* sp.](https://agodmer.github.io/MSclassifR_examples/Vignettes/Vignettemsclassifr_Ecrobiav3.html)
  - [*Klebsiella* sp.](https://agodmer.github.io/MSclassifR_examples/Vignettes/Vignettemsclassifr_Klebsiellav3.html)
  - [differential analysis of omics data](https://agodmer.github.io/MSclassifR_examples/Vignettes/Vignettemsclassifr_DAv3.html)
- **Delve deeper into MSclassifR:** [pre-print article](https://www.biorxiv.org/content/10.1101/2022.03.14.484252v2)

### 🗨️ Forum et Support: do you have any questions or suggestions? Join the discussion on our [forum](https://github.com/agodmer/MSclassifR_examples/discussions).

## 4. Practical workflow using MSclassifR:

<p align="center" style="overflow: hidden; height: 300px; width: auto;">
  <img src="Figures/MSclassifRworkflow.PNG" alt="MSclassifR Workflow" style="object-fit: cover; object-position: top; width: auto; height: 100%;">
</p>

---
