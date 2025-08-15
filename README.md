# ML_Chekcks

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)]()
[![Python](https://img.shields.io/badge/python-3.10+-blue.svg)]()
[![Status](https://img.shields.io/badge/status-experimental-yellow.svg)]()

**Author:** cg  
**Repo:** `cgamingpro/ML_Chekcks`

---

## What is this
**ML_Chekcks** contains three compact ML projects aimed at learning and demos:

- **Property Price Prediction** — regression on California district features.  
- **Customer Churn Prediction** — binary classification to predict churn.  
- **Early Disease Detection (Heart Disease)** — binary classification for heart disease.

Each project has a clear notebook with EDA → preprocessing → baseline models → evaluation.

---

## Quick demo (TL;DR)
```bash
git clone https://github.com/cgamingpro/ML_Chekcks.git
cd ML_Chekcks
# create env, install deps, then open notebook
conda create -n ml_checks python=3.10 -y
conda activate ml_checks
pip install -r requirements.txt
jupyter notebook notebooks/01_property_price.ipynb
```

---

## Repo layout
```
ML_Chekcks/
├─ datasets/                # put CSVs here
│  ├─ property_price.csv
│  ├─ customer_churn.csv
│  └─ heart_disease.csv
├─ notebooks/
│  ├─ 01_property_price.ipynb
│  ├─ 02_customer_churn.ipynb
│  └─ 03_early_disease_detection.ipynb
├─ src/                     # reusable functions (data, models, utils)
├─ models/                  # saved model artifacts (.joblib)
├─ outputs/                 # plots, reports
├─ requirements.txt
├─ environment.yml
└─ README.md
```

---

## Datasets
Place CSVs in `datasets/` (local copies make experiments reproducible). Sources referenced in the project files:

- Property Price: Google Sheet — `1B9RTjgPSEWyQzDr-CQJmCYRriaBIaGq2WEkfp2TLTIA`  
- Customer Churn: Google Sheet — `1J2aMbLrRnk8g0Y5TSbz-en_7UxlI7xh0cLIZnIy4aew`  
- Heart Disease: Google Sheet — `10k1aWfHrvoXJrHxMz6F2nfK5-UlkCmQ8EjhUt9Casso`

(Prefer committing sanitized CSVs to `datasets/`.)

---

## Installation

### Conda (recommended)
```bash
conda env create -f environment.yml   # if provided
conda activate ml_checks
# OR
conda create -n ml_checks python=3.10 -y
conda activate ml_checks
pip install -r requirements.txt
python -m ipykernel install --user --name ml_checks --display-name "Python (ml_checks)"
```

### venv / pip
```bash
python -m venv .venv
# mac/linux
source .venv/bin/activate
# windows (PowerShell)
.\.venv\Scripts\activate
pip install -r requirements.txt
```

---

## Usage

1. Put dataset CSVs into `datasets/`.  
2. Open the notebook you want (Jupyter or VS Code).  
3. Select kernel `Python (ml_checks)` (or the env you created).  
4. Run cells top-to-bottom.

**Save models**
Notebooks save models to `models/` using `joblib.dump(...)`. Check `notebooks/*` to change paths.

---

## Notebook structure (consistent pattern)
1. Load / inspect dataset  
2. EDA (visuals + summary)  
3. Preprocessing (impute, encode, scale)  
4. Train baseline models (sklearn)  
5. Evaluate & compare (metrics + ROC/PR)  
6. Save final model and short write-up

---

## Metrics
- Regression: MAE, MSE, RMSE, R²  
- Classification: Accuracy, Precision, Recall, F1, ROC-AUC

---

## Development tips
- Clear outputs before committing (use `nbstripout`): reduces noisy diffs.  
- Put reusable code in `src/` and import from notebooks.  
- Pin package versions in `requirements.txt`.  
- Use `random_state=42` and document seeds in notebooks for reproducibility.

---

## Common fixes
- **Conda env not visible in VS Code:** run `python -m ipykernel install --user --name ml_checks` and restart VS Code.  
- **`conda` missing from PATH (Windows):** add your conda install path to `PATH` or reinstall Miniconda/Anaconda.

---

## Contribution
1. Fork → branch (`feat/xxx`) → PR.  
2. Keep notebooks runnable top→bottom.  
3. For new functions, add tests in `tests/` (optional).

---

## License
Add a LICENSE file (MIT recommended). This project is intended for learning and demo purposes.

---

## Contact
**Author:** cg — open an issue in the repo or ping me in the repo discussions for help.
