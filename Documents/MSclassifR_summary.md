
<h1 align="center">MSclassifR: A Comprehensive Overview of a User-Friendly Tool for Mass Spectrometry Classification</h1>
Alexandre Godmer, Quentin Giai Gianetto

## 1. Introduction

MSclassifR was developed with accessibility and flexibility in mind, MSclassifR supports a variety of workflows, integrates cutting-edge algorithms, and provides tools for pre-processing, model training, evaluation, and visualization.
MSclassifR is a versatile and user-friendly tool that democratizes access to advanced mass spectrometry analysis. By integrating comprehensive pre-processing pipelines, sophisticated feature selection methods, and state-of-the-art machine learning algorithms, the package enables users to perform interpretable classification of mass spectra using a set of R functions with minimal technical expertise.

---

## 2. Key Functionalities of MSclassifR

### 2.1 Automated Pre-Processing of Mass Spectra

MSclassifR includes comprehensive pre-processing functions to handle raw mass spectrometry data, ensuring high-quality inputs for downstream analysis:
- **Signal Processing (`SignalProcessing`)**:
  - performs intensity transformations (e.g., square root or log), baseline correction (e.g., SNIP), and spectral alignment using robust warping methods.
  - offers smoothing methods such as Wavelet smoothing to enhance data quality.
  - outputs normalized intensity matrices for further statistical analysis.
- **Peak Detection (`PeakDetection`)**:
  - detects significant peaks based on signal-to-noise ratios (SNR).
  - aligns peaks across spectra using configurable tolerance levels for mass alignment.
  - outputs a list of aligned peaks for each spectrum.

These tools automate critical steps, ensuring consistency and reproducibility in mass spectrometry workflows.

---

### 2.2 Feature Selection: Identifying Discriminant m/z Values

