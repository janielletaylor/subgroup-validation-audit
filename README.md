# Subgroup validation audit of a readmission model

**Question.** Is a 30-day readmission risk model equally well calibrated across race and insurance groups?

**Status.** TODO (in progress / complete, date).

## Summary
TODO: 3 sentences in plain language. Lead with the primary result, including a null result if that is what you found.

## Data
Diabetes 130-US Hospitals (UCI, 1999-2008). TODO: n patients, n encounters after exclusions.

## Method
1. Analysis plan committed before results (`PLAN.md`), structured around the TRIPOD+AI reporting statement. TODO: say whether you completed the checklist.
2. Patient-level train/test split.
3. Logistic regression and gradient boosting.
4. Primary analysis: calibration slope by race, with a race-by-log-odds interaction test.
5. Secondary analyses (exploratory): AUROC, fairness metrics, decision-curve analysis, with bootstrap CIs.
6. Python results cross-checked in R.
7. Monitoring rule.

## Results
TODO: primary comparison, then secondary. Embed figures from `figures/`.

## Limitations
- Data span 1999 to 2008 and come from a diabetes cohort.
- The model is a stand-in for a deployed tool, not a real clinical AI product.
- No neighborhood deprivation variable.
- TODO: add anything else you found.

## Reproduce
```
pip install -r requirements.txt
jupyter notebook notebooks/audit.ipynb
```

## Author
Janielle K. Taylor, MSPH
