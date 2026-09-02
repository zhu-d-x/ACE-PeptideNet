# ACE-PeptideNet

## Overview

ACE-PeptideNet is an interpretable machine learning framework developed for the identification and prediction of ultra-short ACE-inhibitory peptides.

This repository provides the complete datasets and feature matrices used for the construction and evaluation of the ACE-PeptideNet model, enabling reproducible analysis of machine learning-based ACE-inhibitory peptide prediction.

The framework integrates physicochemical descriptors and peptide sequence-derived features with an XGBoost classifier to identify potential ACE-inhibitory peptides and analyze sequence–activity relationships.

---

# Dataset Description

The dataset contains a total of **2397 peptide sequences**, including:

- **1376 ACE-inhibitory peptides**
- **1021 non-ACE-inhibitory peptides**

The peptide sequences were collected from publicly available peptide databases, including:

- BIOPEP-UWM
- FermFooDb
- PlantPepDB
- DFBP

Each peptide is assigned a binary label:

| Label | Description |
|-------|-------------|
| 1 | ACE-inhibitory peptide |
| 0 | Non-ACE-inhibitory peptide |

---

# Repository Structure
