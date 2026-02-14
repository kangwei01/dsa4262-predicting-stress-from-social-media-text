````md
# Stress Detection in Reddit Posts (Dreaddit)

**Author:** Fong Kang Wei

This repository contains a Jupyter Notebook project that builds and analyses machine learning models to detect stress signals in Reddit posts using the Dreaddit dataset. The notebook follows an end-to-end workflow: EDA → text-only baseline → model analysis → combined model → interpretability and ethics.

---

## Repository Structure

```
.
├── README.md
├── requirements.txt
├── predicting-stress-from-social-media-text.ipynb
└── data/
    ├── dreaddit-train.csv
    └── dreaddit-test.csv
```

---

## What’s Inside

### predicting-stress-from-social-media-text.ipynb
Main notebook containing:
- Exploratory Data Analysis (dataset structure, label balance, subreddit composition, text length, sentiment, selected LIWC/DAL features)
- Text-only baseline model using TF-IDF + Logistic Regression  
  - Grid search with stratified cross-validation  
  - Evaluation on held-out test set (F1, classification report, confusion matrix)
- Model analysis and sense-making  
  - Top predictive lexical cues  
  - Per-subreddit performance and stress prevalence analysis  
  - Qualitative error analysis  
  - Annotator confidence vs misclassifications
- Final combined model using TF-IDF text + engineered features (LIWC, sentiment, readability, social metrics, text length)  
  - Direct comparison against baseline, including error types and rates

### data/
- dreaddit-train.csv: training dataset
- dreaddit-test.csv: held-out test dataset

### requirements.txt
List of Python dependencies required to run the notebook.

---

## How to Run / Reproduce

### 1) Create a virtual environment (recommended)

macOS / Linux:
```bash
python3 -m venv .venv
source .venv/bin/activate
```

Windows (PowerShell):
```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

### 2) Install dependencies
```bash
pip install -r requirements.txt
```

### 3) Launch Jupyter
```bash
jupyter notebook
```

### 4) Run the notebook
Open `predicting-stress-from-social-media-text.ipynb` and run all cells from top to bottom to reproduce:
- EDA visualisations and summary tables
- Baseline model training and evaluation
- Subreddit-level and error analyses
- Combined model training and performance comparison
- Feature importance and interpretability outputs

---

## Notes
- The predefined train/test split is used for fair and unbiased evaluation.
- Hyperparameter tuning is performed only on the training set using stratified cross-validation.
- The test set is reserved exclusively for final performance reporting and model comparison.
