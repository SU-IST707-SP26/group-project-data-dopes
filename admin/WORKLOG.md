# WORKLOG.md

## 03-22-2026 - Tree-Based Model Development (XGBoost) (Team)

**Context:** Implemented a tree-based model and further evaluated baseline performance for predicting loan outcomes.

**Work Completed:**
- Trained XGBoost model using same preprocessing pipeline (Ashish)
- Evaluated XGBoost using ROC-AUC, confusion matrix, and classification metrics (Ashish)
- Analyzed feature importance from XGBoost model (Ashish)
- Performed cross-validation on logistic regression model (Hazem)
- Calculated mean CV F1-score and ROC-AUC for baseline model (Hazem)
- Compared XGBoost performance to logistic regression baseline (Team)

**Files Created:**
- `work/XGBoost_model.ipynb`

**Impact:** Found similar performance between XGBoost and logistic regression while improving evaluation of the baseline model (M3.T2 through M3.T4 complete)


## 03-06-2026 - Data Preparation and Baseline Model Development (Team)

**Context:** Prepared dataset for model training and developed the first baseline classification model for predicting loan outcomes.

**Work Completed:**
- Split data into training and test sets (Kasem)
- Repositioned missing value imputation within preprocessing pipeline (Prerna)
- Scaled/normalized numerical features (Ashish)
- Addressed class imbalance (Team)
- Trained baseline logistic regression model (Kasem)
- Briefly evaluated model using confusion matrix, classification report, ROC-AUC, and ROC Curve (Kasem)
- Completed and submitted mid-term project report (Team)

**Files Created:**
- `work/Default_Prediction.ipynb`
- `work/logistic_reg.ipynb`
- `checkpoint/submission.ipynb`

**Impact:** Established a baseline predictive model and evaluation framework to benchmark future model improvements (M2.T1 through M3.T1 complete)


## 03-04-2026 - Initial Data Cleaning and EDA (Team)

**Context:** Continued cleaning and preparation of the Lending Club dataset for modeling.

**Work Completed:**
- Removed columns with >30% missing values (Kasem)
- Dropped non-predictive and leakage variables (Team)
- Converted and encoded categorical variables (Hazem & Ashish)
- Implemented missing value imputation (KNN for numeric features, mode for categorical) (Prerna)
- Performed exploratory analysis using histograms and a correlation matrix (Kasem)

**Impact:** Cleaned and reduced dataset ready for modeling (M1.T3 through M1.T6 complete)


## 02-20-2026 - Project Kickoff (Team)

**Context:** Project scope expansion and restructuring

**Work Completed:**
- Set up repository structure (work/, admin/) (Hazem)
- Created and refined Vision.md and Workplan.md (Hazem)
- Downloaded Lending Club dataset from Kaggle (Hazem)
- Restructured project to align more closely with real-world applications (Team)

**Files Created:**
- `work/DataCleaning.ipynb`

**Impact:** Project infrastructure and goals in place.
