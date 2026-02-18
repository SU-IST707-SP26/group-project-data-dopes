# Predicting Loan Deafult Risk: A Data-Driven Approach to Responsible Lending

## Team Members
 Point of Contact: Ashish Rajeev Chaudhary ( AshishRChaudhary )
 
 Hazem Ani (hazemani), Kasem Chaisathitwanit (LuckyFriend), Prerna Bharti (PrernaBharti28)



## Introduction

Lending institutions face an ongoing challenge in deciding which applicants are likely to repay their loans and which may default. These decisions have real financial consequences and directly affect who gains access to credit. While most lenders already use models to estimate default risk, these tools are often designed to minimize losses rather than explore how credit can be extended more responsibly. This is especially important for borrowers with limited credit histories or lower credit scores, who are frequently denied loans under traditional approval rules.

This project focuses on a specific stakeholder: a mid-size lender seeking to responsibly expand access to credit for underserved borrowers while maintaining financial stability. We propose to develop a predictive model that estimates the likelihood of default using historical loan data, with particular attention to borrowers who may not fit neatly into standard credit categories. Rather than stopping at prediction alone, we aim to use these risk estimates to inform lending decisions.

Beyond identifying which borrowers are more likely to default, the project will examine how loan size affects both expected returns and potential losses. Instead of treating lending as a simple approve-or-deny decision, we will consider how different loan amounts may change the balance between risk and reward. By estimating the expected financial value of a loan over time, we can explore how a lender might choose loan amounts that align with a given level of risk tolerance.

If successful, this project will demonstrate how predictive modeling can be combined with practical decision-making tools to create more flexible and inclusive lending strategies. By moving beyond default prediction to evaluate how loans should be structured, the analysis aims to support lending practices that are both financially sound and socially responsible.

## Literature Review
Loan default prediction is usually treated as a binary classification problem. Traditional approaches commonly use logistic regression because it is easy to interpret and widely accepted in financial institutions. More recent research shows that machine learning models such as random forests and gradient boosting can improve prediction performance, especially in terms of ROC-AUC.[^1] However, most studies mainly focus on improving accuracy rather than examining the financial impact of lending decisions.

In practice, lenders use an actuarial framework that combines Probability of Default (PD), Loss Given Default (LGD), and Exposure at Default (EAD) to calculate expected loss.[^2] Even so, lending decisions are often reduced to simple cutoff rules, where borrowers are either approved or denied based on predicted risk. Loan size is usually treated as fixed, and there is limited discussion on how adjusting loan amounts could better balance risk and return.

For a mid-size lender that wants to expand access to underserved borrowers, this creates a real challenge. The lender needs to balance two goals: giving more people access to credit while also protecting the company from financial losses. This means they need a model that does more than just predict whether someone will default. The model should also help the lender understand how much money they might gain or lose from each loan. Instead of simply approving or rejecting applicants based on a strict cutoff, the lender could adjust the loan amount based on the borrower’s risk level. This approach could allow more borrowers to receive credit while still keeping the lender financially stable.

While prior research provides strong methods for predicting default, fewer studies connect those predictions to loan-size optimization under clear risk tolerance assumptions. This project aims to bridge that gap by combining default prediction with expected financial value calculations to support more flexible and responsible lending strategies.

## Data & Methods

<b>Dataset URL:</b> https://www.kaggle.com/datasets/nikhil1e9/loan-default

<b>Summary:</b> The dataset contains 255,347 rows and 18 columns in total.

<img width="900" height="550" alt="image" src="https://github.com/user-attachments/assets/2bbf7382-2b4d-441f-86d8-b62e8e4add56" />

### Data Provenance:<br>
Source -> https://www.coursera.org/projects/data-science-coding-challenge-loan-default-prediction<br>
License -> <a href="https://creativecommons.org/publicdomain/zero/1.0/"> CC0: Public Domain </a> [No Copyright]<br>
<i>The person who associated a work with this deed has dedicated the work to the public domain by waiving all of his or her rights to the work worldwide under copyright law, including all related and neighboring rights, to the extent allowed by law.
You can copy, modify, distribute and perform the work, even for commercial purposes, all without asking permission. See Other Information below.</i>

### Methods<br>
Since loan default prediction involves a binary target, this problem is treated as a classification task. We will begin with a baseline model using logistic regression and then apply more advanced models, including decision trees, random forests, XGBoost, and Support Vector Machine (SVM). Before modeling, the data will be preprocessed by handling missing values, encoding categorical variables, and scaling numerical features when necessary. Model performance will be evaluated using k-fold cross-validation, and we will report the average F1-score and ROC-AUC across folds.

## Project Plan

Period|Activity|Milestone
|---|---|---|
|2/2 - 2/16|Stakeholder Analysis </br> Project Planning|Completed stakeholder analysis and defined project scope
|2/17 - 3/2|EDA on Loan Dataset|Data cleaned, initial patterns and anomalies identified
|3/3 - 3/16|Initial Modeling Experiments (logistic regression, random forest, etc.)|First pass of predictive modeling completed
|3/17 - 3/3|Preprocessing Refinements </br> Testing Candidate Models|Candidate approaches for modeling finalized
|3/31 - 4/13|Model Evaluation|Best performing model identified
|4/14 - 4/27|Finalize Results </br> Prepare Project Report & Presentation| Project report drafted and presentation prepared



## Risks

### 1. Overfitting/Poor generalization

**Risk:**  
Tree-based ensemble models may overfit the training data due to excessive model complexity.

**Mitigation:**  
- Restricted tree depth (`max_depth`)
- Increased minimum samples per leaf (`min_samples_leaf`)
- Preference for shallow trees with more estimators

### 2. Data Leakage

**Risk:**  
Use of future or target-related information during training results in overly optimistic model performance.

**Mitigation:**  
- Train–test split performed prior to preprocessing
- Scaling, encoding, and imputation fitted only on training data
- Exclusion of target-derived features

### 3. Class Imbalance

**Risk:**  
Model bias toward the majority class leads to poor minority-class performance.

**Mitigation:**  
- Stratified train–test splits
- Resampling techniques (SMOTE, undersampling)

 ### 4. Computational Constraints

**Risk:**  
Large ensemble models can be computationally expensive.

**Mitigation:**  
- Limiting the number of estimators
- Feature dimensionality reduction (PCA)
- Early stopping
- Dataset sampling for large-scale data

[^1]:[Y. Zhou, Loan Default Prediction Based on Machine Learning Methods, Proceedings of the 3rd International Conference on Big Data Economy and Information Management (BDEIM 2022)](https://eudl.eu/doi/10.4108/eai.2-12-2022.2328740)

[^2]:[Expected Loss (EL): Overview, How to Calculate, Importance in Credit Risk Management](https://corporatefinanceinstitute.com/resources/career-map/sell-side/risk-management/expected-loss-definition-calculation-importance/?utm_source=chatgpt.com)
