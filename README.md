#ML_Checks — Machine Learning Project Suite

Author: cg
Repo: cgamingpro/ML_Chekcks

##Project overview

This repository bundles three concise, well-documented machine-learning projects intended for learning and demonstration:

Property Price Prediction — Regression models to predict median house values for California districts.

Customer Churn Prediction — Classification model that predicts whether a customer will churn.

Early Disease Detection (Heart Disease) — Classification model to predict presence of heart disease.

Each project includes a Jupyter notebook that performs EDA, preprocessing, model training, evaluation, and a short summary of insights & recommendations.

Repo structure (recommended)
ML_Chekcks/
├─ datasets/
│  ├─ property_price.csv
│  ├─ customer_churn.csv
│  └─ heart_disease.csv
├─ notebooks/
│  ├─ 01_property_price.ipynb
│  ├─ 02_customer_churn.ipynb
│  └─ 03_early_disease_detection.ipynb
├─ src/
│  ├─ data_utils.py
│  ├─ models.py
│  └─ evaluation.py
├─ models/
├─ outputs/
├─ requirements.txt
├─ environment.yml
└─ README.md


Note: Move reusable code into /src to avoid duplication and keep notebooks focused on experiments.

Datasets (sources)

Place the CSVs in datasets/ with the names above. Example sources from the project PDF:

Property Price Prediction
Google Sheet: https://docs.google.com/spreadsheets/d/1B9RTjgPSEWyQzDr-CQJmCYRriaBIaGq2WEkfp2TLTIA

Customer Churn Prediction
Google Sheet: https://docs.google.com/spreadsheets/d/1J2aMbLrRnk8g0Y5TSbz-en_7UxlI7xh0cLIZnIy4aew

Early Disease Detection (Heart Disease)
Google Sheet: https://docs.google.com/spreadsheets/d/10k1aWfHrvoXJrHxMz6F2nfK5-UlkCmQ8EjhUt9Casso

You can download each as CSV and commit into /datasets for reproducibility.

Quick start — Recommended (Conda)

Clone the repo:

git clone https://github.com/cgamingpro/ML_Chekcks.git
cd ML_Chekcks


Create and activate a conda env:

conda create -n ml_checks python=3.10 -y
conda activate ml_checks


Install dependencies:

# If you have environment.yml
conda env update --file environment.yml --prune
# OR
pip install -r requirements.txt


(Optional) Register kernel for Jupyter/VS Code:

python -m ipykernel install --user --name ml_checks --display-name "Python (ml_checks)"


Launch Jupyter:

jupyter notebook


Open and run notebooks in notebooks/.

Quick start — pip / venv

Create venv:

python -m venv .venv
# macOS / Linux
source .venv/bin/activate
# Windows (PowerShell)
.\\.venv\\Scripts\\activate


Install:

pip install -r requirements.txt


Start Jupyter:

python -m notebook

Example requirements.txt
pandas
numpy
scikit-learn
matplotlib
seaborn
jupyter
ipykernel
joblib


Add extra libs you used (e.g., xgboost, lightgbm) as needed.

How each notebook is organized

All notebooks follow this pattern:

Load dataset from datasets/

Exploratory Data Analysis (plots, summary stats)

Preprocessing (missing values, encoding, scaling)

Train baseline model(s)

Evaluate using appropriate metrics

Save final model artifact to models/ (optional)

Short conclusions & recommendations

Expected outputs: model artifacts in models/, evaluation metrics printed, visualizations inline or saved to outputs/.

Evaluation metrics

Regression (Property Price): MAE, MSE, RMSE, R²

Classification (Churn & Disease): Accuracy, Precision, Recall, F1-score, ROC-AUC

Tips & troubleshooting

Conda env not visible in VS Code: run the ipykernel install step and restart VS Code. Then Ctrl+Shift+P → Python: Select Interpreter → pick Python (ml_checks).

conda missing from PATH (Windows): add conda install paths to PATH or reinstall Anaconda/Miniconda. If conda’s a pain, use python -m venv instead.

Large data / memory issues: sample data for prototyping, or use chunked reads: pd.read_csv(..., chunksize=...).

Notebooks produce big diffs: use nbstripout before committing to remove outputs.

Reproducibility

Pin package versions in requirements.txt or environment.yml.

Set random seeds (np.random.seed(42), random_state=42) in notebooks.

Contribution

Open an issue describing changes/bug.

Make a feature branch: git checkout -b feat/your-feature.

Keep notebook outputs cleared before commit (use nbstripout or export to .py).

Add tests in tests/ if adding functions in /src.

License & attribution

Add a LICENSE file (MIT or Apache-2.0 recommended) if you plan to open-source.

Next steps I can help with

Convert notebooks into clean Python modules or scripts.

Create environment.yml or pin requirements.txt.

Add CI workflows (GitHub Actions) to run unit tests or execute notebooks automatically.

Export notebooks to .py for better version control.
