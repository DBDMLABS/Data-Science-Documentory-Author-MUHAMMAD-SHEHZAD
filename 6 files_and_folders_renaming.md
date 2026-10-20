# Professional File and Folder Naming

> Simple rules for naming files and folders so your Data Science projects stay clean, readable and easy to share.

## Table of Content
- [Professional File and Folder Naming](#professional-file-and-folder-naming)
  - [Table of Content](#table-of-content)
  - [Why Naming Matters](#why-naming-matters)
  - [Rule 1 — Use Lowercase Letters and Underscores](#rule-1--use-lowercase-letters-and-underscores)
  - [Rule 2 — Be Descriptive and Specific](#rule-2--be-descriptive-and-specific)
  - [Rule 3 — Use Folders to Group Related Files](#rule-3--use-folders-to-group-related-files)
  - [Rule 4 — Follow a Consistent Naming Convention](#rule-4--follow-a-consistent-naming-convention)
  - [Rule 5 — Add Versions or Dates When Needed](#rule-5--add-versions-or-dates-when-needed)
  - [Rule 6 — Avoid Python Keywords and Built-in Names](#rule-6--avoid-python-keywords-and-built-in-names)
  - [Rule 7 — Keep Names Short but Clear](#rule-7--keep-names-short-but-clear)
  - [Rule 8 — Do Not Start Python File Names with Numbers](#rule-8--do-not-start-python-file-names-with-numbers)
  - [Rule 9 — Use Plural Names for Folders](#rule-9--use-plural-names-for-folders)
  - [Rule 10 — Add a README File](#rule-10--add-a-readme-file)
  - [Example Project Structure](#example-project-structure)
  - [Quick Reference](#quick-reference)
    - [Author](#author)

---

## Why Naming Matters

Good names make it easy to:
- Find a file quickly without opening it
- Understand a project you (or someone else) wrote months ago
- Import Python files as modules without errors
- Avoid problems in the terminal, Git and on different operating systems

---

## Rule 1 — Use Lowercase Letters and Underscores

Use lowercase letters for both files and folders, and separate words with underscores (`_`) or hyphens (`-`). **Avoid spaces.**

| ❌ Bad | ✅ Good |
|---|---|
| `Data Preprocessing.py` | `data_preprocessing.py` |
| `My Notebook.ipynb` | `my_notebook.ipynb` |
| `Raw Data/` | `raw_data/` |

> **Important Point:** Do not use special characters such as `@ # $ % & ( ) !` or spaces. Use only letters, numbers, underscores and hyphens.

> **Note:** For Python files, prefer underscores. A file named `data-cleaning.py` cannot be imported with `import data-cleaning`, but `data_cleaning.py` can be imported with `import data_cleaning`.

> **Why avoid spaces?** In the terminal you must wrap such names in quotes (`cd "My Folder"`), and some tools break on them.

---

## Rule 2 — Be Descriptive and Specific

A name should tell you what the file contains or does.

| ❌ Vague | ✅ Descriptive |
|---|---|
| `script.py` | `linear_regression.py` |
| `data.csv` | `sales_2024.csv` |
| `test.ipynb` | `eda_customer_churn.ipynb` |

---

## Rule 3 — Use Folders to Group Related Files

Group files into folders by their purpose or by their stage in the Data Science pipeline:

| Folder | What goes inside |
|---|---|
| `data/` | Datasets (often split into `raw/` and `processed/`) |
| `notebooks/` | Jupyter notebooks for exploration and analysis |
| `scripts/` or `src/` | Reusable Python code |
| `models/` | Saved trained models |
| `reports/` | Figures, charts and final reports |

---

## Rule 4 — Follow a Consistent Naming Convention

Consistency is key. Pick one style and use it across the whole project.

For example, if you start with the `verb_noun` style:

```text
clean_data.py
train_model.py
evaluate_model.py
plot_results.py
```

Do not mix styles like `cleanData.py`, `Train-Model.py` and `evaluate_model.py` in the same project.

| Style | Example | Common use |
|---|---|---|
| `snake_case` | `clean_data.py` | Python files, folders (recommended) |
| `kebab-case` | `project-report.md` | Web files, documents |
| `camelCase` | `cleanData` | Variables in JavaScript (avoid for file names) |

---

## Rule 5 — Add Versions or Dates When Needed

When you keep several versions of a model or dataset, add a version number or a date:

```text
model_v1.pkl
model_v2.pkl
data_cleaning_v1.py
sales_2024-01-15.csv
```

> **Tip:** Write dates as `YYYY-MM-DD` (for example `2024-01-15`). Files then sort in the correct order automatically.

> **Note:** For code, prefer **Git** over `_v1`, `_v2` copies. Git keeps the full history for you. See [Git and GitHub notes](<3 git_and_github.md>).

---

## Rule 6 — Avoid Python Keywords and Built-in Names

Do not name a file after a Python keyword, a built-in function or a popular library. This can **shadow** (hide) the real module and cause confusing errors.

| ❌ Avoid | Why |
|---|---|
| `list.py`, `dict.py`, `input.py`, `print.py` | Same as built-in names |
| `class.py`, `import.py` | Python keywords |
| `pandas.py`, `numpy.py`, `random.py`, `math.py` | Hide the real library when you `import` it |

Example of the problem:

```python
# If your folder contains a file named "pandas.py":
import pandas as pd   # imports YOUR file, not the real pandas library
pd.read_csv("data.csv")
# AttributeError: module 'pandas' has no attribute 'read_csv'
```

---

## Rule 7 — Keep Names Short but Clear

Keep file and folder names short but descriptive, to avoid very long paths. Use common abbreviations when they are clear.

| ❌ Too long | ✅ Short and clear |
|---|---|
| `train_random_forest_classification_model.py` | `train_rf_model.py` |
| `exploratory_data_analysis_of_customer_data.ipynb` | `eda_customers.ipynb` |

---

## Rule 8 — Do Not Start Python File Names with Numbers

A Python file that starts with a number **cannot be imported** as a module:

```python
import 123_data   # SyntaxError: invalid decimal literal
```

| ❌ Bad | ✅ Good |
|---|---|
| `123_data.py` | `data_123.py` |
| `1_cleaning.py` | `step1_cleaning.py` |

> **Note:** Numbering notes and notebooks (for example `01_intro.ipynb`, `02_eda.ipynb`) is fine and helps keep them in order, because they are not imported. Use leading zeros (`01`, `02` … `10`) so they sort correctly.

---

## Rule 9 — Use Plural Names for Folders

Folders that hold many files of one kind should have plural names:

```text
scripts/
datasets/
notebooks/
models/
```

---

## Rule 10 — Add a README File

Add a `README.md` file to the project (and to important folders) to explain:
- What the project or folder contains
- How the files are organized
- How to run the code (setup, required packages)

> More details on writing README files: [Markdown notes](<2 Markdown_Language.md>)

---

## Example Project Structure

```text
customer_churn/
├── README.md
├── requirements.txt
├── data/
│   ├── raw/
│   │   └── customers_2024-01-15.csv
│   └── processed/
│       └── customers_clean.csv
├── notebooks/
│   ├── 01_eda.ipynb
│   └── 02_feature_engineering.ipynb
├── src/
│   ├── clean_data.py
│   ├── train_model.py
│   └── evaluate_model.py
├── models/
│   ├── churn_model_v1.pkl
│   └── churn_model_v2.pkl
└── reports/
    └── figures/
        └── churn_by_age.png
```

---

## Quick Reference

- [ ] Lowercase letters with underscores, no spaces
- [ ] No special characters
- [ ] Names describe the content
- [ ] Related files grouped in folders
- [ ] One naming style across the project
- [ ] Versions or `YYYY-MM-DD` dates where needed
- [ ] No Python keywords, built-ins or library names
- [ ] Short but clear names
- [ ] Python files do not start with a number
- [ ] Plural folder names
- [ ] A `README.md` explains the project

---

### Author
- Author: __MUHAMMAD SHEHZAD__
- GitHub: https://github.com/dbdmlabs
