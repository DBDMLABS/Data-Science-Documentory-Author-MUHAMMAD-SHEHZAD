# Setting Up Environment for Data Science

> A step-by-step guide to set up a complete Data Science workspace on a new computer.

## Table of Content
- [Setting Up Environment for Data Science](#setting-up-environment-for-data-science)
  - [Table of Content](#table-of-content)
  - [Required Software](#required-software)
  - [Install VS Code Extensions](#install-vs-code-extensions)
    - [Install All Extensions with One Command](#install-all-extensions-with-one-command)
  - [Create Your First Data Science Environment](#create-your-first-data-science-environment)
  - [Connect the Environment to VS Code](#connect-the-environment-to-vs-code)
  - [Verify Everything Works](#verify-everything-works)
  - [Setup Checklist](#setup-checklist)
    - [Author](#author)

---

## Required Software

| Software | Purpose | 
|---|---|
| **VS Code** | IDE (Integrated Development Environment) to write code, notebooks and notes https://code.visualstudio.com |
| **Git** | Version Control System to track changes in your files  https://git-scm.com |
| **GitHub account** | Online storage for your Git projects (and sign-in for VS Code)  https://github.com |
| **Miniconda** | Creates separate environments with different Python versions and packages  https://www.anaconda.com/docs/getting-started/miniconda/install |

---


> **Students:** Apply for the **GitHub Student Developer Pack** (https://education.github.com/pack) to get **GitHub Copilot Pro free**.


## Install VS Code Extensions

Open the Extensions panel with `Ctrl + Shift + X`, search for the name, and click **Install**.

| Extension | Purpose |
|---|---|
| **Python** | Python development support (run, select interpreter, environments) |
| **Pylance** | Fast IntelliSense: auto-complete, type hints, error checking |
| **Python Debugger** | Debug Python programs with breakpoints |
| **Jupyter** | Create and run Jupyter notebooks (`.ipynb`) in VS Code |
| **Jupyter Notebook Renderers** | Display rich outputs (plots, images, LaTeX, HTML) |
| **Jupyter Cell Tags** | Add tags to notebook cells |
| **Jupyter Keymap** | Jupyter-style keyboard shortcuts (`A`, `B`, `DD`, `M`, `Y`) |
| **Markdown All in One** | Shortcuts, auto table of contents, live preview |
| **Markdown PDF** | Convert Markdown files to PDF |
| **vscode-pdf** | View PDF files inside VS Code |
| **HTML Preview** | Preview HTML files inside VS Code |
| **Rainbow CSV** | Colors each CSV column so data is easy to read |
| **Edit CSV** | View and edit CSV files like a spreadsheet |
| **Black Formatter** | Formats Python code automatically to the PEP 8 style |
| **Prettier - Code Formatter** | Formats JSON, HTML, CSS, JavaScript and Markdown |
| **GitHub Copilot** | AI code suggestions as you type |
| **GitHub Copilot Chat** | Ask questions and get code explanations in a chat panel |
| **BLACKBOX AI** | Free alternative AI coding assistant |
| **GitHub Theme** | GitHub-style light and dark color themes |
| **Material Icon Theme** | Clear icons for files and folders |
| **vscode-icons** | Alternative file and folder icon set |
| **DotENV** | Syntax highlighting for `.env` files (environment variables, API keys) |

### Install All Extensions with One Command

Instead of searching one by one, paste these commands into a terminal:

```bash
code --install-extension ms-python.python
code --install-extension ms-python.vscode-pylance
code --install-extension ms-python.debugpy
code --install-extension ms-toolsai.jupyter
code --install-extension ms-toolsai.jupyter-renderers
code --install-extension ms-toolsai.vscode-jupyter-cell-tags
code --install-extension ms-toolsai.jupyter-keymap
code --install-extension yzhang.markdown-all-in-one
code --install-extension yzane.markdown-pdf
code --install-extension tomoki1207.pdf
code --install-extension mechatroner.rainbow-csv
code --install-extension janisdd.vscode-edit-csv
code --install-extension ms-python.black-formatter
code --install-extension esbenp.prettier-vscode
code --install-extension GitHub.copilot
code --install-extension GitHub.copilot-chat
code --install-extension GitHub.github-vscode-theme
code --install-extension PKief.material-icon-theme
code --install-extension mikestead.dotenv
```

---

## Create Your First Data Science Environment

Create a separate environment for data science work, so that its packages never conflict with other projects:

```bash
# Create an environment named "ds" with Python 3.12
conda create -n ds python=3.12 -y

# Activate it
conda activate ds

# Install the main data science libraries
pip install numpy pandas matplotlib seaborn scipy sympy scikit-learn jupyter ipykernel
```

Check that the libraries are installed:

```bash
python -c "import numpy, pandas, matplotlib, seaborn, scipy, sympy, sklearn; print('All libraries installed!')"
```

> **Important Point:** Always **activate** the environment (`conda activate ds`) before installing packages, otherwise they go into the wrong environment.

---

## Connect the Environment to VS Code

**For Python files (`.py`):**
1. Press `Ctrl + Shift + P` → type **Python: Select Interpreter**.
2. Choose the one that shows **`ds`** (for example `Python 3.12 ('ds')`).

**For notebooks (`.ipynb`):**
1. Open or create a notebook.
2. Click **Select Kernel** (top-right) → **Python Environments** → choose **`ds`**.

> **Tip:** The selected interpreter is shown in the bottom-right status bar. If `ds` does not appear in the list, restart VS Code.

---

## Verify Everything Works

1. Create a new file `test.ipynb` in VS Code.
2. Select the `ds` kernel.
3. Run this cell:

```python
import sys
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# Which Python is running? (path should contain "ds")
print(sys.executable)

# Library versions
print("NumPy:", np.__version__)
print("Pandas:", pd.__version__)

# Quick plot
x = np.linspace(0, 10, 100)
plt.plot(x, np.sin(x))
plt.title("Setup works!")
plt.show()
```

If you see the versions and a sine wave plot, your setup is complete.

---

## Setup Checklist

- [ ] VS Code installed and opens correctly
- [ ] Git installed (`git --version`) and configured with name and email
- [ ] GitHub account created and signed in to VS Code
- [ ] Miniconda installed (`conda --version`)
- [ ] VS Code extensions installed
- [ ] `ds` environment created with the data science libraries
- [ ] `ds` selected as the interpreter / notebook kernel
- [ ] Test notebook runs and shows a plot

---
[**Next Lesson `Markdown Language`**](<2 Markdown_Language.md>)

### Author
- **[MUHAMMAD SHEHZAD](https://github.com/dbdmlabs)**
