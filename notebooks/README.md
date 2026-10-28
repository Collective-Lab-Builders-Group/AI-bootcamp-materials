# Notebooks

This folder contains the **Jupyter notebooks** we use during the sessions.

**Right now, there is one notebook here: [`day1_bootcamp_ml_basics.ipynb`](day1_bootcamp_ml_basics.ipynb)** — a Python crash course for machine learning. Below you'll find (1) what a Jupyter notebook *is*, (2) three ways to run this one, including **uploading it to Google Colab or Kaggle with zero installation**, and (3) an explanation of **every line in the notebook**.

---

## 1. What is a Jupyter notebook?

A **Jupyter notebook** is an interactive document that opens inside your web browser. It is made of boxes called **cells**, and each cell is one of two kinds:

- **Code cells** — these hold Python code. You click a cell, press `Shift + Enter`, and Python runs it; the result appears immediately underneath.
- **Text (markdown) cells** — these hold written explanations, headings, and lists (exactly like the cells with `##` titles in our notebook).

Everything lives in one file: your code, your notes, and even the outputs of cells you have already run — so when you reopen the notebook later, previous results are still visible. (A small background program on the computer — the **kernel** — is what actually executes the code when you run a cell.) This "explanations right next to code" setup is why notebooks are the standard tool for learning and doing data science.

How do you recognise one? By the file extension: **`.ipynb`** = "interactive Python notebook". Our file `day1_bootcamp_ml_basics.ipynb` is one — it is *not* a `.py` script you run from the command line.

## 2. Three ways to run this notebook

The notebook only needs Python with these libraries installed: `numpy`, `pandas`, `matplotlib`, `scikit-learn`. Good news — **all of them are preinstalled** on Colab, Kaggle, and in Anaconda/Miniconda environments, so in practice there's nothing extra to install.

### ✅ Way 1 — Google Colab (easiest: nothing to install)

1. Go to <https://colab.research.google.com> and sign in with any Google account.
2. In the menu: **File → Upload notebook** (or just drag `day1_bootcamp_ml_basics.ipynb` onto the page).
3. Run cells with the ▶ button or `Shift + Enter`. To run everything at once: **Runtime → Run all**.

### ✅ Way 2 — Kaggle (nothing to install, and where we'll practise anyway)

