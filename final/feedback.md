This is one of the most ambitious projects I've seen this semester. A lot of what you've done (calibration, LGD estimation, the actuarial PD/LGD/EAD decomposition, expected-profit decision frameworks) is material that goes well beyond what we covered in class. I'm really happy with this.

The problem framing — "go beyond approve/deny to right-size loans for underserved borrowers" — is also exactly the kind of stakeholder-aligned reformulation I had hoped you produce. This is a lot more than a classifier.

That said, there are some methodological issues worth flagging. I'll summarize main strengths and weaknesses below:

## Strengths

- **Probability calibration is sophisticated.** Recognizing that downstream financial calculations need calibrated probabilities is exactly right. Happy to see you try both Platt scaling and isotonic regression and compare calibration curves.
- **LGD by sub-grade.** Computing recovery rates from actual data and stratifying LGD across loan grades is much more rigorous than using a single average. Captures heterogeneity.
- **Data leakage discipline.** Glad to see you Identified and dropped post-origination features for training, but brought them back for financial modeling 
- **Risk segmentation analysis.** The table showing how the optimizer behaves differently across PD segments (low risk +22%, very high risk −50%) is nice.
- **Clean writeup and notebook organization.** The supporting files index is helpful, the notebooks are clearly named, and the narrative flows from data through modeling to policy.
- **The expected-profit framework itself is correctly formulated.** Expected Loss = PD × LGD × Loan Amount matches the standard actuarial decomposition you cited.

## Weaknesses

I'm flagging these because they are subtle - you note some of this in the limitations, but the problems are a bit more significant that stated. 

- **The proportional PD adjustment is the central issue.** The simulation scales each borrower's PD linearly with the loan size multiplier (capped at 1.0), and you describe this as "validated" by loan amount being important in the XGBoost model. It isn't — feature importance tells you loan amount accounts for the most variance in PD, but tells you nothing about the *functional form* of that variation. It could be linear, stepwise, U-shaped, or interaction-dependent. The correct approach was available to you: re-predict PD using the trained XGBoost model with the simulated loan amount substituted into each feature vector. You mention this as future work, but it's really the central thing you should have done. The qualitative direction (bigger loans -> more risk) is probably right, but the magnitudes — and therefore the $47M gain and 139% lift figures — rest on a relationship the model never actually estimated.

- **The calibration story is incomplete.** Recall of 0.68 looks impressive, but `scale_pos_weight` was inflating the predicted probabilities, so lots of records ended up above the 0.5 threshold. Calibration corrected this — most calibrated probabilities are now well below 0.5 (because the true default rate is 20%), so recall at threshold 0.5 plummets to 0.10. The honest recall number is at each model's optimal threshold (you did find that — 0.23 -> F1 0.452). The downstream simulation uses calibrated probabilities, which is correct, but the Results section narrative "we get 0.68 recall" is misleading. Calibration didn't break the model; it exposed that the apparent recall came at a threshold where the probability scores weren't trustworthy.

- **No baseline comparison for the policy outcomes.** "139% profit lift" sounds great but compared to what? Some natural counterfactuals you could have run: reduce all loans uniformly by 25% (no model needed); approve only loans where PD < threshold X (simpler rule); use uncalibrated PDs in the same optimizer. Without these, the lift claim has no anchor.

- **Random 70/30 split rather than out-of-time validation.** Lending Club data spans many years across different macroeconomic conditions. A random stratified split lets the model see loans from later periods when learning about earlier ones. For credit risk specifically, the right validation is temporal — train on early years, test on later. Both PD and LGD estimates may not generalize across regimes; out-of-time evaluation would have stress-tested this.

- **The "5.6 percentage point default rate reduction" is computed on a filtered population.** Just s reporting nit here - the original policy approves all ~88K underserved borrowers (DR 23.7%); optimized approves ~68K (DR 18.1%). The average DR naturally drops when you remove the highest-risk borrowers from the denominator; this is just due to more conservative selection, but not an "improvement" per se. The fair comparison is total expected loss across the full subgroup (which you do report and is genuinely better).

- **EDA created late in the project, by your own admission.** Also just a note doing EDA after modeling is methodologically backwards — patterns you find post-hoc to support a conclusion you've already drawn aren't quite the same as patterns that informed feature engineering and model design. This really matters in a real research workflow.

## Summary

All in all, a lot of good thought and effort here.  There are some errors, but I've sought to flag the methodological problems so you can learn from them.  Strong work. 


**Team Score: 28/30**


---

## Final Project Grade
| Assessment Item | Hazem Ahmed | Kasem Chaisathitwanit | Ashish Chaudhary | Prerna Bharti |
|---|---|---|---|---|
| **Proposal (5 pts)** | 5 | 5 | 5 | 5 |
| **Midterm Report (10 pts)** | 10 | 10 | 10 | 10 |
| **Final Presentation (5 pts)** | 5 | 5 | 5 | 5 |
| **Final Report (30 pts)** | 28 | 28 | 28 | 28 |
| **Weekly Updates (30 pts)** | 30 | 30 | 30 | 28 |
| **Total (80 pts)** | **78** | **78** | **78** | **76** |
