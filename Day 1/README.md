# Day 1 — The Tools We Use, Explained for Beginners

Welcome aboard! 👋 The bootcamp uses several tools. This page explains **what each one is, why we use it, and where to get it**, in plain language. Read this page once from top to bottom, then follow **one of the two setup paths at the bottom** — after that, you are ready for the session.

## 1. Python

Python is the programming language we will use for everything in this bootcamp — machine learning, data analysis, and visualisation. It was chosen because it is free, its code reads almost like plain English (making it the easiest major language to learn), and nearly every machine-learning tool in the world is built for it. We use **Python 3** (any version from 3.9 upwards is fine). **Important:** you usually don't install Python by itself — the tools in the next section install Python *for you* along with everything else.

## 2. Anaconda vs. Miniconda — and why we prefer them for package management

A **package** is a ready-made collection of code that someone else wrote and published, which you can download instead of writing it yourself — e.g. NumPy for maths on big arrays, pandas for tables, scikit-learn for machine learning. **Package management** is the art of installing, updating, and organising such packages **without breaking your computer or mixing up incompatible versions**. Doing that by hand is painful; that is where **Anaconda** and **Miniconda** come in. Both are official installers that give you two things at once: the **Python language itself**, and **conda**, a package manager built specifically for data science. The difference is only how much they pre-install:

- **Anaconda** (full distribution) = Python + conda + a graphical app called Anaconda Navigator + **hundreds of data-science packages preinstalled**. Convenient, but heavy (~10 GB of disk space).
- **Miniconda** = the minimal version: **just Python + conda** and almost nothing else (~900 MB). You install the extra packages you need yourself, one command at a time.