1. Sign up / log in at <https://www.kaggle.com>.
2. Go to **Code → New Notebook** (<https://www.kaggle.com/code>).
3. In the notebook editor: **File → Import Notebook** and choose `day1_bootcamp_ml_basics.ipynb`.
4. Run cells with `Shift + Enter`, or the ▶ button. (Settings on the right can unlock a free GPU when we need one later.)

### 💻 Way 3 — Run it on your own computer

Requires the **Day 1 setup** ([`Day 1/README.md`](../Day%201/README.md)) — Miniconda + the `bootcamp` environment:

1. Download this repo's files (git clone, or download the folder).
2. Open the Anaconda Prompt / terminal and run:

   ```
   conda activate bootcamp
   jupyter lab
   ```

3. Your browser opens with a file listing — navigate to `notebooks/` and click `day1_bootcamp_ml_basics.ipynb`.

> ⚠️ **One rule for any notebook: run the cells top to bottom, in order.** Code in a later cell often depends on earlier cells (e.g. the ML section uses NumPy functions defined earlier in your session). If you get a "not defined" error, run everything from the top (Colab: *Runtime → Run all*; Jupyter: *Run → Run All Cells*).

---

## 3. What the notebook teaches — every cell, line by line

The notebook is titled **"Python Crash Course for Machine Learning & Data Science"**, with the goal: *learn just enough Python to read and write basic ML code*. It moves through 6 topics: Python basics → functions → NumPy → pandas → matplotlib → your first scikit-learn model.

*Convention used below: `#` lines are **comments** — Python ignores them completely; they exist to explain code to humans.*

### The first text cell (title)

Lists the goal and the 6 numbered topics of the session. No code — pure text.

### 1. Python basics

**Cell — variables and types**

```python
age = 25            # int
height = 1.75       # float
name = 'Kelvin'     # str
is_student = True   # bool

print(type(age), type(height), type(name), type(is_student))

# f-strings
print(f'{name} is {age} years old and {height} m tall')
```

- `age = 25` — a **variable** is a named box holding a value. This one holds `25`, a whole number, whose type is **int** (integer). Similar: `height` is a **float** (decimal number), `name` is a **str** (string = text in quotes), and `is_student` is a **bool** (boolean = only ever `True` or `False`).
- `print(type(age), ...)` — `type(x)` asks Python what type a value has; `print(...)` shows results on screen. This line prints all four types at once.
- `print(f'{name} is {age} years old and {height} m tall')` — an **f-string**: put `f` before the quote and wrap variables in `{ }` to insert their values into text. It prints `Kelvin is 25 years old and 1.75 m tall`. You'll use f-strings constantly to label results.

**Cell — lists, tuples, dicts, sets**

```python
scores = [88, 92, 79, 95]               # list: ordered, mutable
point = (3, 4)                          # tuple: ordered, immutable
student = {'name': 'Ada', 'age': 25}    # dict: key -> value
unique = {1, 2, 2, 3}                   # set: unique items

scores.append(100)
print(scores[0], scores[-1], scores[1:3])   # indexing & slicing
print(student['name'])
print(unique)
```

- `scores = [...]` — a **list**: many values in square brackets, kept in order, changeable ("mutable"). Analogy: a shopping list.
- `point = (3, 4)` — a **tuple**: like a list, but **frozen** ("immutable") — you can't change it after creating it. Analogy: coordinates of a point.
- `student = {...}` — a **dictionary** ("dict"): pairs of labels → values, written `'key': value`. `student['name']` looks up what belongs to the key `'name'` → prints `Ada`. Analogy: a real dictionary maps a word → its meaning.
- `unique = {1, 2, 2, 3}` — a **set**: curly braces; it automatically **removes duplicates**, so it prints `{1, 2, 3}`. Useful for counting distinct things.
- `scores.append(100)` — `append` adds `100` to the end of the list; now `scores` has 5 items.
- `scores[0]`, `scores[-1]`, `scores[1:3]` — **indexing and slicing**: `scores[0]` = the first item, `scores[-1]` = the last (negative counts from the end), `scores[1:3]` = items at positions 1 and 2 (the end position is *excluded*). Python counts positions from **0**.
- Last two lines print one lookup in the dict and the whole set.

**Cell — control flow and looping**

```python
for s in scores:
    if s >= 90:
        print(s, '-> A')
    elif s >= 80:
        print(s, '-> B')
    else:
        print(s, '-> C')
print("\n")

# Looping with an index, and over dicts
for i, s in enumerate(scores):
    print(i, s)

print("\n")

for key, value in student.items():
    print(key, value)
```

- `for s in scores:` — a **for loop**: do the indented lines below once *for each item* in the list, with `s` temporarily holding the current item. Indentation (the spaces) is not decoration in Python — it defines what's "inside" the loop.
- `if / elif / else` — decisions: check the first condition (`s >= 90` → grade A); if false, check the second one (`elif` = else-if, grade B); `else` catches everything remaining (grade C). Comparisons are `>=`, `>`, `==`, `<=`, `<`, `!=`.
- `print("\n")` — `\n` is a newline character; this just prints blank lines to separate the three demos.
- `enumerate(scores)` — loop with the **position number included**: `for i, s in ...` gives you both the index `i` and the value `s` at the same time.
- `student.items()` — walk through a **dictionary** pair by pair: `for key, value in ...` hands you each label and its value.

### 2. Functions & comprehensions

**Cell — defining functions**

```python
def mean(values):
    # Return the average of a list of numbers
    return sum(values) / len(values)

def normalize(x, low=0, high=100):
    return (x - low) / (high - low)

print(mean(scores))
print(normalize(50))
```

- `def mean(values):` — **defines a function**: give the block a name (`mean`), an input (`values`), do work in the indented body, and send the result back with `return`. Average = sum divided by how many items (`sum()` and `len()` are built-ins — length of the list). After this cell, `mean(scores)` works anywhere in the notebook.
- `def normalize(x, low=0, high=100):` — a second function squashing a number into the 0–1 range; the formula `(x - low) / (high - low)` maps 0 → 0 and 100 → 1. `low=0, high=100` are **default arguments**: if you call `normalize(50)` the defaults are used, but you can override them: `normalize(50, low=-1, high=1)`.
- The two prints call the functions and show their results.

**Cell — comprehensions, lambda, zip**

```python
# List comprehensions: you'll see these everywhere in ML code
squares = [x**2 for x in range(10)]
evens = [x for x in range(10) if x % 2 == 0]
print(squares)
print(evens)

# lambda + zip
add = lambda a, b: a + b
for a, b in zip([1, 2, 3], [4, 5, 6]):
    print(add(a, b))
```

- `range(10)` — generates the numbers 0 through 9.
- `[x**2 for x in range(10)]` — a **list comprehension**: an entire for-loop compressed into one line. Reads as: "make a list of `x**2` (x squared) for every x in that range." This one prints `[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]`. The next line, `evens`, does the same with an `if` filter, keeping only numbers where `x % 2 == 0` (`%` is the remainder operator; remainder 0 means even) → `[0, 2, 4, 6, 8]`. Comprehensions are everywhere in real ML code because they're shorter than a loop with `append` and just as readable once you know the pattern.
- `add = lambda a, b: a + b` — a **lambda**: a function without a name, written in one line (`lambda x: x + 1` style). Handy for tiny throwaway functions.
- `zip([1,2,3], [4,5,6])` — `zip` **pairs up** two lists element by element, so the loop sees `(1,4)`, `(2,5)`, `(3,6)`; for each pair, `add(a, b)` prints the sum.

**Cell — a tiny class**

```python
# A tiny class: ML libraries are built on these (model.fit, model.predict)
class Counter:
    def __init__(self):
        self.count = 0

    def increment(self):
        self.count += 1

c = Counter()
c.increment()
c.increment()
print(c.count)
```

- `class Counter:` — a **class** is a blueprint for objects that carry both data and functions. ML code everywhere looks like this, which is why it appears: a `RandomForest` model is an object, and you call `model.fit(...)` and `model.predict(...)` on it — exactly the pattern of `fit`/`predict` style methods shown in section 6.
- `def __init__(self):` — runs automatically when an object is created (**initialises** it). `self` refers to *this specific object*, and `self.count = 0` gives it a starting value of a stored number.
- `def increment(self):` — a method (a function that belongs to the class): adds 1 to that object's own `count`.
- `c = Counter()` — create (instantiate) one counter; `c.increment()` twice bumps its count to 2; the print shows `2`.

**Cell — imports**

```python
# Imports
import math
import random
print(math.sqrt(16), random.randint(1, 10))
```

- `import math` / `import random` — loads packages from Python's standard repository. After importing, their functions are reachable through the dot: `math.sqrt(16)` computes the square root (`4.0`), and `random.randint(1, 10)` gives a random whole number between 1 and 10 (varies every run). Anything you `import` once is available for the rest of the session.

### 3. NumPy: the foundation of ML math

**Cell — arrays and vectorised math**

```python
import numpy as np

a = np.array([1, 2, 3, 4])
M = np.array([[1, 2], [3, 4], [5, 6]])

print(a.shape, M.shape)
print(a * 2)          # vectorized: no loop needed
print(a + a)
print(M.T)            # transpose
```

- `import numpy as np` — the universal convention: NumPy is always imported *as* `np`.
- `np.array(...)` — turns a Python list into a NumPy **array**, the data structure all ML math is built on (pandas and scikit-learn convert to arrays under the hood). `a` is a 1-D array (a vector); `M` is a 2-D array (a matrix: 3 rows × 2 columns).
- `a.shape` — the size of each dimension: `(4,)` for the vector, `(3, 2)` for the matrix. Data scientists glance at shapes constantly.
- `a * 2` — **vectorization**: multiply *every element at once* → `[2, 4, 6, 8]`, with no `for` loop. This is NumPy's superpower: fast and short.
- `a + a` — element-wise addition (position by position: 1+1=2, 2+2=4, …) → `[2, 4, 6, 8]`.
- `M.T` — **transpose**: flip rows into columns; shape `(3, 2)` becomes `(2, 3)`.

**Cell — useful creation functions + randomness**

```python
# Useful creation functions
print(np.zeros((2, 3)))
print(np.ones(3))
print(np.arange(0, 10, 2))
print(np.linspace(0, 1, 5))

rng = np.random.default_rng(42)
X = rng.normal(size=(5, 3))
print(X)
```

- `np.zeros((2, 3))` — a 2×3 matrix filled with zeros ( NumPy recipes always pass the shape as a tuple `(rows, columns)`); `np.ones(3)` — three ones.
- `np.arange(0, 10, 2)` — integers 0, 2, 4, 6, 8 (like `range`, start–stop–step); `np.linspace(0, 1, 5)` — **5 evenly spaced points between 0 and 1** (both ends included): 0, 0.25, 0.5, 0.75, 1.0. Use `arange` for steps, `linspace` for "N samples across an interval".
- `np.random.default_rng(42)` — creates a **random number generator**; the `42` is a **seed** that pins the "same randomness" every run — so results are reproducible (you get the same numbers today and tomorrow). Any integer works.
- `rng.normal(size=(5, 3))` — a 5×3 array of random values from a normal (bell-curve) distribution — the classic stand-in for "some data".

**Cell — aggregations, axes, indexing, masks**

```python
# Aggregations, axes, indexing, masks
print(X.mean(), X.mean(axis=0))   # overall mean, per-column mean
print(X.std(axis=0))
print(X[:, 0])                    # first column
print(X[X[:, 0] > 0])             # rows where first column > 0

# Matrix multiplication (core of neural nets)
W = rng.normal(size=(3, 2))
print((X @ W).shape)
```

- `X.mean()` — one mean over **all** numbers; `X.mean(axis=0)` — an **axis** means "collapse along this direction": axis 0 = down the rows → **one mean per column** (array of 3 means). `axis=1` would give one mean per row.
- `X.std(axis=0)` — the standard deviation (spread) of each column — you'll meet it again when we standardise data.
- `X[:, 0]` — **slicing extends to 2-D**: `[rows, columns]`. Here: *all* rows (`:` = everything), column 0 → the first column.
- `X[X[:, 0] > 0]` — a **boolean mask**: inside the brackets is a True/False condition per row; NumPy keeps only the rows that are `True`. This "filter rows by condition" trick is a daily-usage idiom.
- `W = rng.normal(size=(3, 2))` then `X @ W` — **matrix multiplication** with `@`: X is (5,3), W is (3,2), and the inner sizes match (3 = 3), so the result is (5, 2). This single operation (each output value is a sum of products — a **dot product**) is literally what the layers of a neural network compute.

### 4. Pandas: working with tabular data

**Cell — a DataFrame**

```python
import pandas as pd

df = pd.DataFrame({
    'age':    [22, 35, 58, 41, 29],
    'income': [28000, 54000, 72000, 61000, 39000],
    'city':   ['Abuja', 'Lagos', 'Lagos', 'Kano', 'Abuja'],
    'bought': [0, 1, 1, 1, 0],
})

df.head()
```

- `import pandas as pd` — the universal alias.
- `pd.DataFrame({...})` — a **DataFrame** is pandas' "spreadsheet": build one from a dictionary where each **key becomes a column name** and each **list becomes that column's values**. Here: 5 customers (rows) with 4 attributes (columns). `bought` (0/1) is a classic prediction target: *did the customer buy?*
- `df.head()` — shows the first 5 rows as a tidy table. (In a notebook, a bare `df.head()` as the last line of a cell displays automatically — no `print` needed. That's also why `df` alone would show the same thing.)

**Cell — getting to know the data**

```python
df.info()
df.describe()
```

- `df.info()` — the health check: lists every column, its **dtype** (int/float/object-where-object usually means text), and **how many values are filled** — missing data shows up here as "non-null count < row count". Use this on any new dataset, first.
- `df.describe()` — quick statistics per numeric column: count, mean, standard deviation, min, quartiles, max.

**Cell — selecting and filtering**

```python
# Selecting and filtering
print(df['age'])                      # one column (Series)
print(df[['age', 'income']])          # several columns
print(df[df['income'] > 50000])       # filter rows
print(df.loc[0, 'city'], df.iloc[0, 1])
```

- `df['age']` — one column by name → a **Series** (pandas' 1-D object). `df[['age', 'income']]` — **two brackets = a list of columns** → a small DataFrame. Rule of thumb: single brackets → Series, list inside brackets → DataFrame.
- `df[df['income'] > 50000]` — **row filtering with a boolean mask** (same idea as NumPy's): the condition produces True/False per row and only the True rows are kept.
- `df.loc[0, 'city']` — `.loc` selects **by label**: row labeled 0, column named `'city'`. `df.iloc[0, 1]` — `.iloc` selects **by integer position**: first row (row 0), second column (column 1) → the income of the first customer. Both together cover every lookup you'll ever need.

**Cell — new columns, grouping, missing values, one-hot encoding**

```python
# Creating columns, grouping, handling missing values
df['income_k'] = df['income'] / 1000
print(df.groupby('city')['income'].mean())

df.loc[2, 'age'] = np.nan             # introduce a missing value
print(df.isna().sum())
df['age'] = df['age'].fillna(df['age'].median())

# One-hot encode a categorical column
df_encoded = pd.get_dummies(df, columns=['city'])
df_encoded.head()
```

- `df['income_k'] = df['income'] / 1000` — **create a new column** by doing arithmetic on an existing one; pandas applies the operation to every row at once (vectorized, like NumPy).
- `df.groupby('city')['income'].mean()` — **groupby**: split rows into groups (one per city), then aggregate each group — here the **average income per city**. ("For each group, take the mean of this column.")
- `df.loc[2, 'age'] = np.nan` — writes `np.nan` (Not a Number = the standard placeholder for **missing data**) into one cell, purely to demonstrate missing-data handling.
- `df.isna().sum()` — counts missing values per column (`isna()` → True/False; sums ⇒ count of Trues). It should report `age` has 1 missing.
- `df['age'].fillna(df['age'].median())` — the standard first fix: **fill missing values (impute)** — here with the **median age** (median is robust to outliers), storing the result back into the column.
- `pd.get_dummies(df, columns=['city'])` — **one-hot encoding**: machine-learning models understand numbers, not words, so the text column `city` is expanded into one 0/1 column per city (`city_Abuja`, `city_Lagos`, `city_Kano`). A row "in Lagos" then shows `1` under `city_Lagos` and `0` elsewhere.

**Text cell after it** — reminds you how real data arrives later in the bootcamp: `pd.read_csv('file.csv')` loads a real file into a DataFrame exactly like the mini-table above.

### 5. Matplotlib: looking at your data

**Cell — a line plot**

```python
import matplotlib.pyplot as plt

x = np.linspace(0, 10, 100)
plt.plot(x, np.sin(x), label='sin(x)')
plt.xlabel('x'); plt.ylabel('y'); plt.legend(); plt.title('A line plot')
plt.show()
```

- `import matplotlib.pyplot as plt` — the plotting library; you always use its `pyplot` part, aliased to `plt`.
- `x = np.linspace(0, 10, 100)` — 100 x-values spread evenly from 0 to 10 (why linspace: we want a smooth line, not 10 choppy steps).
- `plt.plot(x, np.sin(x), label='sin(x)')` — one y-value for every x (`np.sin` applied to the whole array — vectorized again) connected into a curve; the `label` is what the legend shows.
- The decorator line: `plt.xlabel('x')` / `plt.ylabel('y')` — axis captions; `plt.legend()` — draws the label box; `plt.title(...)` — the chart title. (Semicolons let us put several short calls on one line.)
- `plt.show()` — renders the picture below the cell. Rule: *always label your axes* — an unlabelled chart communicates nothing.

**Cell — scatter plot of noisy data, and a histogram**

```python
rng = np.random.default_rng(0)
x = rng.uniform(0, 10, 100)
y = 3 * x + rng.normal(0, 3, 100)

plt.scatter(x, y, alpha=0.7)
plt.title('Noisy linear data')
plt.show()

plt.hist(y, bins=15)
plt.title('Histogram of y')
plt.show()
```

- New `rng` with seed `0`; `rng.uniform(0, 10, 100)` — 100 random x-values spread uniformly between 0 and 10.
- `y = 3 * x + rng.normal(0, 3, 100)` — manufactured data with a **signal plus noise**: true relationship `y = 3x` (each x is tripled — again vectorized) plus normal random noise (mean 0, spread 3). This is exactly the kind of data a linear model is going to try to *learn from*.
- `plt.scatter(x, y, alpha=0.7)` — a **scatter plot** (dot per data point — the standard first look at two variables together); `alpha=0.7` makes dots slightly transparent so overlaps stay visible.
- `plt.hist(y, bins=15)` — a **histogram**: how often values fall into each of 15 value ranges ("bins") — the standard way to see a variable's distribution. One cell can produce several charts; each block here ends with its own `plt.show()`.

### 6. Your first ML model: scikit-learn

**Text cell** — states the workflow that *every* ML project follows:

> load data → split train/test → fit model → predict → evaluate

Keep this loop in mind — the next two cells are literally this loop, numbered.

**Cell — train your first model**

```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score

# 1. Load data
X, y = load_iris(return_X_y=True)
print(X.shape, y.shape)

# 2. Split
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# 3. Fit
model = LogisticRegression(max_iter=200)
model.fit(X_train, y_train)

# 4. Predict & 5. Evaluate
preds = model.predict(X_test)
print('Accuracy:', accuracy_score(y_test, preds))
```

- The four `from ... import ...` lines — pull specific tools from specific places: a famous dataset, the splitter, a model, and a scoring helper. (Capitalised names = classes you will *instantiate*.)
- `X, y = load_iris(return_X_y=True)` — the **iris dataset**: 150 flowers, 4 measurements each (petal/sepal length & width). `X` = the measurements (the **features**, a 150×4 matrix) and `y` = the species label, 0/1/2 (the **target** vector). Convention: capital `X`, lowercase `y` — used everywhere in ML.
- `train_test_split(X, y, test_size=0.2, random_state=42)` — the crucial hygiene step: put aside **20%** of the flowers (`test_size=0.2`) as a *hidden exam set* the model never trains on — testing on data the model has seen would be like grading an exam you'd already seen the answers to. `random_state=42` makes that 80/20 division the same every run. You get back four arrays: training features/target and test features/target.
- `model = LogisticRegression(max_iter=200)` — choose a model object (here, logistic regression = classification despite the name). Similar to the `Counter` class: an object whose methods do the work.
- `model.fit(X_train, y_train)` — **training**: the model looks at the training data and adjusts itself. *This one line is "the learning".* `max_iter=200` just raises the internal iteration limit so the optimisation finishes comfortably.
- `preds = model.predict(X_test)` — **prediction**: the fitted model makes its species guess for each held-out flower.
- `accuracy_score(y_test, preds)` — **evaluation**: the fraction of test flowers where the guess was exactly right. On this dataset, accuracy typically lands in the **very high 90s — often even 100%** — because iris is an easy, classic dataset. Your first working model! 🎉

**Cell — swapping models is one line**

```python
# Swapping models is a one-line change: same fit/predict API
from sklearn.ensemble import RandomForestClassifier

rf = RandomForestClassifier(random_state=42)
rf.fit(X_train, y_train)
print('Random forest accuracy:', rf.score(X_test, y_test))
```

- `from sklearn.ensemble import RandomForestClassifier` — a different, more powerful model class. Import it, create it, and call the **exact same `.fit()` / evaluate flow** — that consistency is scikit-learn's design: once you know the loop, you can try any model by changing one line.
- `rf.score(X_test, y_test)` — scikit-learn's shortcut that combines `predict` + `accuracy_score` for classifiers.

### Text cell at the end — exercises

Four practice tasks that combine the sections; hints for each:

1. **`standardize(arr)`** — write it as a function like `mean`/`normalize` above, with a body of `return (arr - arr.mean()) / arr.std()`; NumPy vectorization does the rest.
2. Average income of buyers — a `groupby('bought')['income'].mean()` on the customer table; read the group with `bought == 1`.
3. Scatter plot where colour = bought — `plt.scatter(df['age'], df['income'], c=df['bought'], alpha=0.7)`; colour-mapping with `c=` is all it takes.
4. KNeighborsClassifier — same 5 steps as the logistic-regression cell, replacing only the model line with `from sklearn.neighbors import KNeighborsClassifier` … `model = KNeighborsClassifier()`.

## If something goes wrong

- **`ModuleNotFoundError: No module named 'xxx'`** — you're running outside Colab/Kaggle/Anaconda without that library. `pip install xxx` (or the conda equivalent), or just run the notebook in Colab/Kaggle where it's preinstalled.
- **A cell references something "not defined"** — you skipped a cell above; run all cells from the top.
- **Numbers look different from your neighbour's** — seeds are set (`random_state=42`, seed 0/42), so results *should* match; check you ran everything in order.

## Python learning resources

Since this notebook is a *Python* crash course first, here are solid places to strengthen the basics:

- 📘 **The official Python tutorial** (free, from Python's makers): <https://docs.python.org/3/tutorial/>
- 🎓 **Python for Everybody** — a famously friendly free beginner course (book + videos + exercises): <https://www.py4e.com/>
- 🔧 **Automate the Boring Stuff with Python** — free online book aimed at practical, real-world tasks: <https://automatetheboringstuff.com/>
- 🥁 **Kaggle Learn: Python** — a free 7-lesson interactive course that runs *in notebooks*, exactly like today's session: <https://www.kaggle.com/learn/python>
- 💡 **futurecoder** — learn Python by typing code in the browser, with instant feedback: <https://futurecoder.io/>
- 📝 **W3Schools Python** — quick reference with try-it-yourself examples: <https://www.w3schools.com/python/>

And the documentation for each library used in this notebook (your go-to references later):

- **Python** (language): <https://www.python.org/> · **NumPy**: <https://numpy.org/doc/stable/user/absolute_beginners.html> · **pandas**: <https://pandas.pydata.org/docs/user_guide/10min.html> · **Matplotlib**: <https://matplotlib.org/> · **scikit-learn**: <https://scikit-learn.org/stable/getting_started.html>
