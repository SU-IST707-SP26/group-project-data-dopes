# Vision.md

## Current Version

### Project: Beyond Default Prediction: A Risk-Adjusted Approach to Loan Optimization
**Primary Stakeholders:** A mid-size financial institution seeking to responsibly expand access to credit for underserved borrowers while maintaining financial stability

**Problem Statement:**
Traditional lending models focus primarily on predicting default and making approve-or-deny decisions. However, default prediction alone does not determine whether a loan will be profitable. Lenders must also consider how loan size and structure affect expected financial return given their risk tolerance. This is particularly important for borrowers with limited credit histories or lower credit scores, who are often excluded under rigid approval rules.

**Solution:**
We will build a predictive model to estimate probability of default and integrate these estimates into an actuarial framework that assigns a dollar value to each loan profile. For each combination of loan amount and repayment method, we will estimate expected interest income, expected losses from default, and overall net expected value.

Rather than treating lending as a binary decision, we will simulate how different loan amounts affect expected profitability and identify loan structures that align with a lender's specified level of risk tolerance.


---

## Version History

### Version 1.0 - Initial Vision (02-02-2026)

#### Project: Predicting Loan Deafult Risk: A Data-Driven Approach to Responsible Lending
**Primary Stakeholder:** Financial institutions making loan approval decisions

**Problem Statement:**
Lending institutions need to assess the risk that a loan applicant will default, but traditional decision rules and limited indicators can lead to inconsistent and inaccurate outcomes. This makes it difficult to balance financial risk with fair access to credit.

**Solution:**
We will build a machine learning model that predicts whether a loan applicant is likely to repay or default using historical loan data. The model will compare a simple baseline approach with more advanced techniques to improve prediction quality, with a focus on metrics appropriate for imbalanced data. The goal is to support more accurate, consistent, and responsible lending decisions.
