# Git and GitHub

> Used by data scientists to **track versions** of code, notebooks and experiments, and to **collaborate** on the same ML project.

| | Git | GitHub |
|---|---|---|
| **What** | A **version control system** (software) | A **website** that hosts Git repositories online |
| **Where** | Runs on your computer | Runs in the cloud (https://github.com) |
| **Works offline?** | Yes | No |
| **Used for** | Saving snapshots (commits), branching, undoing changes | Backup, sharing, teamwork, Pull Requests, portfolio |

> **Remember:** Git is the tool, GitHub is the place where you store and share Git projects.

> **Example project used in these notes:** `house-price-prediction` — an ML project with data cleaning, EDA, feature engineering, model training and evaluation. **Shehzad** and **Athar** work on it together.

## Table of Contents

- [Git and GitHub](#git-and-github)
  - [Table of Contents](#table-of-contents)
  - [Important Terms](#important-terms)
  - [Setup](#setup)
    - [Check Git Version](#check-git-version)
    - [Configure User Details](#configure-user-details)
    - [Connect to GitHub with SSH](#connect-to-github-with-ssh)
  - [Initialize Repository](#initialize-repository)
  - [Git 3-Stage Workflow](#git-3-stage-workflow)
    - [Check Status](#check-status)
    - [Add to Staging](#add-to-staging)
    - [Commit](#commit)
  - [See Changes \& History](#see-changes--history)
  - [.gitignore \& .gitkeep](#gitignore--gitkeep)
    - [.gitignore](#gitignore)
    - [.gitignore for Data Science Projects](#gitignore-for-data-science-projects)
    - [.gitkeep](#gitkeep)
  - [Remove \& Rename Files](#remove--rename-files)
  - [Unstaging \& Restore](#unstaging--restore)
  - [Undo Commits](#undo-commits)
    - [Amend the Last Commit](#amend-the-last-commit)
    - [Reset (Soft, Mixed, Hard)](#reset-soft-mixed-hard)
    - [Revert Commit](#revert-commit)
    - [Recover Lost Commits (Reflog)](#recover-lost-commits-reflog)
    - [Which Undo to Use](#which-undo-to-use)
  - [Branching](#branching)
  - [Merging Branches](#merging-branches)
    - [Fast-Forward Merge](#fast-forward-merge)
    - [Three-Way Merge](#three-way-merge)
    - [Squash Merge](#squash-merge)
    - [Octopus Merge](#octopus-merge)
  - [Merge Conflicts](#merge-conflicts)
  - [Stash](#stash)
  - [Git Rebase](#git-rebase)
  - [Cherry-Pick](#cherry-pick)
  - [Tags](#tags)
  - [Remote Repository](#remote-repository)
  - [Clone Repository](#clone-repository)
  - [Push, Pull \& Fetch](#push-pull--fetch)
    - [Daily Workflow](#daily-workflow)
  - [Remote Branches](#remote-branches)
  - [Fork \& Pull Request Workflow](#fork--pull-request-workflow)
  - [Team Workflow on a Shared Remote Branch](#team-workflow-on-a-shared-remote-branch)
    - [Author](#author)

---

## Important Terms

| Term | Meaning |
|---|---|
| **Repository (repo)** | A project folder tracked by Git (contains a hidden `.git` folder) |
| **Commit** | A saved snapshot of your files with a message |
| **Staging area** | A waiting area where you choose which changes go into the next commit |
| **Branch** | An independent line of work (e.g. `main`, `feature-engineering`) |
| **HEAD** | Pointer to the commit/branch you are currently on |
| **Merge** | Combine changes from one branch into another |
| **Remote** | A copy of the repo somewhere else, usually GitHub (`origin`) |
| **Clone** | Download a full copy of a remote repo |
| **Push / Pull** | Upload / download commits to / from the remote |
| **Fork** | Your own copy of someone else's GitHub repo |
| **Pull Request (PR)** | A request to merge your branch into another repo/branch |

---

## Setup

### Check Git Version

```bash
git --version
```

### Configure User Details

Your name and email are attached to every commit you make.

```bash
git config --global user.name "Muhammad Shehzad"
git config --global user.email "shehzad@email.com"

# Check configuration
git config --list
```

> Use the **same email** as your GitHub account so commits are linked to your profile.

### Connect to GitHub with SSH

SSH lets you push and pull without typing a password every time. Run these in **Git Bash**:

- **Inside VS Code:** open the terminal with `` Ctrl + ` ``, click the **⌄** next to **+**, choose **Git Bash**.
- **On its own:** press the Windows key, type **Git Bash**, open it.

> The default VS Code terminal on Windows is **PowerShell**. `eval` and `clip <` won't work there.

| # | Step | Command / Action |
|---|------|------------------|
| 1 | Check for existing keys | `ls ~/.ssh` |
| 2 | Generate a new key | `ssh-keygen -t ed25519 -C "your_email@example.com"` *(press Enter ×3)* |
| 3 | Start the SSH agent | `eval "$(ssh-agent -s)"` |
| 4 | Add the key to the agent | `ssh-add ~/.ssh/id_ed25519` |
| 5 | Copy the public key | `clip < ~/.ssh/id_ed25519.pub` |
| 6 | Add the key to GitHub | GitHub → **Settings** → **SSH and GPG keys** → **New SSH key** → Paste → **Add** |
| 7 | Test the connection | `ssh -T git@github.com` *(type `yes` the first time)* |
| 8 | Clone with SSH | `git clone git@github.com:USERNAME/REPO.git` |
| 9 | Switch a repo to SSH | `git remote set-url origin git@github.com:USERNAME/REPO.git` |

---

## Initialize Repository

Turn a normal folder into a Git repository:

```bash
mkdir house-price-prediction
cd house-price-prediction
git init          # creates a hidden .git folder
```

> **Warning:** Never delete the `.git` folder — it contains the entire history of your project.

---

## Git 3-Stage Workflow

```text
 Working Directory ──►  Staging Area ──►  Repository
```

| Stage | Meaning |
|---|---|
| **Working Directory** | Files you are editing right now |
| **Staging Area** | Changes selected for the next commit |
| **Repository** | Permanently saved commits |

### Check Status

```bash
git status
```

| Status | Meaning |
|---|---|
| **Untracked** | New file, Git is not tracking it yet |
| **Modified** | Tracked file changed but not staged |
| **Staged** | Ready to be committed |

### Add to Staging

```bash
git add clean_data.py                 # one file
git add clean_data.py train_model.py  # several files
git add .                             # everything in this folder (and subfolders)
git add *.py                          # all files of one type
```

### Commit

```bash
# Commit staged changes with a message
git commit -m "data cleaned"

# Stage all TRACKED modified files and commit in one step
git commit -am "Handle missing values in price column"
```

> **Note:** `-am` does not include **new (untracked)** files. Use `git add .` for those.

> **Commit message rules:** start with a verb (Add, Fix, Update, Remove), keep it short (≤ 50 characters), and describe **what** changed — e.g. `Add Random Forest baseline model`.

---

## See Changes & History

```bash
git diff                              # changes not yet staged
git diff --staged                     # changes that will go into the next commit
git log                               # full history (press q to quit)
git log --oneline                     # one line per commit
git log --oneline --all --graph       # all branches as a graph
git log --oneline -5                  # last 5 commits
git log --oneline -- train_model.py   # history of one file
git show commit_code                  # details of one commit
git blame train_model.py              # who changed each line
```

---

## .gitignore & .gitkeep

### .gitignore

A file named `.gitignore` tells Git which files and folders to **ignore** (never track).

```text
config.yaml        # one file
data/raw/          # a whole folder
*.log              # all .log files
temp*              # all files starting with temp
!important.log     # exception: DO track this file
```

```bash
git add .gitignore
git commit -m "Add .gitignore"
```

> **Important:** `.gitignore` only affects **untracked** files. If a file is already tracked, stop tracking it with `git rm --cached file_name`.

### .gitignore for Data Science Projects

```text
# Python
__pycache__/
*.pyc

# Virtual environments
venv/
.venv/
env/

# Jupyter checkpoints
.ipynb_checkpoints/

# Secrets (NEVER push these)
.env
*.key

# Large data and trained models
data/raw/
*.csv
*.zip
*.pkl
*.joblib
*.h5

# Experiment logs
mlruns/
wandb/

# Editor / OS files
.vscode/
.DS_Store
Thumbs.db
```

> **Tip:** GitHub provides ready-made templates: https://github.com/github/gitignore

### .gitkeep

Git does **not** track empty folders. Put an empty `.gitkeep` file inside to keep the folder:

```bash
mkdir models
touch models/.gitkeep
git add models/.gitkeep
```

> `.gitkeep` is not a special Git feature — it is just a common name for an empty placeholder file.

---

## Remove & Rename Files

```bash
git rm old_notebook.ipynb              # delete a file and stage the deletion
git rm --cached house_prices.csv       # stop tracking, keep the file on your computer
git mv model.py train_model.py         # rename or move a file
```

---

## Unstaging & Restore

```bash
git restore --staged train_model.py               # unstage one file (keeps your edits)
git restore --staged .                            # unstage everything
git restore train_model.py                        # discard edits, go back to last commit
git restore --source commit_code train_model.py   # restore a file from a specific commit
```

> **Warning:** `git restore file_name` permanently discards the uncommitted changes in that file.

---

## Undo Commits

### Amend the Last Commit

```bash
# Change the last commit message
git commit --amend -m "Add XGBoost model"

# Add a forgotten file to the last commit
git add requirements.txt
git commit --amend --no-edit
```

> Only amend commits that you have **not pushed** yet.

### Reset (Soft, Mixed, Hard)

`git reset` moves the branch back to an earlier commit. `HEAD~1` means "one commit before the current one".

```bash
git reset --soft HEAD~1    # undo last commit, keep changes staged
git reset HEAD~1           # undo last commit, keep changes unstaged (mixed)
git reset --hard HEAD~1    # undo last commit and DELETE the changes
git reset --soft HEAD~3    # undo the last 3 commits
```

> **Warning:** `--hard` can permanently delete work. Never reset commits that are already pushed — use `git revert` instead.

### Revert Commit

Safely undo a commit by creating a **new** commit that does the opposite (e.g. `A — B — C — C'`, where `C'` undoes `C`). History is not rewritten, so it is safe for pushed commits.

```bash
git log --oneline          # find the commit code
git revert commit_code
```

### Recover Lost Commits (Reflog)

Git remembers everywhere `HEAD` has been, even after a hard reset.

```bash
git reflog                 # history of HEAD movements
git reset --hard HEAD@{2}  # go back to a lost commit
```

### Which Undo to Use

| Situation | Command |
|---|---|
| Unstage a file | `git restore --staged file` |
| Discard edits in a file | `git restore file` |
| Fix the last commit message | `git commit --amend -m "..."` |
| Undo last commit (not pushed), keep work | `git reset --soft HEAD~1` |
| Undo a commit that is already pushed | `git revert commit_code` |
| Throw away all local changes | `git reset --hard` |
| Recover after a mistake | `git reflog` |

---

## Branching

A branch lets you try an idea (new feature, new model) without affecting `main`.

```text
main:                  A --- B --- C
                                    \
feature-engineering:                 D --- E
```

```bash
git branch                           # list branches (* = current)
git branch feature-engineering       # create a branch
git switch feature-engineering       # switch to it
git switch -c train-random-forest    # create + switch in one step
git switch main                      # back to main
git branch -m tune-hyperparameters   # rename the current branch
git branch -d feature-engineering    # delete a merged branch
git branch -D train-random-forest    # force delete an unmerged branch
```

> **Note:** `git checkout branch_name` and `git checkout -b branch_name` are older commands that do the same as `git switch` / `git switch -c`.

> **Good branch names for ML projects:** `data-cleaning`, `eda-notebook`, `feature-engineering`, `train-xgboost`, `tune-hyperparameters`, `fix-data-leakage`.

---

## Merging Branches

```bash
git switch main                    # 1. go to the branch that RECEIVES the changes
git merge feature-engineering      # 2. merge the other branch into it
```

| Type | When it happens | Merge commit? |
|---|---|---|
| **Fast-forward** | `main` has no new commits since the branch was created | No |
| **Three-way** | Both branches have new commits | Yes |
| **Squash** | You want all branch commits as **one** commit | No (one normal commit) |
| **Octopus** | Merging 3+ branches at once | Yes (with many parents) |

### Fast-Forward Merge

`main` has no new commits, so Git just moves `main` forward to the branch's last commit.

```bash
git switch -c data-cleaning
echo "df = df.dropna()" > clean_data.py
git add .
git commit -m "Add data cleaning script"

git switch main
git merge data-cleaning            # fast-forward, no merge commit
```

### Three-Way Merge

Both branches have new commits, so Git creates a **merge commit** `M` that joins them.

```text
main:             A --- B --- E --- M
                         \         /
eda-notebook:             C --- D
```

```bash
# Shehzad works on EDA in a branch
git switch -c eda-notebook
echo "df.describe()" > eda.py
git add .
git commit -m "Add EDA summary statistics"

# Meanwhile main gets a different commit
git switch main
echo "pandas" > requirements.txt
git add .
git commit -m "Add requirements.txt"

# Merge (-m gives the merge commit a message, so no editor opens)
git merge eda-notebook -m "Merge eda-notebook into main"
```

### Squash Merge

Combines all commits of a branch into **one** new commit on `main`. Keeps `main` history clean — useful when a branch has many small "try this" commits.

```bash
git switch -c train-model

echo "split data" > split_data.py
git add . && git commit -m "Add train/test split"

echo "fit model" > train_model.py
git add . && git commit -m "Add model training"

echo "rmse, r2" > evaluate.py
git add . && git commit -m "Add evaluation metrics"

git switch main
git merge --squash train-model     # stages all changes, does NOT commit yet
git commit -m "Add model training pipeline (split, train, evaluate)"

git branch -D train-model          # -D because Git does not see it as merged
```

### Octopus Merge

Merges **several** branches at once into one merge commit (e.g. three independent experiments).

```bash
git switch -c model-linear
echo "LinearRegression" > linear.py
git add . && git commit -m "Add linear regression model"

git switch main
git switch -c model-random-forest
echo "RandomForestRegressor" > random_forest.py
git add . && git commit -m "Add random forest model"

git switch main
git switch -c model-xgboost
echo "XGBRegressor" > xgboost_model.py
git add . && git commit -m "Add XGBoost model"

git switch main
git merge model-linear model-random-forest model-xgboost -m "Merge all model experiments"
```

> **Note:** An octopus merge stops if there is any conflict. Then merge the branches one by one.

---

## Merge Conflicts

A **conflict** happens when two branches change the **same lines** of the same file. Git cannot decide which version to keep, so you choose.

```bash
git status       # shows which files have conflicts
```

Git marks the conflict inside the file like this:

```text
<<<<<<< HEAD
model = LinearRegression()
=======
model = RandomForestRegressor()
>>>>>>> try-random-forest
```

**Resolve it:**
1. Keep the line you want (one side, the other, or a mix).
2. Delete the markers `<<<<<<<`, `=======`, `>>>>>>>`.
3. Save the file, then:

```bash
git add .
git commit -m "Resolve model conflict"

# Or cancel the merge completely
git merge --abort
```

> **Tip:** VS Code shows buttons above each conflict: **Accept Current**, **Accept Incoming**, **Accept Both**, **Compare**.

> Practice (create a conflict on purpose)

```bash
echo "model = LinearRegression()" > train_model.py
git add . && git commit -m "Add linear model"

git switch -c try-random-forest
echo "model = RandomForestRegressor()" > train_model.py
git commit -am "Try random forest"

git switch main
echo "model = Ridge()" > train_model.py
git commit -am "Try ridge regression"

git merge try-random-forest   # CONFLICT in train_model.py
```

---

## Stash

**Stash** temporarily saves uncommitted changes so you can switch branches with a clean working directory.

```bash
git stash                                          # save uncommitted changes
git stash push -u -m "half-done feature scaling"   # with a message, include untracked files
git stash list                                     # see all stashes
git stash pop                                      # restore latest and remove it from the list
git stash apply                                    # restore latest, keep it in the list
git stash apply stash@{1}                          # restore a specific stash
git stash drop                                     # delete the latest stash
git stash clear                                    # delete all stashes
```

> Workflow

```bash
# Athar is half-way through feature engineering — not ready to commit
git stash

# Urgent: the training script crashes on main
git switch main
git add train_model.py
git commit -m "Fix crash on missing target column"
git push

# Back to the feature work
git switch feature-engineering
git stash pop
```

---

## Git Rebase

**Rebase** moves your branch's commits so they start from the **latest** commit of another branch. The result is a straight history with no merge commit.

```text
Before:   main: A --- B --- C          feature: (from B) D --- E
Merge:    feature: ... D --- E --- M   (extra merge commit)
Rebase:   feature: A --- B --- C --- D' --- E'   (straight line)
```

```bash
# Athar's feature-engineering branch is behind main
git switch feature-engineering
git rebase main

# If there is a conflict: fix the file, then
git add .
git rebase --continue

# Or cancel
git rebase --abort
```

| Merge | Rebase |
|---|---|
| Keeps the full true history | Creates a clean straight-line history |
| Adds a merge commit | No merge commit |
| Safe for shared branches | **Only for local / unshared commits** |

> **Golden rule:** Never rebase commits that have been pushed and shared with others.

---

## Cherry-Pick

Copy **one specific commit** from another branch onto the current branch:

```bash
git log --oneline feature-engineering   # find the commit code
git switch main
git cherry-pick commit_code
```

> Useful when you need just one fix (e.g. a data leakage fix) from a branch, without merging the whole branch.

---

## Tags

Tags mark important commits, usually **releases** or **model versions** (`v1.0`, `model-v2`).

```bash
git tag v1.0                                   # lightweight tag
git tag -a v1.0 -m "Baseline model, R2 = 0.82"  # annotated tag (recommended)
git tag v0.9 commit_code                       # tag an older commit
git tag                                        # list tags
git show v1.0                                  # tag details
git push origin v1.0                           # push one tag
git push origin --tags                         # push all tags
git tag -d v1.0                                # delete local tag
git push origin --delete v1.0                  # delete remote tag
```

> **Note:** `git push` does **not** push tags automatically.

---

## Remote Repository

A **remote** is a link to a repository on GitHub. The default name is `origin`.

```bash
git remote add origin https://github.com/shehzad/house-price-prediction.git
git remote -v                                                            # check remotes
git remote set-url origin git@github.com:shehzad/house-price-prediction.git  # switch to SSH
git remote rename origin upstream
git remote remove origin
```

**Push an existing local project to a new GitHub repo:**
1. On GitHub: **New repository** → name it → **do not** add a README → **Create repository**.
2. In your project folder:

```bash
git remote add origin https://github.com/shehzad/house-price-prediction.git
git branch -M main
git push -u origin main
```

---

## Clone Repository

Download a full copy of an existing GitHub repository (all files + history):

```bash
git clone https://github.com/shehzad/house-price-prediction.git
git clone https://github.com/shehzad/house-price-prediction.git my-folder   # different folder name
cd house-price-prediction
```

> Cloning automatically sets up the `origin` remote.

---

## Push, Pull & Fetch

```text
             git push  ────────►
 Local Repo                         GitHub (origin)
             ◄────────  git pull / git fetch
```

| Command | What it does |
|---|---|
| `git push -u origin main` | First push: upload and link local `main` to `origin/main` |
| `git push` | Upload commits (after `-u` is set) |
| `git pull` | Download **and merge** latest changes |
| `git fetch origin` | Download **without** merging, so you can look first |

```bash
# Fetch, check, then merge
git fetch origin
git log --oneline main..origin/main   # what's new on GitHub
git merge origin/main
```

> **pull** = fetch + merge

> **Error "rejected – fetch first":** someone pushed before you. Run `git pull`, fix any conflicts, then `git push` again.

### Daily Workflow

```bash
git pull                                       # 1. get the latest code
# 2. edit notebooks / scripts ...
git status                                     # 3. check what changed
git add .                                      # 4. stage
git commit -m "Add cross-validation to training"  # 5. commit
git push                                       # 6. upload
```

---

## Remote Branches

```bash
# Shehzad pushes his branch to GitHub
git switch -c train-xgboost
git add xgboost_model.py
git commit -m "Add XGBoost model"
git push -u origin train-xgboost

# View branches
git branch        # local
git branch -r     # remote
git branch -a     # all

# Athar checks out Shehzad's branch
git fetch origin
git switch train-xgboost      # creates a local branch tracking origin/train-xgboost

# Delete branches
git push origin --delete train-xgboost   # on GitHub
git branch -d train-xgboost              # locally
git fetch --prune                        # clean up refs to branches deleted on GitHub
```

---

## Fork & Pull Request Workflow

Use this when you want to contribute to a repository you **do not own** (open source, a classmate's project).

| Remote | Points to | Meaning |
|---|---|---|
| `origin` | **Your fork** | You can push here |
| `upstream` | **Original repository** | You only pull from here |

```text
athar/house-price-prediction     (Athar's original repo)   ← upstream
              │ Fork
              ▼
shehzad/house-price-prediction   (Shehzad's copy on GitHub) ← origin
```

**1. Fork** — on GitHub, open the original repository → click **Fork** (top-right).

**2. Clone your fork** (not the original):

```bash
git clone git@github.com:shehzad/house-price-prediction.git
cd house-price-prediction
```

**3. Add the original repo as upstream:**

```bash
git remote add upstream git@github.com:athar/house-price-prediction.git
git remote -v
# origin    → your fork
# upstream  → original repository
```

**4. Create a branch and make changes** — never work directly on `main`:

```bash
git switch -c fix-data-leakage
git add preprocess.py
git commit -m "Fit scaler on train set only"
```

**5. Push to your fork:**

```bash
git push -u origin fix-data-leakage
```

**6. Create a Pull Request** — on your fork click **Compare & pull request**, then check the direction:

| | Repository | Branch |
|---|---|---|
| **base** (receives changes) | `athar/house-price-prediction` | `main` |
| **compare** (your changes) | `shehzad/house-price-prediction` | `fix-data-leakage` |

**7. Review & merge** — Athar reviews, comments or approves, then merges. If changes are requested, just commit and push again to the **same branch**; the PR updates automatically.

**8. Sync your fork with upstream** when the original gets new commits:

```bash
git switch main
git pull upstream main
git push origin main
```

> **Tip:** You can also click **Sync fork** on your fork's GitHub page.

> **Full flow:** Fork → Clone → Add upstream → Branch → Commit → Push to origin → Pull Request → Review → Merge → Sync

---

## Team Workflow on a Shared Remote Branch

When teammates have **write access** to the same repository, they share branches directly (no fork needed). Suppose Athar pushed `origin/feature-engineering`:

```bash
# Shehzad: get the branch
git fetch origin
git branch -r                     # origin/main, origin/feature-engineering, ...
git switch -c feature-engineering origin/feature-engineering

# Shehzad: edit and push back to the same branch
git add features.py
git commit -m "Add log transform for skewed features"
git push origin feature-engineering

# Athar: update his local copy
git switch feature-engineering
git pull origin feature-engineering
```

---
[**Next Lesson `MiniConda`**](<4 minicoda.md>)

### Author
- **[MUHAMMAD SHEHZAD](https://github.com/dbdmlabs)**
