# Stress Detection in Reddit Posts (Dreaddit)  
**DSA4262 – Individual Assignment 2**

This project develops and analyses interpretable machine learning models to detect stress signals in Reddit posts using the Dreaddit dataset. The workflow moves from exploratory data analysis to baseline modelling, detailed error and subgroup analyses, and finally a combined feature model that integrates psychological and behavioural indicators with textual features.

---

## Project Overview

Detecting stress from social media text is challenging because expressions of distress are often subtle, contextual, and narrative in nature. This project aims to build a transparent and methodologically rigorous modelling pipeline that not only achieves strong predictive performance but also explains *why* the model makes its decisions.

The analysis proceeds in several stages:

1. **Exploratory Data Analysis (EDA)**
   - Inspect dataset structure, label balance, and subreddit composition  
   - Analyse text length patterns, sentiment distributions, and selected psychological lexical features  
   - Understand how stress expression varies across different online communities  

2. **Text-Only Baseline Model**
   - Build a TF-IDF + Logistic Regression classifier  
   - Tune hyperparameters using grid search with stratified cross-validation  
   - Establish an interpretable lexical baseline for stress detection  

3. **Model Sense-Making Analyses**
   - Identify top predictive lexical cues for stressed vs non-stressed posts  
   - Compare performance across subreddits  
   - Conduct qualitative error analysis (false positives and false negatives)  
   - Examine the relationship between annotator confidence and misclassifications  

4. **Combined Feature Model**
   - Integrate engineered psychological and behavioural features (LIWC indicators, sentiment, readability, social metrics, text length) with TF-IDF text features  
   - Evaluate whether these features provide incremental predictive value beyond raw language  
   - Compare performance and error types against the baseline model  

5. **Interpretability and Ethics**
   - Analyse feature importance to understand the roles of lexical and engineered signals  
   - Discuss implications of false positives and false negatives in mental health contexts  
   - Reflect on responsible and human-in-the-loop deployment of stress detection systems  

---

## Repository Structure
```
.
├── predicting-stress-from-social-media-text.ipynb   # Main analysis and modelling notebook
├── data/
│   ├── dreaddit-train.csv   # Training split of Dreaddit dataset
│   └── dreaddit-test.csv    # Held-out test split
│
├── requirements.txt         # Python dependencies
└── README.md
```

The Dreaddit dataset splits are included directly in the `data/` folder to allow full reproducibility of all analyses and results.

---

## Dataset

### Dreaddit: Stress Analysis Dataset  
The Dreaddit dataset consists of Reddit posts labelled as **“Stressed”** or **“Not Stressed”**, along with annotator confidence scores and a range of pre-computed psychological, linguistic, and social features.

It includes:
- Raw post text
- Stress labels and annotator confidence
- Subreddit metadata
- LIWC-based psychological lexical features
- Sentiment scores
- Readability and syntactic complexity measures
- Social engagement metrics (e.g., upvote ratio, number of comments)

A predefined train/test split is provided and used to ensure fair and unbiased model evaluation.

---

## How to Reproduce the Analysis

### 1. Clone the repository

### 2. Create a virtual environment
```bash
python -m venv venv
source venv/bin/activate  # macOS/Linux
# venv\Scripts\activate   # Windows
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the notebook
```bash
jupyter notebook predicting-stress-from-social-media-text.ipynb
```

Run all cells sequentially to reproduce:
- EDA visualisations and summary statistics  
- Baseline model training and evaluation  
- Subreddit-level performance and error analyses  
- Combined model training and comparison  
- Feature importance and interpretability outputs  

---

## Author

**Fong Kang Wei**

