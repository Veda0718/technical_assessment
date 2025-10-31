# Hospital Readmission Prediction & Clinical Text Extraction

## Overview
This repository contains my submission for the **Data Science & LLM Technical Assessment**.  
The goal was to build a system that:
1. Predicts whether a patient will be **readmitted within 30 days** using structured clinical data.  
2. Extracts and categorizes **key clinical entities** from discharge notes using NLP/LLM methods.

## Setup & Execution

#### 1. Clone the repository
```bash
git clone https://github.com/Veda0718/technical_assessment.git
cd technical_assessment
```

#### 2. Install dependencies
```bash
pip install -r requirements.txt
```

#### 3. Run the notebook
Open and execute **_Data Science Assignment.ipynb_**, which walks through each step of the analysis.

## Project Workflow
#### Task 1 – Predicting 30-Day Readmissions
- EDA & Feature Engineering:
  - Cleaned and explored the dataset (200 records, 9 features)
  - Engineered stay_per_admission and age_bin features to capture clinical patterns
  - Handled class imbalance using SMOTE
- Models Tested: Logistic Regression, Decision Tree, Random Forest, XGBoost
- Evaluation Metrics: ROC-AUC, F1-Score, Confusion Matrix
- Best Model: Decision Tree – selected for strong performance, interpretability, and robustness with small, categorical data

#### Task 2 – Clinical Text Extraction (NLP / LLM)
- Pipeline Design: Two-step approach for modularity and precision.
- Entity Extraction: Using Flan-T5 to identify diagnoses, symptoms, treatments, medications, and follow-up actions.
- Entity Categorization: Using GPT-4o to classify extracted phrases into structured clinical categories.
- Outcome: Structured, labeled output that converts free-text notes into machine-readable data for downstream analysis.

## Results & Insights
- Top Predictive Features: stay_per_admission, length_of_stay, num_previous_admissions, age_bin_senior, gender_male.
- Key Insight: Patients with longer or more frequent hospitalizations are at higher risk of 30-day readmission.
- NLP Pipeline: Successfully extracted structured entities from discharge notes, enabling better clinical summarization and data mining.

The detailed summary, including methodology, results, clinical interpretation, and future improvements, is available in **_Final report.pdf_**
