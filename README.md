# PGDL-for-evapotranspiration-estimation
A four-stage Python workflow for preprocessing gridded environmental data, pretraining a deep neural network to estimate 8-day evapotranspiration (ET), fine-tuning the model with a physical constraint based on the Penman-Monteith equation, and generating spatially continuous ET predictions.

## Overview
This repository implements a physics-guided deep learning pipeline for ET estimation. The workflow is designed around multi-source gridded environmental variables, land-cover information, and geographic coordinates.

The pipeline includes:

- Raster preprocessing and temporal alignment
- Water-mask and physical-range filtering
- Leakage-aware feature normalization
- Deep neural network pretraining
- Two-stage physics-guided fine-tuning
- Model evaluation and scientific visualization
- Spatial ET prediction to GeoTIFF

## Script Description

### `data_pre.py`
Preprocesses 8-day environmental rasters and prepares a tabular training dataset.

### `data_train.py`
Trains the baseline deep neural network using the preprocessed NPZ dataset.

### `finetune_PM.py`
Fine-tunes the pretrained model through a residual correction head and a physics-based constraint.

### `pred_finetune_PM.py`
Applies the fine-tuned physics-residual model to gridded environmental data and writes ET predictions as GeoTIFF files.
