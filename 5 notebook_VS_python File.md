# Python File vs Jupyter Notebook (.py vs .ipynb)

> A beginner-friendly comparison of `.py` files and `.ipynb` notebooks: what each one is, where each one wins, and how to use both together.

## Table of Content
- [Python File vs Jupyter Notebook (.py vs .ipynb)](#python-file-vs-jupyter-notebook-py-vs-ipynb)
  - [Table of Content](#table-of-content)
  - [Comparison](#comparison)
    - [Basics](#basics)
    - [Writing and Documentation](#writing-and-documentation)
    - [Code Quality and Engineering](#code-quality-and-engineering)
    - [Teamwork and Sharing](#teamwork-and-sharing)
    - [Research vs Production](#research-vs-production)
    - [Score Summary](#score-summary)
  - [How to Run Each File](#how-to-run-each-file)
  - [Converting Between Formats](#converting-between-formats)
  - [Common Notebook Problem — Out-of-Order Execution](#common-notebook-problem--out-of-order-execution)
  - [Notebooks and Git](#notebooks-and-git)
  - [When to Use Which](#when-to-use-which)
  - [Recommended Workflow — Use Both](#recommended-workflow--use-both)
    - [Author](#author)


## Comparison

The 33 points below compare both formats. **Winner** shows which format is usually the better choice for that point.

### Basics

| Comparison Point | `.py` — Python File | `.ipynb` — Jupyter Notebook | Winner / Best Choice |
|---|---|---|---|
| **Nature** | Plain-text Python source code | Interactive notebook containing code, Markdown, outputs and metadata | Depends |
| **Format** | `.py` plain-text file | `.ipynb` JSON-based file | `.py` (simpler) |
| **Primary Use** | Software development, automation, APIs and production systems | Data analysis, research, experimentation and visualization | Depends |
| **Execution** | Runs sequentially from start to finish | Runs cell by cell, in any order you choose | `.ipynb` (for experimentation) |
| **Execution Environment** | Terminal, IDE, server, cloud, container, scheduler | Jupyter, JupyterLab, Colab, VS Code and similar environments | Depends |
| **Learning Curve** | Slightly harder for beginners (no instant feedback) | Easier for interactive learning (see results immediately) | `.ipynb` |

### Writing and Documentation

| Comparison Point | `.py` — Python File | `.ipynb` — Jupyter Notebook | Winner / Best Choice |
|---|---|---|---|
| **Output Display** | Usually the console or external files | Output appears directly below each cell | `.ipynb` |
| **Markdown Support** | No native Markdown cells (only comments) | Native Markdown cells | `.ipynb` |
| **Documentation** | Comments and docstrings | Markdown + code + results + explanations in one place | `.ipynb` |
| **Media Embedding** | Limited (plots open in a separate window or are saved to files) | Images, charts, HTML and other rich outputs are embedded in the file | `.ipynb` |

### Code Quality and Engineering

| Comparison Point | `.py` — Python File | `.ipynb` — Jupyter Notebook | Winner / Best Choice |
|---|---|---|---|
| **IDE Support** | Excellent | Very good in modern IDEs | `.py` |
| **Code Editor Experience** | Excellent (refactoring, linting, formatting) | Good, but notebook-oriented | `.py` |
| **Code Organization** | Excellent (functions, classes, modules, folders) | Can become messy as notebooks grow | `.py` |
| **Modularity** | Excellent | Possible but less natural | `.py` |
| **Reusability** | Excellent | Moderate unless the code is moved into modules | `.py` |
| **Import Options** | Can import any library **and** can be imported by other files (`import my_module`) | Can import any library, but a notebook **cannot be imported** directly by other code (needs `%run` or extra tools) | `.py` |
| **Package Development** | Excellent (the standard format for Python packages) | Not recommended as the primary format | `.py` |
| **Testing** | Excellent (`pytest`, `unittest`) | Possible but less convenient | `.py` |
| **Debugging** | Excellent IDE/debugger support (breakpoints, step-through) | Good interactive debugging (inspect variables between cells) | `.py` |
| **Maintainability** | Excellent | Moderate for large notebooks | `.py` |
| **Long-Term Maintenance** | Excellent | Moderate | `.py` |

### Teamwork and Sharing

| Comparison Point | `.py` — Python File | `.ipynb` — Jupyter Notebook | Winner / Best Choice |
|---|---|---|---|
| **Version Control** | Excellent Git compatibility (clean line-by-line diffs) | Harder, because of JSON structure, saved outputs and metadata | `.py` |
| **Collaboration** | Excellent for software teams | Good for analysis and research teams | `.py` |
| **Sharing** | Excellent for sharing source code | Excellent for sharing a complete analysis with its results | `.ipynb` |
| **Code Review** | Easy with Git diffs | Harder because of notebook metadata and outputs | `.py` |

### Research vs Production

| Comparison Point | `.py` — Python File | `.ipynb` — Jupyter Notebook | Winner / Best Choice |
|---|---|---|---|
| **Interactive Research** | Moderate | Excellent | `.ipynb` |
| **Experiment Tracking** | Usually needs additional tools (e.g. MLflow) | Convenient for quick manual experiments | `.ipynb` |
| **Research Publication** | Good | Excellent for showing methodology + results together | `.ipynb` |
| **Reproducibility** | Generally strong (always runs top to bottom) | Can suffer from out-of-order execution | `.py` |
| **Performance** | Excellent for automated, scheduled and long-running workloads | Good for interactive workloads | `.py` |
| **File Size** | Usually small | Can become large because of saved outputs and images | `.py` |
| **Enterprise Applications** | Excellent | Usually supplementary | `.py` |
| **Overall Professional Engineering** | **Excellent** | **Good as a complementary tool** | `.py` |

> **Note:** Python code runs at the **same speed** in both formats, because both use the same Python interpreter. The `.py` advantage in **Performance** comes from being easy to automate, schedule and run on servers without a notebook interface.

### Score Summary

| Winner | Points |
|---|---|
| `.py` | 20 |
| `.ipynb` | 10 |
| Depends | 3 |
| **Total** | **33** |

> **Important Point:** `.py` wins most **engineering** points, while `.ipynb` wins most **exploration and presentation** points. Neither is "better" for everything — choose based on the task.

---

## How to Run Each File

**Run a `.py` file** (activate your environment first):

```bash
conda activate ds
python analysis.py
```

In VS Code you can also click the **Run** (play) button in the top-right corner of the editor.

**Run a `.ipynb` notebook:**

```bash
# Classic Jupyter Notebook in the browser
jupyter notebook

# Modern JupyterLab interface in the browser
jupyter lab
```

In VS Code, open the `.ipynb` file, select the kernel, and use these shortcuts:

| Shortcut | Action |
|---|---|
| `Shift + Enter` | Run the current cell and move to the next one |
| `Ctrl + Enter` | Run the current cell and stay on it |
| `A` / `B` | Insert a new cell above / below (in command mode) |
| `M` / `Y` | Change cell to Markdown / Code |
| `DD` | Delete the current cell |

> **Tip:** Press `Esc` to enter **command mode** before using the single-letter shortcuts.

---

## Converting Between Formats

| Task | Command / Method |
|---|---|
| Notebook → Python script | `jupyter nbconvert --to script notebook.ipynb` |
| Notebook → HTML (for sharing) | `jupyter nbconvert --to html notebook.ipynb` |
| Notebook → PDF | `jupyter nbconvert --to pdf notebook.ipynb` (needs LaTeX installed) |
| Notebook → Python in VS Code | Open the notebook → `...` menu → **Export** → **Python Script** |
| Python script ↔ notebook (keep both in sync) | `pip install jupytext`, then `jupytext --to notebook script.py` or `jupytext --to py notebook.ipynb` |

**Notebook-style cells inside a `.py` file:** VS Code treats `# %%` as a cell marker. You get notebook-like "Run Cell" buttons while keeping a clean `.py` file:

```python
# %%
import pandas as pd
df = pd.DataFrame({"marks": [78, 92, 85]})

# %% [markdown]
# ## Average marks

# %%
df["marks"].mean()
```

> **Tip:** This `# %%` style gives you the best of both worlds — interactive running **and** Git-friendly plain text.

---

## Common Notebook Problem — Out-of-Order Execution

In a notebook you can run cells in any order. This is useful, but it can create results that **nobody else can reproduce**.

```python
# Cell 1
x = 10

# Cell 2
y = x * 2
print(y)

# Cell 3  (you later edit Cell 1 to x = 5 and run only Cell 1 and Cell 3)
print(x, y)   # prints 5 20  -> y is now out of date!
```

The notebook still "remembers" old variables in memory, so the saved outputs may not match the code.

> **Important Point:** Before sharing or committing a notebook, use **Restart Kernel and Run All Cells**. If it runs from top to bottom without errors, it is reproducible.

---

## Notebooks and Git

Notebooks save outputs and metadata, which makes Git diffs noisy. These habits help:

| Habit / Tool | What it does |
|---|---|
| **Clear All Outputs** before committing | Keeps the file small and the diff clean |
| `nbstripout` | Automatically removes outputs when you commit (`pip install nbstripout`, then `nbstripout --install`) |
| `nbdime` | Shows readable, cell-by-cell diffs of notebooks (`pip install nbdime`, then `nbdiff a.ipynb b.ipynb`) |
| `jupytext` | Keeps a paired `.py` copy that is easy to review |

> More details: [Git and GitHub notes](<3 git_and_github.md>)

---

## When to Use Which

| Task | Best Choice |
|---|---|
| Learning Python and data science step by step | `.ipynb` |
| Exploring a new dataset (EDA) | `.ipynb` |
| Making charts and explaining results | `.ipynb` |
| Teaching, tutorials and study notes | `.ipynb` |
| Trying different machine learning models quickly | `.ipynb` |
| Writing reusable functions and classes | `.py` |
| Automation scripts and scheduled jobs | `.py` |
| Web apps, APIs and production systems | `.py` |
| Building a Python package or library | `.py` |
| Code that needs tests and code review | `.py` |

---

## Recommended Workflow — Use Both

Most professional data scientists use **both** formats together:

1. **Explore** the data and try ideas in a notebook (`.ipynb`).
2. **Move** the code that works into functions inside a `.py` file (for example `utils.py`).
3. **Import** those functions back into the notebook, so the notebook stays short and clean.
4. **Automate** the final pipeline with `.py` scripts.

```python
# In the notebook: reload utils.py automatically every time you edit it
%load_ext autoreload
%autoreload 2

from utils import clean_data, train_model

df = clean_data("data.csv")
model = train_model(df)
```

> **Tip:** A common project layout is a `notebooks/` folder for exploration and a `src/` folder for reusable `.py` code.

---
[**Next Lesson `Files and Folders Renaming`**](<6 files_and_folders_renaming.md>)

### Author
- **[MUHAMMAD SHEHZAD](https://github.com/dbdmlabs)**
