# WORKLOG.md

## 04-17-2026 - Loan Size Optimization and Policy Comparison (Team)

**Context:** Compared optimized loan amounts against original loan decisions to evaluate the impact of the risk-adjusted lending policy on borrower-level loan sizing and portfolio structure.

**Work Completed:**
- Created simulated loan size grid and recalculated key financial ratios (Hazem)
- Recalculated expected revenue, loss, and profit for each simulated loan size using PD and LGD (Kasem)
- Introduced risk-adjusted objective function incorporating default risk and borrower affordability constraints (Ashish)
- Identified profit-maximizing loan size per borrower based on objective score and applied profitability constraints (Prerna)
- Created loan difference and percentage change columns to compare optimized vs original loan amounts (Kasem)
- Analyzed loan size adjustments using multiplier distribution and segment-level summaries across risk groups (Kasem)

**Files Created:**
- `Policy_Simulation.ipynb`

**Impact:** Quantified how the optimized lending policy reshapes loan sizing across risk segments, showing systematic adjustments toward higher or lower loan amounts based on risk-adjusted profitability (M5.T1 through M5.T5 complete)


## 04-10-2026 - Expected Profit Modeling and Portfolio Analysis (Team)

**Context:** Developed and validated expected profit framework using model outputs to support loan-level decision making and portfolio analysis.

**Work Completed:**
- Calculated Loss Given Default (LGD) using recovery-based approach on defaulted loans (Kasem)
- Analyzed and visualized LGD distribution overall and by loan sub-grade (Kasem)
- Mapped expected LGD by sub-grade into policy dataset with fallback to overall mean (Hazem)
- Computed expected revenue, loss, and profit for each borrower using predicted default probabilities (PD) and LGD (Hazem)
- Validated expected profit calculations using test cases across different risk levels (Prerna)
- Generated summary statistics of expected profit distribution (e.g., mean, median, total profit) (Prerna)
- Created visualizations to analyze profit distribution, risk-return patterns, and portfolio performance (Ashish)

**Files Created:**
- `lgd_by_grade.png`
- `lgd_distribution_by_grade.png`

**Impact:** Established a risk-adjusted profit framework and provided insights into portfolio performance, enabling more informed lending and policy decisions (M4.T3 through M4.T6 complete)


## 04-06-2026 - Financial Feature Engineering and Policy Simulation Prep (Team)

**Context:** Began preparing dataset and framework for loan optimization and policy simulation.

**Work Completed:**
- Ran Breusch-Pagan test to check for heteroskedasticity (Hazem)
- Recomputed dataset to include required variables for policy simulation (Kasem)
- Generated updated test set using new dataset (Kasem)
- Created initial financial ratio features for modeling (Hazem)
- Implemented loan revenue calculation for optimization framework (Ashish)

**Files Created:**
- `Data_Prep_for_Policy_Simulation.ipynb`

**Impact:** Established foundation for policy simulation and financial modeling; feature engineering still in progress (M3.T6 through M4.T2 complete)


## 03-26-2026 - Probability Calibration and Threshold Optimization (Prerna)

**Context:** Improved reliability of predicted probabilities from the XGBoost model to better support financial decision-making and risk-based optimization.

**Work Completed:**
- Applied probability calibration using Platt Scaling (sigmoid) and isotonic regression (Prerna)
- Generated calibration curves to compare results (Prerna)
- Evaluated calibrated models and optimized classification threshold to maximize F1-score (Prerna)

**Files Created:**
- `work/xgb_evaluation.png`
- `work/xgb_feature_importance.png`

**Impact:** Calibration improved probability alignment, but overall model performance remained largely unchanged with only minor gains (M3.T5 complete)


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
