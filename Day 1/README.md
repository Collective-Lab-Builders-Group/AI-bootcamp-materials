# Day 1 — Python for Machine Learning

**Self-paced, ≈3–4 hours.** By the end of today your tools will work, and you will be able to read and write basic machine-learning code.

## What you'll be able to do after today

- Run notebooks in **Google Colab / Kaggle** (nothing to install) or on your own computer
- Read and write Python: variables, lists/dicts, loops, functions
- Use **NumPy** (math on arrays), **pandas** (tables), **matplotlib** (charts) at beginner level
- Train your **first model** with scikit-learn: `load → split → fit → predict → evaluate`

## Step 1 — Set up your tools (≈45–60 min)

Follow **[`setup-and-tools.md`](setup-and-tools.md)**. Pick ONE of its two paths:

- **Path A (easiest):** run everything in the browser on Colab or Kaggle — nothing to install
- **Path B:** install Miniconda on your computer and create the `bootcamp` environment

## Step 2 — Work through the notebook (≈2 hours)

Open **[`day1_bootcamp_ml_basics.ipynb`](day1_bootcamp_ml_basics.ipynb)** (how to open it is in the setup guide) and go **top to bottom**: read each text cell, then **run each code cell yourself** — don't just read the code, re-type the examples and re-run them. Tweak things and see what breaks; that's how the learning sticks.

Stuck on any line? Every single line is explained in plain language in **[`notebook-walkthrough.md`](notebook-walkthrough.md)**.

The notebook covers, in order:

1. Python basics — variables, types, lists/tuples/dicts/sets, loops, `if/elif/else`
2. Functions & comprehensions (+ your first class — this is what `model.fit()` is!)
3. NumPy — arrays, vectorized math, the operations behind every ML library
4. pandas — tables, filtering, grouping, missing values, one-hot encoding
5. matplotlib — line plots, scatter plots, histograms
6. Your first model — the full scikit-learn loop on the iris dataset

## Step 3 — Exercises (≈45 min)

Do the **Exercises** at the bottom of the notebook. They only need things the notebook already showed you. Exercise 4 (a K-nearest-neighbours model) is a preview of Day 2.

## Done when ✅

- [ ] The notebook runs top to bottom without errors
- [ ] You can explain, in one sentence each: a *variable*, a *list*, a *dict*
- [ ] You can reproduce the ML loop from memory: `load → split → fit → predict → evaluate`
- [ ] Exercises 1 and 2 are attempted

## Next

Tomorrow — **Day 2: basic model building done properly** on messier, real-world data, plus the habits that keep your results honest (preprocessing, overfitting, the right metrics, cross-validation). See **[`../Day 2/`](../Day%202/)**.

After Day 2 you'll build your **own project** — that project is the club's assessment: [`../Projects/`](../Projects/).
