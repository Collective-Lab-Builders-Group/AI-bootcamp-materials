# Your Project = Your Assessment

The two self-paced days taught you the loop: **load → split → preprocess → fit → predict → evaluate**. Now the club wants to see you run that loop **on your own, end to end, on real data**. This project is the bootcamp's assessment — it decides whether you complete the programme — and it becomes the first piece in your portfolio.

You get **one week** after Day 2 (your club lead confirms the exact date). It is designed to take an evening or two, not a month.

## The brief

Pick **one dataset** you find interesting (Kaggle is the easiest place — ideas below). Then build **one notebook** that does all of the following, in order:

1. **Problem statement** — 3+ sentences at the top: what are you predicting, from what data, and why would anyone care?
2. **Explore the data (EDA)** — `df.info()`, `df.describe()`, a look at the target's balance (`value_counts`), and **at least 2 charts** (matplotlib) with labelled axes.
3. **Split correctly** — `train_test_split` with `random_state` (so it's reproducible) and `stratify=y` if it's a classification problem.
4. **Preprocess without leaking** — handle missing values, encode any text columns, scale if your model needs it. Everything is **fitted on the training set only**.
5. **Model against a baseline** — a `DummyClassifier` (or 'predict the average' for regression) **plus at least 2 real models**, compared in one table or loop.
6. **Evaluate honestly** — classification: accuracy **and** the confusion matrix with precision/recall/F1 · regression: MAE, RMSE, R². Include a **5-fold cross-validation** score for your best model.
7. **Check for overfitting** — show train vs test performance for at least one model and comment on the gap.
8. **Conclude** — 5+ sentences: which model won, by how much, what surprised you, what you would try next with more time.

## The rules

- **Your own work.** You may consult documentation, tutorials, and AI tools to *understand* things — but every line in the notebook must be something you can explain, because at a club meetup you may be asked to.
- **No copied full notebooks**, no auto-ML one-liners that skip the workflow. The point is the loop, not the leaderboard.
- **Cite your sources** (dataset link, any tutorial that helped) in the notebook.
- The notebook must **run top to bottom from a fresh kernel** without errors — restart and run all before you submit.

## Deliverables & how to submit

1. A **GitHub repository** named like `firstname-ml-project` containing:
   - your notebook (`.ipynb`) with all outputs visible,
   - a short `README.md`: the problem, the dataset link, your final result, and how to run the notebook.
2. **Push it to GitHub** — the Git guide at the root of [this repo](../README.md) covers everything you need (clone, add, commit, push).
3. Send the repo link through your club's submission channel *(club lead: fill in the link/form here)*.

> Tip: test your submission the way we will — open your GitHub repo, download the notebook, and run it in Colab. If it runs there, you're safe.

## Ideas (or bring your own dataset)

| Project | Link | Type |
|---|---|---|
| Titanic — who survived? | <https://www.kaggle.com/competitions/titanic> | classification |
| Telco customer churn (very close to Day 2's example!) | <https://www.kaggle.com/datasets/blastchar/telco-customer-churn> | classification |
| Palmer penguins — guess the species | <https://www.kaggle.com/datasets/parulpandey/palmer-archipelago-antarctica-penguin-data> | classification |
| House prices — predict the price | <https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques> | regression |
| Student exam scores — predict performance | <https://www.kaggle.com/datasets/spscientist/students-performance-in-exams> | regression / classification |

Any dataset works if it has **at least ~500 rows**, a target you can define in one sentence, and at least one text column or some missing values — wrestling with those is part of the exercise.

## How you'll be graded (20 points)

| Criterion | Points |
|---|---|
| Notebook runs top to bottom from a fresh kernel, no errors | 4 |
| EDA: real exploration, target-balance check, ≥2 labelled charts | 4 |
| Correct split + leakage-free preprocessing | 4 |
| Baseline + ≥2 models actually compared | 4 |
| Honest evaluation: right metric for the problem, confusion matrix / regression metrics, CV on the best model | 2 |
| Clear write-up: problem statement + conclusion | 2 |

A project that *runs and is honest* scores well even with modest accuracy — a copied 99%-accuracy notebook that can't be explained scores zero. When in doubt, ask in the club channel **before** the deadline; asking questions is a feature, not a bug.
