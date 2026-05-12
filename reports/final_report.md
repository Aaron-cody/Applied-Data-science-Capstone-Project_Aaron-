# SpaceX Falcon 9 Landing Success Prediction: Final Report

## Executive Summary

This project predicts whether a SpaceX Falcon 9 first stage will land successfully using historical launch records. The final portfolio version uses 90 launches from 2010-06-04 through 2020-11-05, with a binary target where `1` indicates a successful landing and `0` indicates an unsuccessful landing.

The best final models reached 83.3% accuracy on an 18-row held-out test set. Logistic regression was selected as the primary model because it tied for best test accuracy while remaining interpretable.

## Business Context

First-stage reuse is a major driver of launch economics. A landing-success classifier can help analysts reason about mission risk, compare launch profiles, and understand which available features are associated with successful booster recovery.

## Data

The final artifacts use local CSV snapshots in `data/processed/`:

- `dataset_part_1.csv`: cleaned launch records after initial collection.
- `dataset_part_2.csv`: launch records with the binary `Class` outcome.
- `dataset_part_3.csv`: encoded feature matrix for modeling.

Dataset scope:

- Rows: 90 launches
- Date range: 2010-06-04 to 2020-11-05
- Overall success rate: 66.7%
- Launch-site counts: CCAFS SLC 40 = 55, KSC LC 39A = 22, VAFB SLC 4E = 13

## Methodology

The project follows a standard applied data science workflow:

1. Collect Falcon 9 launch records from public sources.
2. Clean launch fields and derive the landing-success target.
3. Explore success rates by year, launch site, orbit, and payload mass.
4. Train classification models on the encoded feature matrix.
5. Compare models using cross-validation and a held-out test set.
6. Select a model with attention to both predictive performance and interpretability.

The final evaluation avoids test leakage by fitting preprocessing and hyperparameter search on the training split only.

## Results

| Model | Best CV Accuracy | Test Accuracy | Best Parameters |
|---|---:|---:|---|
| Logistic Regression | 0.835 | 0.833 | `{'model__C': 0.1, 'model__penalty': 'l1'}` |
| SVM | 0.877 | 0.833 | `{'model__C': 0.01, 'model__gamma': 'scale', 'model__kernel': 'linear'}` |
| KNN | 0.864 | 0.833 | `{'model__n_neighbors': 9, 'model__p': 1, 'model__weights': 'distance'}` |
| Decision Tree | 0.863 | 0.778 | `{'criterion': 'gini', 'max_depth': 2, 'min_samples_leaf': 1, 'min_samples_split': 2}` |

Selected model: Logistic Regression

Held-out test accuracy: 83.3%

Confusion matrix with labels `[0, 1]`:

| Actual / Predicted | 0: Did not land | 1: Landed |
|---|---:|---:|
| 0: Did not land | 3 | 3 |
| 1: Landed | 0 | 12 |

The model identified all successful landings in the test set, but it missed three unsuccessful landings by predicting them as successful.

## Key Figures

- `figures/landing_success_trend_by_year.png`
- `figures/success_rate_by_launch_site.png`
- `figures/success_rate_by_orbit.png`
- `figures/payload_mass_by_outcome.png`
- `figures/model_comparison_accuracy.png`
- `figures/confusion_matrix_best_model.png`
- `figures/logistic_regression_top_coefficients.png`

## Limitations

- The dataset contains only 90 rows.
- The held-out test set contains only 18 rows.
- Several orbit categories have very small sample sizes.
- Historical public launch features are not enough for operational launch-risk prediction.
- The model should be treated as an analytical portfolio project, not a production decision system.

## Recommended Next Steps

- Add richer mission and booster metadata if available.
- Use repeated cross-validation or bootstrap intervals to quantify uncertainty.
- Build a small dashboard for interactive filtering by launch site, orbit, payload mass, and model prediction.
- Package the modeling workflow into a script or lightweight pipeline for easier reruns.
