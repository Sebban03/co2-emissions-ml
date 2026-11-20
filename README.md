# CO2 Emissions: Individual Carbon Footprint

Machine learning project that predicts an individual's monthly carbon emission from lifestyle features.

## Dataset
[Individual Carbon Footprint Calculation](<https://www.kaggle.com/datasets/dumanmesut/individual-carbon-footprint-calculation>), 10,000 people and 20 features (diet, transport, energy use, waste and others). Target: `CarbonEmission`.

## Tasks
- **Regression:** predict `CarbonEmission` (main metric: MAE).
- **Classification:** predict `high_emission`, the top 20% of emissions (main metric: PR-AUC, because classes are imbalanced).

## Notebooks
1. `01_eda.ipynb`: data quality, distributions and relationships with the target.
2. `02_split.ipynb`: label definition and stratified train/test split.
3. `03_modeling.ipynb`: preprocessing pipelines and comparison of baseline, linear, k-NN, tree-based and boosting models with cross-validation.

## Results (cross-validation on the training set)
- Classification: logistic regression PR-AUC 0.974, F1 0.906 (baseline PR-AUC 0.200).
- Regression: gradient boosting MAE 106.4, RMSE 147.0 (baseline MAE 766.0).

Hyperparameter tuning and the final evaluation on the test set are planned.

## How to run
```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```
Place the dataset at `data/raw/co2_emissions.csv` (if it is not in the repository) and run the notebooks in order. `02_split.ipynb` creates `data/processed/`.