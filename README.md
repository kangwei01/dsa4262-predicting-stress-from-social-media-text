Stress Detection in Reddit Posts (Dreaddit)

This repository contains a Jupyter Notebook project that builds and analyses machine learning models to detect stress signals in Reddit posts using the Dreaddit dataset. The notebook covers the full workflow from exploratory data analysis (EDA) to modelling, evaluation, interpretability, and ethical reflection in a mental health context.

Repository Structure

.
├── README.md
├── requirements.txt
├── predicting-stress-from-social-media-text.ipynb
└── data/
  ├── dreaddit-train.csv
  └── dreaddit-test.csv

File / Folder Descriptions
 • predicting-stress-from-social-media-text.ipynb
Main notebook containing:
 • Exploratory data analysis (dataset structure, label balance, subreddit composition, text length, sentiment, and selected lexical features)
 • Text-only baseline model (TF-IDF + Logistic Regression) with grid search and stratified cross-validation
 • Model evaluation on the held-out test set (F1-score, classification report, confusion matrix)
 • Model analysis (top predictive words, per-subreddit performance, qualitative error analysis, annotator confidence analysis)
 • Final combined model integrating TF-IDF text features with engineered psychological and behavioural features
 • data/
Contains the Dreaddit dataset splits used in the project:
 • dreaddit-train.csv: training data
 • dreaddit-test.csv: held-out test data
 • requirements.txt
Lists the Python packages required to run the notebook.
 • README.md
Overview of the project, repository structure, and instructions to reproduce the results.

How to Reproduce / Run the Project
 1. Create and activate a virtual environment (recommended)

macOS / Linux:
python3 -m venv .venv
source .venv/bin/activate

Windows (PowerShell):
python -m venv .venv
.venv\Scripts\Activate.ps1
 2. Install dependencies
pip install -r requirements.txt
 3. Launch Jupyter Notebook
jupyter notebook
 4. Open and run the notebook
Open:
predicting-stress-from-social-media-text.ipynb

Run all cells from top to bottom to reproduce the full analysis, modelling pipeline, and results.

Notes
 • The notebook uses the predefined Dreaddit train/test split to ensure fair and unbiased evaluation.
 • Hyperparameter tuning is performed only on the training data using stratified cross-validation.
 • The held-out test set is used strictly for final performance reporting and comparison between models.