# Fast-track roadmap (about 5 to 6 hours a day, finish in 9 days)

Rule: do not skip the PLAN.md commit. Everything else can compress.

| Day | Hours | Do | Done when |
|---|---|---|---|
| 1 | 4 | Install Python and Git, push this folder to GitHub. Skim TRIPOD+AI (read the checklist, not every paper). Read Van Calster et al. on calibration. | Repo is public. You can say what a calibration slope of 1 means. |
| 2 | 5 | Learn pandas basics. Do the 10-patient practice exercise until you match 0%, 67%, 33%, 50%, 1.0, 0.67. | All six numbers match. |
| 3 | 5 | Fill in PLAN.md completely, including fairness metrics and the monitoring rule. Send it for review. Commit it. | Timestamped commit before any data is opened. |
| 4 | 5 | Notebook steps 0 to 3: load, define outcome, clean, split. | Exclusions table and patient-level split done. |
| 5 | 6 | Step 4: fit both models and output probabilities. Overall AUROC and calibration plot. | Plots saved to figures/. |
| 6 | 6 | Steps 5 and 6: calibration slope and intercept by race, interaction test. | The primary result table exists. |
| 7 | 6 | Step 7: AUROC, fairness metrics, decision curve, all labeled exploratory. | One table per metric family. |
| 8 | 5 | Step 8: R cross-check. Step 9: monitoring rule. Step 10: limitations. | Python and R agree, or you can explain why not. |
| 9 | 5 | README, one-page brief, clean the code, fresh-clone test. Add link to resume and letter. | A reader understands it in five minutes. |

If you fall behind, cut in this order: decision-curve analysis, payer strata, gradient boosting.
Never cut: PLAN.md commit, calibration by race, the limitations section.
