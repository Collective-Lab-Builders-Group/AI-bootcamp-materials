# Day 2 — Basic Model Building (and the things to know)

**Self-paced, ≈3–4 hours.** Day 1 gave you a first model on small, clean data. Today you run the same loop on messier, realistic data — and learn the habits that separate a *lucky* score from a *trustworthy* one.

## What you'll be able to do after today

- Load a real CSV, choose features (`X`) and target (`y`), and split correctly (`stratify`, `random_state`)
- Preprocess without cheating: impute missing values, one-hot encode text, scale — **fit on train only** (data leakage!)
- Build **five models** and compare them: baseline, logistic regression, KNN, decision tree, random forest (+ a regression example)
- Evaluate honestly: accuracy **and** precision/recall/F1, the confusion matrix, MAE/RMSE/R²
- Spot **overfitting** with the train↔test gap, judge models with **cross-validation**, bundle everything in a **pipeline**, and **save** a trained model

## Before you start

- **Day 1 is done** (tools work, notebook finished). If not, go back to [`../Day 1/`](../Day%201/).
- To open the notebook: upload `model_building_basics.ipynb` to **[Google Colab](https://colab.research.google.com)** (File → Upload notebook) or **[Kaggle](https://www.kaggle.com/code)** (File → Import Notebook) — or locally: `conda activate bootcamp`, then `jupyter lab`.

## The plan

1. **(≈2–2.5 h)** Work through [`model_building_basics.ipynb`](model_building_basics.ipynb) **top to bottom**. Every cell is written to teach itself: read the text cell, run the code cell, then tweak a number and re-run to see what changes. The notebook even generates and saves its own CSV file (`customers.csv`), so you practice the real Kaggle flow of reading data from a file.
2. **(≈45–60 min)** Do the **exercises** at the end of the notebook. Exercise 5 — a full run-through on the real Titanic dataset — is the best practice there is.

## Done when ✅

- [ ] The notebook runs top to bottom without errors
- [ ] You can explain **data leakage** in two sentences (and why preprocessing is fitted on train only)
- [ ] You can name a metric for when accuracy lies — and why
- [ ] You can point at the train↔test gap in the depth sweep and say which tree overfit
- [ ] Exercises 1–3 are attempted

## Resources

- **scikit-learn — Getting Started** (official): <https://scikit-learn.org/stable/getting_started.html>
- **Kaggle Learn — Intro to Machine Learning** (free, hands-on, notebook-based): <https://www.kaggle.com/learn/intro-to-machine-learning>
- **Kaggle Learn — Intermediate Machine Learning** (the natural next step: missing values, pipelines, cross-validation): <https://www.kaggle.com/learn/intermediate-machine-learning>
- **Google ML Crash Course** (concepts, videos, visualisations): <https://developers.google.com/machine-learning/crash-course>
- **StatQuest with Josh Starmer** (the best plain-English explanations of ML ideas, on YouTube): <https://www.youtube.com/@statquest>
