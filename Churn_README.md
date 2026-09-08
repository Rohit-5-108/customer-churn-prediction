# Customer Churn Prediction

Predicts whether a telecom customer will cancel their service, using the IBM Telco Customer Churn dataset (7,043 customers). Built to be simple end to end — two models, no tuning, no advanced interpretability tools — so every line is something you can explain in your own words.

## Files
| File | Purpose |
|---|---|
| `Churn_Prediction.ipynb` | The project — already run, with outputs. Walk through this in an interview. |
| `data/telco_churn.csv` | Raw dataset |

## What it does, in one line each
1. Loads 7,043 customer records; ~26.5% churned.
2. Fixes 11 rows where `TotalCharges` was blank text instead of a number.
3. Converts text columns (Yes/No, contract type, etc.) into 0/1 columns.
4. Trains Logistic Regression and a shallow Decision Tree; keeps whichever tests better.
5. Looks at the confusion matrix and the model's coefficients to see what drives churn.

## Results
| Model | Accuracy |
|---|---|
| Logistic Regression | **0.803** |
| Decision Tree (max_depth=5) | 0.778 |

Final model: Logistic Regression — 80.3% accuracy. On the churn class specifically: 65% precision, 57% recall (open the notebook for the full report).

**Biggest finding:** customers on **month-to-month contracts** churn far more than those on 1- or 2-year contracts — the single clearest driver in the whole dataset.

## Resume bullet
> Built a customer churn prediction model on 7,000+ telecom customer records using Logistic Regression and Decision Tree classifiers, achieving 80% accuracy and identifying contract type and tenure as the leading churn drivers.

## If asked about it — keep answers this simple
- **"Walk me through your project"** → load data, noticed ~26% churn, cleaned a few bad rows, turned categories into numbers, trained two models, compared accuracy, looked at which features mattered.
- **"Why two models?"** → wanted to compare a simple linear approach against a simple rule-based one, and pick whichever generalized better on unseen data.
- **"Why Logistic Regression won"** → say it plainly: it tested slightly higher on this data. You don't need a deeper theory than that unless pushed — and if pushed further than you're prepared for, it's fine to say you'd want to try more models/tuning with more time.
- **"What would you improve with more time?"** → try Random Forest, handle the class imbalance more carefully (recall on churners is the weak point), tune hyperparameters.

Keep this project to a single, honest bullet on your resume — one clean line is safer than an over-decorated one you can't back up.
