# Chapter 5: Communities of Interest for Anomaly Detection

A deep learning framework for detecting collective anomalies in IoT temperature sensor data using autoencoder architectures within Communities of Interest (CoIs).

## Overview

This folder contains the implementation of a collective anomaly detection methodology that identifies abnormal sensor behaviour in temperature time series from a network of meteorological stations in the province of Castelló, Spain. Hierarchical clustering groups the stations into Communities of Interest (CoIs). Three autoencoder architectures (MLP, LSTM and BiLSTM) are trained to detect collective anomalies such as sustained temperature drops that indicate sensor malfunctions.

### Key features

- **Hierarchical clustering**: groups sensors by temporal, spatial and elevation similarity (4 clusters: C1–C4)
- **Multiple autoencoder architectures**: MLP, LSTM and BiLSTM
- **Feature engineering**: 13-feature pipeline including temporal encodings and statistical features
- **Hyperparameter optimisation**: Bayesian Hyperband Optimisation (BOHB) with expanding window cross-validation
- **Global baseline**: comparison with a network-wide model to assess the effectiveness of CoIs

## Repository structure

| Folder | Content |
|---|---|
| `hpo_results/global/`, `hpo_results/representative/` | BOHB scripts and results (convergence, parameter importance, trials) per architecture |
| `final_models/global/`, `final_models/representative/` | Final training scripts and trained models, scalers, thresholds and metadata per architecture |
| `evaluation/global/`, `evaluation/representative/` | Test results per architecture: detailed predictions, metrics and comparison plots, per cluster (C1–C4) for representative models |

*Representative* models are trained on the representative station of each community; *global* models are trained on the whole network.

## Architectures

### Autoencoder models

1. **MLP autoencoder**: dense layers, for baseline comparison and computational efficiency
2. **LSTM autoencoder**: unidirectional LSTM for sequential pattern learning
3. **BiLSTM autoencoder**: bidirectional LSTM layers that capture temporal dependencies in both directions

### Feature engineering pipeline

13 features are extracted from the raw temperature readings:

- **Raw temperature**: original sensor value
- **Cyclical temporal encodings**: `hour_sin`, `hour_cos`, `dow_sin`, `dow_cos`
- **Derivative features**: velocity (1st derivative), acceleration (2nd derivative), energy
- **Volatility measures**: for detecting stuck or erratic sensors
- **Statistical aggregations**: rolling mean, standard deviation, range

## Methodology

### Data processing and clustering

- **Frequency**: 10-minute intervals
- **Sequence length**: 24
- **Clusters**: 4, formed through hierarchical clustering

### Cross-validation

Expanding window cross-validation (5 folds) with a purge gap:

- The expanding window preserves temporal order and prevents data leakage.
- A purge gap of 2 × sequence length (48 time steps) separates training and validation sets, removing autocorrelated influence from the training period.
- The validation set size is fixed and computed automatically to maximise data usage while keeping a feasible step between folds.
- The training set grows with each fold; the validation window moves forward without overlap.

### Hyperparameter optimisation

BOHB with 60 evaluations, combining the Tree-structured Parzen Estimator (TPE) with Hyperband pruning.

### Evaluation

- Metrics: accuracy, precision, recall, F1-score, specificity, AUC-ROC, PR-AUC
- Threshold strategy: statistical thresholds (μ + 3σ) proved more practical than ROC-based optimisation

### Hardware

Training: NVIDIA GeForce RTX 5090 GPU.

## Reproducibility

All experiments use fixed random seeds:

```python
np.random.seed(42)
tf.random.set_seed(42)
tf.config.experimental.enable_op_determinism()
```

Metadata and scalers are saved with each trained model for traceability.

## Data availability

The temperature data come from the meteorological station network of the Associació Valenciana de Meteorologia "Josep Peinado" (AVAMET). The data are not included in this repository; access requires permission from AVAMET: https://www.avamet.org/mxo-meteoxarxaonline.html

## Publication

Hammad, S. S., Ramos, F., Gould Carlson, M., Huerta Guijarro, J., Trilles, S. (2026). Community-based model sharing and generalisation: Anomaly detection in IoT temperature sensor networks. *Internet of Things*, 39, 102027. https://doi.org/10.1016/j.iot.2026.102027

Code archive: https://doi.org/10.5281/zenodo.18758344