**Why do we prefer conda over installing plain Python and using `pip` (Python's basic installer)?** Four practical reasons: (1) conda downloads **pre-built** packages — no compilers or cryptic installation errors; (2) it automatically works out **which versions of which packages fit together**, avoiding so-called *dependency hell*; (3) it can install **non-Python dependencies** (the low-level C/Fortran libraries that NumPy and friends rely on) — something `pip` struggles with; (4) it creates **isolated environments** (see Section 4), so different projects' packages never clash with each other. **What we recommend you install: [Miniconda](https://www.anaconda.com/download)** — small, fast, and exactly what data scientists use. Choose the full Anaconda installer only if you want everything preinstalled and don't mind the size. *(Note: Anaconda's default package repository is free for individuals and education; the details are linked in the Resources section.)*

## 3. Mamba / libmamba — for intermediate & advanced users

Behind the scenes, conda uses a **"solver"** — an engine that, when you ask for a package, works out all the compatible versions of that package *and everything it depends on*. The classic conda solver is reliable but can be **very slow** on large installs, sometimes minutes of staring at "solving environment…". **Mamba** is a drop-in rewrite of conda in a faster language: you type the same commands (just `mamba` instead of `conda`) and it uses the same packages, only **dramatically faster and with clearer error messages**. **libmamba** is the same fast engine plugged directly *into* conda as its solver. For intermediate/advanced users who install packages often, this is simply less waiting. In the terminal:

```
# Option A — install the faster conda replacement itself:
conda install -n base -c conda-forge mamba
# then, from now on, use `mamba` like you used `conda`:
mamba install numpy pandas matplotlib scikit-learn

# Option B — keep using `conda` but switch its engine to libmamba:
conda update -n base conda
conda config --set solver libmamba
```

**If you're a complete beginner: skip this for now.** Recent conda versions already use libmamba as their default solver, so a fresh install is already fast — revisit this section once installing packages is second nature.

## 4. Environments: Jupyter Notebooks

An **environment** in conda is a sealed-off copy of Python with its own packages — like a separate toolbox per project, so updating one project never breaks another. For the bootcamp, the environment is just where our Python and libraries live; you create it once with a single command (shown in the quick-start paths below) and switch into it with `conda activate bootcamp`. Inside that environment we do our work in **Jupyter Notebooks** — and this is the tool you will touch every single day. A notebook is a document that opens **in your browser**, made of small boxes called **cells**; each cell holds either runnable **code** or formatted **text**. You run a code cell, and its output (a number, a table, a chart) appears **immediately underneath it**. This is ideal for learning and for data science: instead of writing a whole program, you experiment step by step and *see* each result. A small helper program called the **kernel** (just Python running in the background) is what actually executes your code. Notebook files end in **`.ipynb`** — for example, our Day 1 file `notebooks/day1_bootcamp_ml_basics.ipynb`. **Requirement to know:** Jupyter runs a tiny "server" on your computer — that sounds scary, but installing and launching it is a single command (`jupyter lab`), covered below.

## 5. Google Colab and Kaggle — for those who don't want to install anything on their computer

If you don't want to install Jupyter's server (or any of the tools above) on your own machine — maybe your laptop is old, low on space, or you simply prefer zero setup — use **Google Colab**, <https://colab.research.google.com>, or **Kaggle**, <https://kaggle.com>. Both provide notebooks that run **entirely in your web browser**: Google or a Kaggle account runs the notebook server *for* you in their cloud, so there is genuinely nothing to install, nothing to download, and all popular libraries (NumPy, pandas, matplotlib, scikit-learn) are **already preinstalled**. Both are free, and both even lend you a free **GPU** (a fast processor for AI) when you need one. Your notebook files and their outputs live in the cloud instead of on your laptop, which also means you can continue a session from any computer. **How to use them with our material:** simply upload our `.ipynb` notebook into either site and run it — exact click-by-click steps are in [`notebooks/README.md`](../notebooks/README.md). Pick **one** of Colab or Kaggle; they work the same way for our purposes.

## 6. Kaggle — the website we will use throughout the bootcamp

**Kaggle** (<https://www.kaggle.com>) is the world's biggest community website for data science and machine learning, and it's free. It has four things we'll actually use: **(1) Datasets** — thousands of free, ready-to-use data files we will download for exercises; **(2) Notebooks** — the in-browser notebook environment from Section 5, usable with zero installation; **(3) Competitions** — real prediction challenges (from beginner to research level) where you train a model and see how it ranks, a great way to practise; and **(4) Kaggle Learn** — a set of short, free, hands-on courses (Python, pandas, machine learning) that pair perfectly with this bootcamp. **Action for you: create your free Kaggle account today** at <https://www.kaggle.com> — we'll use the site from today onward.

## Quick start — choose ONE path

**Path A — No installation (easiest, works on any laptop):**
1. Have a Google or Kaggle account (5 minutes: <https://www.kaggle.com> or any Google account).
2. Open Colab: <https://colab.research.google.com> — or Kaggle: <https://www.kaggle.com/code>.
3. Upload this file: `notebooks/day1_bootcamp_ml_basics.ipynb` → follow the steps in [`notebooks/README.md`](../notebooks/README.md).
4. Done — you're ready for the session.

**Path B — Full local install (recommended if you want to work offline):**
1. Download and install **Miniconda**: <https://www.anaconda.com/download>
2. Open the **Anaconda Prompt** (Windows) or a terminal (Mac/Linux), then run — this creates the bootcamp environment with all the libraries already in it:

   ```
   conda create -n bootcamp python=3.11 numpy pandas matplotlib scikit-learn jupyterlab
   conda activate bootcamp
   jupyter lab
   ```

3. Your browser opens with a file listing — navigate to the notebook file and start.
4. (Optional, once you're comfortable: see Section 3 for mamba.)

Happy learning! 🚀

## Resources

### Python
- Where Python itself lives: <https://www.python.org/>
- The official Python tutorial (free): <https://docs.python.org/3/tutorial/>
- Beginner-friendly Python drills: <https://www.w3schools.com/python/>
- **Python for Everybody** — a classic free beginner course <https://www.py4e.com/>
- Interactive Python course (browser): <https://futurecoder.io/>

### Anaconda / Miniconda / conda (package management)
- Download page for **both** Miniconda and Anaconda: <https://www.anaconda.com/download>
- Anaconda vs. Miniconda — the official explanation of the difference: <https://anaconda.com/docs/getting-started/concepts/anaconda-or-miniconda>
- Getting started with conda (official): <https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html>
- Managing environments (official how-to): <https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html>
- Official conda cheat sheet (one page, commands): <https://docs.conda.io/projects/conda/en/latest/user-guide/cheatsheet.html>

### Mamba / libmamba
- Mamba documentation (what it is, how it fits with conda): <https://mamba.readthedocs.io/en/latest/>
- Installing mamba step by step: <https://mamba.readthedocs.io/en/latest/installation/mamba-installation.html>
- Mamba on GitHub (source, releases, issues): <https://github.com/mamba-org/mamba>

### Jupyter Notebooks
- Jupyter's home page (what it is, downloads): <https://jupyter.org/>
- Install instructions (official): <https://jupyter.org/install>
- Try Jupyter **in the browser** without installing anything: <https://jupyter.org/try-jupyter>
- Official Jupyter documentation: <https://docs.jupyter.org/en/latest/>

### Google Colab
- Colab itself (sign in with a Google account): <https://colab.research.google.com/>
- Official Colab "Welcome" notebook — a guided tour of what Colab can do: <https://colab.research.google.com/notebooks/intro.ipynb>

### Kaggle
- Kaggle's home page (register free): <https://www.kaggle.com/>
- Kaggle Learn — free short courses (Python, pandas, ML): <https://www.kaggle.com/learn>
- Kaggle datasets (free data for practice): <https://www.kaggle.com/datasets>
- How Kaggle notebooks work (official docs): <https://www.kaggle.com/docs/notebooks>
