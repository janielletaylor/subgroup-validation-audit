# Pre-specified analysis plan

COMMIT THIS FILE BEFORE LOOKING AT ANY RESULTS. Fill every TODO in your own words.
Structure follows the TRIPOD+AI reporting statement (Collins et al., BMJ 2024;385:e078378).
After reading it, add the checklist item numbers next to each section below. Claim "reported
following TRIPOD+AI" in the README only if you complete the checklist.

## 1. Question
TODO: One sentence. Is a 30-day readmission risk model equally well calibrated across race and payer groups?

## 2. Setting and limits (state up front)
- Public data, 130 US hospitals, 1999-2008.
- The model is a stand-in for a deployed tool. This is not an audit of a real clinical AI product.
- No neighborhood deprivation variable is available.

## 3. Outcome
TODO: Define 30-day readmission from the `readmitted` column. State what counts as 1 and 0.

## 4. Unit and split
TODO: One row per patient (`patient_nbr`). Patient-level train/test split. State ratio and random seed.

## 5. Predictors and model
TODO: List predictors and say why. State whether race and payer are excluded from the model.
Models: logistic regression and gradient boosting. Output predicted probabilities (0 to 1), not 0-100 scores.

## 6. Strata
- Race (TODO: categories; how you handle small or missing groups)
- Payer (TODO: group `payer_code` into a few categories and justify)

## 7. PRIMARY comparison (one only)
Calibration slope, by race, on the held-out test set, with a test of whether the slope differs by race
(stratum-by-logit(predicted risk) interaction).
- Calibration slope: coefficient on logit(predicted probability) when you regress the outcome on it. Ideal = 1.
- TODO: In one sentence, say why calibration is primary and AUROC is secondary (an AUC alone can hide subgroup failure; Van Calster et al., BMC Med 2019).

## 8. Secondary analyses (label all as exploratory)
- Calibration intercept (calibration-in-the-large) by race.
- Same calibration metrics by payer.
- AUROC by race and by payer, with bootstrap confidence intervals.
- Fairness metrics (see section 9).
- Decision-curve analysis (net benefit) by stratum.

## 9. Fairness metrics to report
TODO: Choose and justify. Candidates: equalized odds (equal false-negative and false-positive rates across groups),
predictive parity (equal positive predictive value), calibration within groups.
For each chosen metric write one sentence on why it fits a readmission follow-up-call use case.
State the threshold you use to define "flagged" and why.

## 10. Hypotheses
- H0: calibration slope is homogeneous across strata (no interaction).
- H1: the slope differs by stratum.
- TODO: State in one sentence that finding no difference is a valid result.

## 11. Monitoring rule
TODO: Which metric, which threshold, how often reviewed, what triggers modification or retirement.
Use NIST AI RMF language where it helps (Govern, Map, Measure, Manage).

## 12. Multiplicity
One primary comparison. Everything else is secondary and exploratory.

## 13. Cross-check
TODO: Which two or three numbers you will recompute in R (for example overall AUROC, one calibration slope,
one false-negative rate) to confirm the Python results.
