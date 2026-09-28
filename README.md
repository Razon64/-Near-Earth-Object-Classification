# NEA Classification

Deep learning for near-Earth asteroid (NEA) orbit-class classification from orbital elements. The project compares TabNet against several attention-based neural models on a heavily imbalanced dataset, tests three imbalance-handling strategies, and explains the resulting TabNet model with SHAP, LIME and Shapash.

> Status: research prototype. The headline accuracies below come from a pipeline that resamples before splitting, so they are optimistic.

## Overview

- Task: 6-class classification of asteroids from 11 orbital and physical features.
- Models compared: TabNet, GRU + Attention, CNN-LSTM + Attention, FT-Transformer-style model, Self-Attention Network (SAN).
- Imbalance handling: SMOTE, Tomek Links, and Alpha-VAE latent features + ADASYN.
- Evaluation: accuracy, weighted precision / recall / F1, 5-fold stratified CV, paired t-tests against TabNet.
- Explainability: SHAP (KernelExplainer), Shapash, LIME (per class), and per-feature contribution plots.

## Data

The notebook expects a CSV named `classast - pha.csv` (one experiment reads `classast - pha1.csv`) with a `class` target column and the following features:

| Feature | Meaning |
|---|---|
| `a (AU)` | Semi-major axis |
| `e` | Eccentricity |
| `i (deg)` | Inclination |
| `w (deg)` | Argument of perihelion |
| `Node (deg)` | Longitude of ascending node |
| `M (deg)` | Mean anomaly |
| `q (AU)` | Perihelion distance |
| `Q (AU)` | Aphelion distance |
| `P (yr)` | Orbital period |
| `H (mag)` | Absolute magnitude |
| `MOID (AU)` | Minimum orbit intersection distance |

The dataset is strongly imbalanced: the smallest class has only 3 members. Add the data source and download instructions here.


Add citation details or an associated paper here.
