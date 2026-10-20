# Miniconda

> What Miniconda and Conda are, why we need separate environments, and the main Conda commands for Data Science work.

## Table of Content
- [Miniconda](#miniconda)
  - [Table of Content](#table-of-content)
  - [What Is Miniconda?](#what-is-miniconda)
    - [Remember](#remember)
    - [Anaconda vs Miniconda](#anaconda-vs-miniconda)
  - [Why Do We Use Conda?](#why-do-we-use-conda)
  - [Example of Python Version Conflict](#example-of-python-version-conflict)
  - [Example of Package Version Conflict](#example-of-package-version-conflict)
  - [Solution — Virtual Environments](#solution--virtual-environments)
    - [Result](#result)
  - [Easy Formula](#easy-formula)
  - [Miniconda with Different Types of Projects](#miniconda-with-different-types-of-projects)
  - [What Is a Conda Environment?](#what-is-a-conda-environment)
  - [Basic Conda Commands](#basic-conda-commands)
    - [Quick Reference](#quick-reference)
    - [Check Conda Installation](#check-conda-installation)
    - [Create a New Environment](#create-a-new-environment)
      - [Explanation](#explanation)
    - [Activate an Environment](#activate-an-environment)
    - [Deactivate an Environment](#deactivate-an-environment)
    - [List All Environments](#list-all-environments)
    - [Install Packages](#install-packages)
    - [Remove a Package](#remove-a-package)
    - [List Installed Packages](#list-installed-packages)
    - [Update Conda](#update-conda)
    - [Install Jupyter](#install-jupyter)
    - [Remove an Environment](#remove-an-environment)
    - [Save and Share an Environment](#save-and-share-an-environment)
  - [conda install vs pip install](#conda-install-vs-pip-install)
  - [Complete Data Science Environment](#complete-data-science-environment)
  - [Final Concept](#final-concept)
    - [Author](#author)

---

## What Is Miniconda?

**Miniconda** is a small (lightweight) installer that gives you **Conda**, **Python**, and a few essential packages, and nothing else.

It is used to:

- Create virtual (isolated) environments
- Manage different Python versions on the same computer
- Install and manage packages
- Keep each project's dependencies separate
- Manage Data Science, Machine Learning (ML), Deep Learning (DL) and AI environments

> Installation steps: [Setting Up Environment notes](<1 setting_up_env.md>)

### Remember

> **Important Point:** Miniconda ≠ Virtual Environment
> - **Miniconda** is the installer that provides **Conda**.
> - **Conda** is the tool that creates and manages **environments** and **packages**.
> - An **environment** is the isolated workspace that Conda creates.

### Anaconda vs Miniconda

| | Anaconda | Miniconda |
|---|---|---|
| **Size** | Large (several GB) | Small (a few hundred MB) |
| **Packages included** | Hundreds of packages pre-installed | Only Conda, Python and essentials |
| **Graphical app** | Includes Anaconda Navigator | Command line only |
| **Best for** | Users who want everything ready at once | Users who want to install only what they need |

> **Tip:** Miniconda is usually the better choice: it is faster to install and you keep each environment clean.

---

## Why Do We Use Conda?

Suppose we are working on 3 projects on the same PC:

```text
My PC
│
├── Project_A/
│   └── code.py
│
├── Project_B/
│   └── code.py
│
└── Project_C/
    └── code.py
```

Without separate environments, all projects share the same Python and the same packages:

```text
                    ONE PYTHON
                        │
                        ↓
              ONE PACKAGE ENVIRONMENT
                        │
             ┌──────────┼──────────┐
             ↓          ↓          ↓
         Project A  Project B  Project C
```

> This can create **dependency conflicts**: one project needs something that breaks another project.

---

## Example of Python Version Conflict

| Project | Required Python version |
|---|---|
| Project A | Python 3.12 |
| Project B | Python 3.11 |
| Project C | Python 3.10 |

> If all projects use the same environment, you can have only **one** Python version active, so managing different Python requirements becomes difficult.

---

## Example of Package Version Conflict

| Project | Required pandas version |
|---|---|
| Project A | pandas 1.x |
| Project B | pandas 2.x |

> If both projects use the same environment, upgrading pandas for Project B can break Project A (and downgrading it for Project A can break Project B).

---

## Solution — Virtual Environments

We create a **separate environment for each project**. Each environment has its own Python and its own packages.

```text
My PC
│
├── Project_A/  ──uses──►  Environment_A  (Python 3.12 + pandas 1.x)
│   └── code.py
│
├── Project_B/  ──uses──►  Environment_B  (Python 3.11 + pandas 2.x)
│   └── code.py
│
└── Project_C/  ──uses──►  Environment_C  (Python 3.10 + its packages)
    └── code.py
```

> **Note:** By default, Conda does **not** store environments inside your project folders. It keeps them all in one place, for example `C:\Users\<you>\miniconda3\envs\` on Windows or `~/miniconda3/envs/` on macOS/Linux. Your project only needs to know **which environment to use**.

If you really want an environment inside the project folder, use `--prefix` (or `-p`) instead of `-n`:

```bash
conda create --prefix ./env python=3.12
conda activate ./env
```

### Result

Logically, each project now has its own Python and packages:

```text
My PC
│
├── Project_A/
│   ├── code.py
│   └── Environment_A/
│       └── Its own Python + Packages
│
├── Project_B/
│   ├── code.py
│   └── Environment_B/
│       └── Its own Python + Packages
│
└── Project_C/
    ├── code.py
    └── Environment_C/
        └── Its own Python + Packages
```

> These environments are **isolated** from each other, even though all projects are on the same computer. Changing one environment never affects the others.

---

## Easy Formula

| Term | Meaning |
|---|---|
| **Folder** | Your project files (code, data, notes) |
| **Virtual Environment** | Python + Packages (an isolated workspace) |
| **Conda** | Environment Manager + Package Manager |
| **Miniconda** | Lightweight installer (distribution) of Conda |

---

## Miniconda with Different Types of Projects

```text
                         MINICONDA
                             │
              ┌──────────────┼──────────────┐
              ↓              ↓              ↓
        Environment 1   Environment 2   Environment 3
        Data Science    Deep Learning   AI Agent
              │              │              │
              ↓              ↓              ↓
           pandas         PyTorch        LangChain
           numpy          Transformers   OpenAI
           scikit-learn   CUDA tools     FastAPI
```

Each environment can have its own:
- Python version
- Packages
- Package versions
- Dependencies
- Project configuration

---

## What Is a Conda Environment?

A **Conda environment** is an isolated workspace where we can install a particular Python version and packages **without affecting other environments**.

Example:

```text
Data Science Environment
│
├── Python 3.12
├── NumPy
├── Pandas
├── Matplotlib
└── Scikit-learn


Deep Learning Environment
│
├── Python 3.11
├── PyTorch
├── Transformers
└── CUDA-related packages


AI Agent Environment
│
├── Python
├── LangChain
├── OpenAI
└── FastAPI
```

> **Note:** Every Miniconda installation also has a default environment called **`base`**. Keep `base` clean and create a new environment for your projects.

---

## Basic Conda Commands

> **Tip:** On Windows, run these commands in **Anaconda Prompt**, or in the VS Code terminal / PowerShell after running `conda init` once.

### Quick Reference

| Command | Purpose |
|---|---|
| `conda --version` | Check that Conda is installed |
| `conda create -n name python=3.12` | Create a new environment |
| `conda activate name` | Activate (enter) an environment |
| `conda deactivate` | Deactivate (leave) the current environment |
| `conda env list` | List all environments |
| `conda install package` | Install a package in the active environment |
| `conda remove package` | Remove a package from the active environment |
| `conda list` | List packages in the active environment |
| `conda update conda` | Update Conda itself |
| `conda env remove -n name` | Delete an environment |
| `conda env export > environment.yml` | Save an environment to a file |
| `conda env create -f environment.yml` | Create an environment from a file |

### Check Conda Installation

```bash
conda --version
```

Example output:

```text
conda 24.9.2
```

> If you see `'conda' is not recognized...`, Miniconda is not installed correctly, or you are not using Anaconda Prompt / a terminal where `conda init` was run.

### Create a New Environment

```bash
conda create -n datascience python=3.12
```

#### Explanation

| Part | Meaning |
|---|---|
| `conda create` | Create a new environment |
| `-n` | Short for `--name`: give the environment a name |
| `datascience` | The environment name (you can choose any name) |
| `python=3.12` | The Python version to install in it |

> **Tip:** Add `-y` at the end (`conda create -n datascience python=3.12 -y`) to answer "yes" automatically to the confirmation question.

You can also install packages while creating the environment:

```bash
conda create -n datascience python=3.12 pandas numpy
```

### Activate an Environment

```bash
conda activate datascience
```

After activation, Python commands and package installations work **inside** the `datascience` environment. The terminal prompt shows the active environment name:

```text
(base) C:\Users\you>        ← before
(datascience) C:\Users\you> ← after
```

### Deactivate an Environment

```bash
conda deactivate
```

> This leaves the currently active environment and returns you to the previous one (usually `base`).

### List All Environments

```bash
conda env list
```

Example output:

```text
# conda environments:
#
base                     C:\Users\you\miniconda3
datascience           *  C:\Users\you\miniconda3\envs\datascience
deeplearning             C:\Users\you\miniconda3\envs\deeplearning
aiagent                  C:\Users\you\miniconda3\envs\aiagent
```

> The `*` shows the currently active environment. `conda info --envs` gives the same result.

### Install Packages

```bash
conda install pandas numpy matplotlib
```

> Packages are installed into the **currently active** environment.

Install a specific version with `=`:

```bash
conda install pandas=2.2
```

Install from the community channel **conda-forge** (it has more packages and newer versions):

```bash
conda install -c conda-forge seaborn
```

> **Important Point:** Always **activate** the right environment before installing, otherwise the packages go into the wrong environment (often `base`).

### Remove a Package

```bash
conda remove pandas
```

> This removes pandas from the current environment.

### List Installed Packages

```bash
conda list
```

> Shows every package (and its version) in the active environment. To check one package: `conda list pandas`.

### Update Conda

```bash
conda update conda
```

> Run this from the `base` environment. To update a package in your environment, use `conda update package_name` (for example `conda update pandas`).

### Install Jupyter

```bash
conda install jupyter
```

> Install Jupyter inside each environment where you want to use notebooks. For VS Code notebooks, the `ipykernel` package is enough: `conda install ipykernel`.

### Remove an Environment

```bash
conda deactivate
conda env remove -n datascience
```

> You cannot delete the environment you are currently inside, so deactivate it first.

### Save and Share an Environment

Save the environment (Python version + all packages) to a file:

```bash
conda env export > environment.yml
```

Recreate the same environment on another computer:

```bash
conda env create -f environment.yml
```

> **Tip:** Add `environment.yml` to your GitHub repository so anyone can recreate your exact setup. More details: [Git and GitHub notes](<3 git_and_github.md>)

---

## conda install vs pip install

Inside a Conda environment you can use both `conda install` and `pip install`.

| | `conda install` | `pip install` |
|---|---|---|
| **Source** | Anaconda / conda-forge channels | PyPI (Python Package Index) |
| **Packages** | Python and non-Python packages (e.g. CUDA libraries) | Python packages only |
| **Number of packages** | Fewer | Almost every Python package |
| **Dependency check** | Checks the whole environment | Checks only the package being installed |

> **Tip:** Activate the environment first, then try `conda install`. If the package is not available on Conda, use `pip install`. Avoid mixing both for the same package.

```bash
conda activate datascience
pip install langchain
```

---

## Complete Data Science Environment

```bash
# Step 1 — Create environment
conda create -n datascience python=3.12 -y

# Step 2 — Activate environment
conda activate datascience

# Step 3 — Install Data Science packages
conda install pandas numpy matplotlib scikit-learn

# Step 4 — Install Jupyter
conda install jupyter

# Step 5 — Start Jupyter Notebook
jupyter notebook
```

Check that everything works inside a notebook cell:

```python
import sys
import pandas as pd
import sklearn

print(sys.executable)        # path should contain "datascience"
print("Pandas:", pd.__version__)
print("Scikit-learn:", sklearn.__version__)
```

> **Note:** `jupyter notebook` opens Jupyter in your web browser. Press `Ctrl + C` in the terminal to stop it. In VS Code you can skip Step 5 and just select the `datascience` kernel in a `.ipynb` file.

---

## Final Concept

> Miniconda gives us **Conda**, which helps us create and manage isolated environments, so different projects can use different Python versions and packages without interfering with each other.

**Typical workflow:** `conda create` → `conda activate` → `conda install` → work on your project → `conda deactivate`.

---

### Author
- Author: __MUHAMMAD SHEHZAD__
- GitHub: https://github.com/dbdmlabs
