# NEO Hazard Prediction

Predictive modeling project focused on classifying Near-Earth Objects (NEOs) as hazardous or non-hazardous using observable physical and orbital attributes.

## Project Overview

This project builds and evaluates a binary classification workflow to answer:

**Which features and K value produce the best-performing K-Nearest Neighbors (KNN) classifier for NEO hazard prediction?**

The analysis follows a complete machine learning pipeline:
- problem framing and metric selection
- exploratory data analysis (EDA)
- feature selection and preprocessing
- model tuning with cross-validation
- final model evaluation on held-out test data

## Dataset

- **Source:** NASA/JPL NEO records (`neo.csv`)
- **Target variable:** `hazardous` (True/False)
- **Candidate predictors used in analysis:**
  - `est_diameter_min`
  - `est_diameter_max`
  - `relative_velocity`
  - `miss_distance`
  - `absolute_magnitude`

## Tools and Technologies

- **Language:** R
- **Notebook environment:** Jupyter Notebook
- **Core libraries:**
  - `tidyverse` (data wrangling and visualization)
  - `tidymodels` (modeling workflow)
  - `kknn` (KNN engine)
  - `cowplot`, `repr` (plot formatting and display)
  

## Machine Learning Fundamentals Demonstrated

- **Supervised learning:** binary classification
- **Model selection:** KNN hyperparameter tuning (`k`)
- **Feature engineering:** predictor scaling and centering (`step_scale`, `step_center`)
- **Data splitting strategy:** train/test split with stratification
- **Class imbalance handling:** class balancing via resampling
- **Validation strategy:** 5-fold cross-validation (`vfold_cv`)
- **Model evaluation:** accuracy, precision, recall, and confusion matrix
- **Reproducibility practices:** fixed random seeds and explicit workflow steps

## Modeling Approach

1. Clean and prepare the dataset.
2. Perform EDA to examine class distribution and predictor behavior.
3. Build a preprocessing recipe and standardize predictors.
4. Tune KNN with `k` values across a defined range.
5. Compare cross-validated performance to choose candidate `k` values.
6. Train final candidate models and evaluate on test data.

## Results Snapshot

- Best-performing region observed around **k = 13 to 16**
- Final models compared at **k = 14** and **k = 15**
- Top model achieved approximately **87.5% test accuracy**
- Precision/recall analysis used to assess hazardous-object detection quality

## Repository Structure

- `neoAnalysis.ipynb` - full analysis, modeling workflow, and results
- `neo.csv` - project dataset
- `README.md` - project summary and technical overview

## Key Takeaways

- Data preprocessing choices (especially scaling) materially affect distance-based models like KNN.
- Accuracy alone is not enough for risk-sensitive tasks; recall and precision are both critical.
- Cross-validation is essential for selecting robust hyperparameters and reducing overfitting risk.
- Thoughtful feature selection can improve model reliability and interpretability.