Feature selection is essential for identifying the most informative m/z values that discriminate between categories. MSclassifR provides multiple methods:
- **Mean Decrease in Accuracy (MDA)**:
  - Feature selection by thresholding "mda" variable importances estimated from Random Forests using a mixture model (see [our paper](https://doi.org/10.1016/j.eswa.2025.128796)). The `mda` variable importances are calculated using the reduction in model accuracy when a specific variable is excluded. 
- **Cross-Validated Permutation (CVP)**:
  - Feature selection by thresholding "cvp" variable importances estimated from Random Forests using a mixture model (see [our paper](https://doi.org/10.1016/j.eswa.2025.128796)). The `cvp` variable importances are calculated using cross-validations to evaluate variable importances (see [Janitza et al.](https://doi.org/10.1007/s11634-016-0276-4)).
- **Recursive Feature Elimination (RFE) (`SelectionVar`)**:
  - Combines with either random forests (`RFERF`) or logistic regression (`RFEGlmnet`) to iteratively remove non-essential features.
- **Sparse Partial Least Squares Discriminant Analysis (sPLSDA) (`SelectionVar`)**:
  - Feature selection by selecting variables from the ones kept in latent components of the sparse PLS-DA model using an automatic choice of the number of components (when the balanced classification error rate (BER) reaches a plateau) (see the `mixOmics` R package).
- **VSURF (Variable Selection Using Random Forests) (`SelectionVar`)**:
  - Selects variables using a three steps variable selection procedure based on random forests (see the `VSURF` R package). 
- **Boruta (`SelectionVar`)**:
  - Selects variables using the Boruta algorithm that iteratively compares importances of variables with importances of shadow variables,
created by shuffling original ones (see the `Boruta` R package).
- **Multiple statistical tests (`SelectionVarStat`)**:
  - Selects variables using multiple statistical tests (e.g., ANOVA, Kruskal-Wallis, Limma) to identify discriminant features (m/z values). Features are selected by controlling a false discovery rate threshold using adaptive Benjamini-Hochberg procedures.

These methods ensure the selection of statistically significant features.

---

### 2.3 Machine Learning Algorithms for Classification

MSclassifR supports a wide range of machine learning algorithms, making it suitable for diverse datasets and classification problems:
- **Parametric models**:
  - linear logistic regression (PredictLogReg function): standard approach for binary or multiclass classification problems.
  - minimising Akaike Information Criterium from multiple linear regressions (PredictFastClass function). It can be used to flag a mass spectrum that do not correspond to any of the categories present in the training data set ("p_not_in_DB" score).
- **Non-parametric models**:
  - **Support Vector Machines (SVM)**: effective for data separation using kernel tricks (only linear kernels are available in MSclassifR).
  - **Random Forests (RF)**: ensemble-based decision tree models that offer robust performance on complex datasets.
  - **Neural Networks (nnet)**: feed-forward neural networks with a single hidden layer for capturing intricate patterns in data.
  - **Extreme Gradient Boosting (XGBoost)**: a high-performance gradient boosting method optimized for speed and accuracy.
---
### 2.4 Resampling Techniques for Imbalanced Data

To address challenges posed by imbalanced datasets, MSclassifR incorporates resampling methods:
- **Up-Sampling**: replicates minority class samples to match the majority class.
- **Down-Sampling**: reduces majority class samples to match the minority class.
- **SMOTE (Synthetic minority Over-sampling Technique)**: generates synthetic data points for the minority class using k-nearest neighbors ("smote_classif" function).

These techniques are seamlessly integrated into model training functions like `LogReg` and `SelectionVar`, ensuring robust classification results even with imbalanced data.

---

### 2.5 Model Evaluation and Interpretation

MSclassifR provides extensive tools for evaluating model performance and interpreting results:
- **Performance Metrics**:
  - accuracy, Kappa, F1 Score, Adjusted Rand Index, and Matthews Correlation Coefficient.
  - cross-validation methods such as k-fold, repeated k-fold, and leave-one-out cross-validation (LOOCV) ensure reliable performance estimates&#8203;:contentReference[oaicite:4]{index=4}.
- **Confusion Matrices**:
  - summarize predictions versus actual outcomes, offering insights into classification accuracy and errors.
- **Visual Metrics**:
  - boxplots and summary tables of evaluation metrics allow users to compare models and select the most effective one.
---
### 2.6 Prediction and Classification

Trained models can be applied to new datasets using functions like `PredictLogReg` and `PredictFastClass`. These functions:
- match m/z values between the model and input spectra.
- provide category probabilities that a mass spectrum belongs to a category and assign predictions based on the probabilities.
- allow for tolerance adjustments to optimize peak matching.
- can be used to flag mass spectra that do not correspond to any categories in the training dataset ('p_not_in_DB' score in the `PredictFastClass` function).

---

### 2.7 Visualization Tools

MSclassifR includes robust visualization capabilities to aid interpretation:
- **Spectra Visualization (`PlotSpectra`)**:
  - visualizes raw and processed spectra, highlighting detected peaks and discriminant m/z values.
- **Performance Visualization**:
  - displays evaluation metrics, confusion matrices, and feature importance graphs for easy interpretation.

---

### 2.8 Practical Workflow : Step-by-Step Guide to Using MSclassifR

1. **Pre-Processing**:
   - use `SignalProcessing` to clean and align raw spectra.
   - detect peaks with `PeakDetection` and create an intensity matrix.

2. **Feature Selection**:
   - apply `SelectionVar` with methods like RFE or mda for instance to identify discriminant m/z values.

3. **Model Training**:
   - train supervised models using `LogReg`, selecting algorithms (e.g., SVM, random forests) and metrics (e.g., Kappa, Accuracy).

4. **Evaluation**:
   - use cross-validation and confusion matrices to assess model performance.
   - visualize results with boxplots and other graphical outputs.

5. **Prediction**:
   - classify new spectra using `PredictLogReg` or `PredictFastClass`, ensuring robust and interpretable predictions.

---

### 2.9 Accessibility for Non-Experts

The design of MSclassifR prioritizes ease of use, especially for non-experts in programming or machine learning:
- high-level functions abstract technical details, allowing users to focus on scientific questions rather than implementation challenges.
- comprehensive vignettes and tutorials provide step-by-step guidance.
- automated processes like hyperparameter tuning, resampling, and visualization make complex workflows accessible.

---

**Dr Alexandre Godmer, Dr Quentin Giai Gianetto**
