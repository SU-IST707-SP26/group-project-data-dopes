# Work Plan

## Active Tasks

### Milestone 1: Data Acquisition & Cleaning (2/18/26 - 3/2/26)
- [✅] M1.T1 - Refine stakeholder decision problem and define objective function (Team)
- [✅] M1.T2 - Download and load Lending Club dataset into project environment (Hazem)
- [✅] M1.T3 - Remove columns with greater than 30% missing values (Kasem)
- [⏳] M1.T4 - Identify and remove non-predictive or irrelevant columns (Team)
- [] M1.T5 - Implement missing value imputation strategy
- [] M1.T6 - Encode categorical variables
- [] M1.T7 - Create finalized modeling dataset and save cleaned version

### Milestone 2: Data Cleaning & Preprocessing (3/3/26 - 3/12/26)
- [ ] M2.T1 - Create financial ratio features (DTI, income-to-loan ratio, etc.)
- [ ] M2.T2 - Scale/normalize numerical features where necessary
- [ ] M2.T3 - Split data into training and test sets
- [ ] M2.T4 - Address class imbalance (class weights or resampling method)

### Milestone 3: Probability of Default Modeling (3/13/26 - 3/23/26)
- [ ] M3.T1 - Train baseline logistic regression model
- [ ] M3.T2 - Train tree-based model (Random Forest or Gradient Boosting)
- [ ] M3.T3 - Perform cross-validation on candidate models
- [ ] M3.T4 - Evaluate models using ROC-AUC, Precision-Recall, and F1-score
- [ ] M3.T5 - Calibrate predicted probabilities (Platt scaling or isotonic regression)
- [ ] M3.T6 - Select final model and export predicted probabilities

### Milestone 4: Financial Model Construction (3/24/26 - 4/3/26)
- [ ] M4.T1 - Implement loan revenue calculation function (based on amount, rate, term)
- [ ] M4.T2 - Implement Loss Given Default (LGD) assumption or calculation
- [ ] M4.T3 - Compute expected profit for each borrower using PD outputs
- [ ] M4.T4 - Validate expected profit outputs using test cases
- [ ] M4.T5 - Generate summary statistics of expected profit distribution

### Milestone 5: Loan Size Simulation & Optimization (4/4/26 - 4/14/26)
- [ ] M5.T1 - Create simulated loan size grid
- [ ] M5.T2 - Recalculate expected profit for each simulated loan size
- [ ] M5.T3 - Introduce risk-adjusted objective function
- [ ] M5.T4 - Identify profit-maximizing loan size per borrower
- [ ] M5.T5 - Compare optimized loan sizes to original loan amounts

### Milestone 6: Subgroup & Policy Analysis (4/15/26 - 4/22/26)
- [ ] M6.T1 - Filter dataset for underserved borrower subgroup
- [ ] M6.T2 - Compare expected profit before vs after optimization for subgroup
- [ ] M6.T3 - Compare default rates under traditional approval vs optimized strategy
- [ ] M6.T4 - Generate visualizations (profit curves, risk-return tradeoff plots)
- [ ] M6.T5 - Summarize key policy findings in written format

### Milestone 7: Presentation Preparation (4/23/26 - 4/27/26)
- [ ] M7.T1 - Create final presentation slides
- [ ] M7.T2 - Integrate charts and optimization visuals
- [ ] M7.T3 - Draft presentation script
- [ ] M7.T4 - Present findings

### Milestone 8: Final Report Completion (4/28/26 - 5/6/26)
- [ ] M8.T1 - Write Introduction section
- [ ] M8.T2 - Write detailed methodology section
- [ ] M8.T3 - Write results and interpretation section
- [ ] M8.T4 - Document assumptions and limitations
- [ ] M8.T5 - Compile appendix (code references, robustness checks)
- [ ] M8.T6 - Final proofreading and submission
