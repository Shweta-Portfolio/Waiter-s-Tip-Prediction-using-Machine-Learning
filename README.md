# Restaurant Tipping Analysis

This repository explores guest tipping behavior using the classic `tips.csv` dataset. The work is captured in the notebook `food.ipynb`, where exploratory data analysis (EDA) and a handful of regression models are used to understand which factors influence tip amounts and to estimate expected tips.

## Project Structure

- `food.ipynb` — end-to-end workflow covering data inspection, visualization, preprocessing, model training, and evaluation.
- `tips.csv` — input dataset (244 dining transactions with bill, tip, party details, and context features).

## Prerequisites

- Python 3.9+
- Recommended environment: virtualenv, venv, or Conda
- Key packages:
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - scikit-learn
  - xgboost
  
Install the dependencies with:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost
```

## How to Use

1. Launch Jupyter:
   ```bash
   jupyter notebook
   ```
2. Open `food.ipynb`.
3. Run the cells sequentially to reproduce the entire analysis (EDA, preprocessing, modeling, and evaluation).

All plots are generated inline, and each modeling step prints mean absolute error (MAE) scores for the train and validation sets.

## Analysis Summary

- **Exploratory analysis:** Histograms, boxplots, and scatter plots provide intuition around bill amounts, tip sizes, and relationships with categorical factors (sex, smoker status, day, and service time).
- **Preprocessing:** Outlier trimming removes extreme bills and tips, categorical values are label-encoded, and features are standardized prior to modeling.
- **Modeling:** Linear Regression, XGBoost, Random Forest, and AdaBoost regressors are benchmarked via an 80/20 train–validation split.
- **Key result:** Random Forest delivered the lowest validation MAE (~0.74), making it the top performer among the tested models, albeit with some overfitting (train MAE ~0.28).
