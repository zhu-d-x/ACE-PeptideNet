# ACE-PeptideNet

## Overview

ACE-PeptideNet is an interpretable machine learning framework developed for the identification and prediction of ultra-short ACE-inhibitory peptides.

This repository provides the complete datasets, predefined data partitions, and feature matrices used for the construction and evaluation of the ACE-PeptideNet model, enabling reproducible analysis of machine-learning-based ACE-inhibitory peptide prediction.

The framework integrates physicochemical descriptors and peptide sequence-derived features with an XGBoost classifier to identify potential ACE-inhibitory peptides and analyze sequence–activity relationships.

---

## Dataset Description

The dataset contains a total of **2,397 peptide sequences**, including:

- **1,376 ACE-inhibitory peptides**
- **1,021 peptides without reported ACE-inhibitory activity**

The peptide sequences were collected from publicly available peptide databases, including:

- BIOPEP-UWM
- FermFooDb
- PlantPepDB
- DFBP

Each peptide was assigned a binary label:

| Label | Description |
|---|---|
| 1 | ACE-inhibitory peptide |
| 0 | Peptide without reported ACE-inhibitory activity |

For the negative dataset, no artificially generated peptide sequences were used. Peptides annotated or reported as ACE-inhibitory were excluded from the candidate negative pool, and duplicate sequences and sequences overlapping with the positive dataset were removed. A total of 1,021 peptides without reported ACE-inhibitory activity were then sampled to construct the negative dataset.

---

## Data Partitioning and Validation Strategy

The complete dataset was divided into a **development set (80%)** and an **independent test set (20%)** using stratified sampling to preserve the class distribution.

The development set was used for model training, validation, and hyperparameter optimization. Five-fold cross-validation was performed within the development set. In each cross-validation iteration, four folds were used for model training and the remaining fold was used for validation.

The independent test set was completely held out during model development and was used exclusively for final model evaluation. It was not used for model selection or hyperparameter optimization.

Hyperparameter optimization was conducted using grid search based only on the cross-validation results obtained from the development set.

The exact peptide sequences and predefined data partitions used in this study are provided in the `data/` directory to facilitate reproducibility.

---

## Repository Structure

The repository currently contains the following main directories:

- `data/` — datasets and predefined data partitions used for model development and independent evaluation.
- `feature/` — physicochemical and sequence-derived feature matrices used for machine learning model construction.
- `README.md` — description of the dataset, validation strategy, and repository organization.

Detailed descriptions of the files contained in each directory are provided below.

---

## Model Construction and Evaluation

Five machine learning algorithms were evaluated using the same screened feature set and the same data partitioning strategy:

- XGBoost
- LightGBM
- CatBoost
- Gradient Boosting Decision Tree (GBDT)
- Multi-Layer Perceptron (MLP)

Five-fold cross-validation within the development set was used for hyperparameter optimization. All models were subsequently evaluated using the same independent test set to ensure a fair and consistent comparison.

The independent test set remained separate from model training, validation, and hyperparameter optimization throughout the model development procedure.

---

## Reproducibility

To reproduce the model development and evaluation procedure:

1. Use the predefined development and independent test datasets provided in the `data/` directory.
2. Perform model training and hyperparameter optimization using only the development set.
3. Conduct five-fold cross-validation within the development set for model selection and hyperparameter optimization.
4. Do not use the independent test set during model training, validation, or hyperparameter tuning.
5. Evaluate the final optimized model on the independent test set.
6. Use the corresponding feature matrices provided in the `feature/` directory.

The predefined data partitions provided in this repository correspond to those used to generate the results reported in the manuscript.

---

## ACE-PeptideNet Web Server

ACE-PeptideNet is also available as a web-based prediction system supporting both single-sequence and batch prediction of 2–5-residue ultra-short peptides.

- Primary server: https://ace.peptideinnov.com
- Overseas mirror: https://global.ace.peptideinnov.com
- Web interface: https://github.com/zhu-d-x/ACE-PeptideNet-Web

---

## Data Availability

The complete dataset, predefined data partitions, and related feature files used in this study are publicly available in this repository:

https://github.com/zhu-d-x/ACE-PeptideNet

---

## Citation

If you use ACE-PeptideNet, the associated datasets, or the web server in your research, please cite the corresponding article after publication.

**Article title:**  
*Interpretable Machine Learning Decodes Sequence–Activity Rules of Ultra-Short ACE-Inhibitory Peptides*

DOI and complete bibliographic information will be added after publication.
