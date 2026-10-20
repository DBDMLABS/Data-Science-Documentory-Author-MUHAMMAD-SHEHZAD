# Git and GitHub

> Used by developers to **track versions** of their files and **collaborate** on the same project.

| | Git | GitHub |
|---|---|---|
| **What** | A **version control system** (software) | A **website** that hosts Git repositories online |
| **Where** | Runs on your computer | Runs in the cloud (https://github.com) |
| **Works offline?** | Yes | No |
| **Used for** | Saving snapshots (commits) of your project, branching, undoing changes | Backup, sharing, teamwork, Pull Requests, portfolio |

> **Remember:** Git is the tool, GitHub is the place where you store and share Git projects.

## Table of Contents

- [Git and GitHub](#git-and-github)
  - [Table of Contents](#table-of-contents)
  - [Important Terms](#important-terms)
  - [Setup](#setup)
    - [Check Git Version](#check-git-version)
    - [Configure User Details](#configure-user-details)
    - [Connect to GitHub with SSH (Recommended)](#connect-to-github-with-ssh-recommended)
  - [Initialize Repository](#initialize-repository)
  - [Git 3-Stage Workflow](#git-3-stage-workflow)
    - [Check Status](#check-status)
    - [Add to Staging](#add-to-staging)
    - [Commit](#commit)
    - [Writing Good Commit Messages](#writing-good-commit-messages)
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
    - [Which Undo Should I Use?](#which-undo-should-i-use)
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
    - [Push](#push)
    - [Pull](#pull)
    - [Fetch](#fetch)
    - [Daily Workflow](#daily-workflow)
  - [Remote Branches](#remote-branches)
  - [Fork \& Pull Request Workflow](#fork--pull-request-workflow)
    - [Step 1 — Fork the Repository](#step-1--fork-the-repository)
    - [Step 2 — Clone Your Fork](#step-2--clone-your-fork)
    - [Step 3 — Add the Original Repo as Upstream](#step-3--add-the-original-repo-as-upstream)
    - [Step 4 — Create a Branch and Make Changes](#step-4--create-a-branch-and-make-changes)
    - [Step 5 — Push to Your Fork](#step-5--push-to-your-fork)
    - [Step 6 — Create a Pull Request](#step-6--create-a-pull-request)
    - [Step 7 — Review \& Merge](#step-7--review--merge)
    - [Step 8 — Sync Your Fork with Upstream](#step-8--sync-your-fork-with-upstream)
    - [Complete Fork Workflow](#complete-fork-workflow)
  - [Team Workflow on a Shared Remote Branch](#team-workflow-on-a-shared-remote-branch)
  - [Basic GitHub Workflow](#basic-github-workflow)
    - [Author](#author)

---

## Important Terms

| Term | Meaning |
|---|---|
| **Repository (repo)** | A project folder tracked by Git (contains a hidden `.git` folder) |
| **Commit** | A saved snapshot of your files with a message |
| **Staging area** | A waiting area where you choose which changes go into the next commit |
| **Branch** | An independent line of work (e.g. `main`, `feature-login`) |
| **HEAD** | Pointer to the commit/branch you are currently on |
| **Merge** | Combine changes from one branch into another |
| **Remote** | A copy of the repo on another place, usually GitHub (`origin`) |
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
git config --global user.name "User Name"
git config --global user.email "user@email.com"
```

> Use the **same email** as your GitHub account so commits are linked to your profile.

Recommended extra settings:

```bash
# Name the first branch "main" in every new repository
git config --global init.defaultBranch main

# Use VS Code as the editor for commit messages
git config --global core.editor "code --wait"
```

Check configuration:

```bash
git config --list
git config user.name
```

### Connect to GitHub with SSH (Recommended)

SSH lets you push and pull without typing a password every time.

```bash
# 1. Create a key (press Enter to accept the defaults)
ssh-keygen -t ed25519 -C "user@email.com"

# 2. Show the public key and copy it
cat ~/.ssh/id_ed25519.pub
```

3. On GitHub: **Settings → SSH and GPG keys → New SSH key** → paste → **Add SSH key**.
4. Test the connection:

```bash
ssh -T git@github.com
# Hi username! You've successfully authenticated...
```

> **HTTPS vs SSH URLs:**\
> HTTPS → `https://github.com/username/repository.git`\
> SSH → `git@github.com:username/repository.git`

---

## Initialize Repository

Turn a normal folder into a Git repository:

```bash
# Create folder
mkdir dbdm-project

# Enter folder
cd dbdm-project

# Initialize Git (creates a hidden .git folder)
git init
```

> **Warning:** Never delete the `.git` folder — it contains the entire history of your project.

---

## Git 3-Stage Workflow

```text
 Working Directory  ──git add──►  Staging Area  ──git commit──►  Repository
 (edit files)                     (choose changes)                (saved history)
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
# Specific file
git add file_name.txt

# Multiple files
git add file1.txt file2.txt

# All files in the current folder (and subfolders)
git add .

# All files of one type
git add *.py
```

### Commit

```bash
# Commit staged changes with a message
git commit -m "Your message"

# Stage all TRACKED modified files and commit in one step
git commit -am "Your message"
```

> **Note:** `-am` does not include **new (untracked)** files. Use `git add .` for those.

### Writing Good Commit Messages

| Bad | Good |
|---|---|
| `update` | `Add data cleaning step for missing ages` |
| `fixed stuff` | `Fix wrong column name in sales plot` |
| `asdf` | `Remove unused imports from model.py` |

> **Rules:** Start with a verb (Add, Fix, Update, Remove), keep it short (≤ 50 characters), and describe **what** changed.

---

## See Changes & History

```bash
# Changes not yet staged
git diff

# Changes that are staged (will go into the next commit)
git diff --staged

# Commit history (press q to quit)
git log

# Compact history: one line per commit
git log --oneline

# All branches as a graph
git log --oneline --all --graph

# Last 5 commits
git log --oneline -5

# History of one file
git log --oneline -- file_name.txt

# Show details of one commit
git show commit_code

# Who changed each line of a file
git blame file_name.txt
```

---

## .gitignore & .gitkeep

### .gitignore

A file named `.gitignore` tells Git which files and folders to **ignore** (never track).

```text
file_name.txt      # one file
folder/            # a whole folder
*.log              # all .log files
temp*              # all files starting with temp
!important.log     # exception: DO track this file
```

```bash
git add .gitignore
git commit -m "Add .gitignore"
```

> **Important Point:** `.gitignore` only affects **untracked** files. If a file is already tracked, stop tracking it with:
> ```bash
> git rm --cached file_name.txt
> ```

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

# Large data and models
data/raw/
*.csv
*.zip
*.pkl
*.joblib

# Editor / OS files
.vscode/
.DS_Store
Thumbs.db
```

> **Tip:** GitHub provides ready-made templates: https://github.com/github/gitignore

### .gitkeep

Git does **not** track empty folders. Put an empty `.gitkeep` file inside to keep the folder:

```bash
mkdir uploads
touch uploads/.gitkeep
git add uploads/.gitkeep
```

> `.gitkeep` is not a special Git feature — it is just a common name for an empty placeholder file.

---

## Remove & Rename Files

```bash
# Delete a file and stage the deletion
git rm file_name.txt

# Stop tracking a file but keep it on your computer
git rm --cached file_name.txt

# Rename or move a file
git mv old_name.txt new_name.txt
```

---

## Unstaging & Restore

```bash
# Remove a specific file from staging (keeps your edits)
git restore --staged file_name.txt

# Remove all files from staging
git restore --staged .

# Discard changes in a file and restore the last committed version
git restore file_name.txt

# Restore a file from a specific commit
git restore --source commit_code file_name.txt
```

> **Warning:** `git restore file_name.txt` permanently discards the uncommitted changes in that file.

---

## Undo Commits

### Amend the Last Commit

Fix the last commit message, or add a forgotten file to it:

```bash
# Change the last commit message
git commit --amend -m "Correct message"

# Add a forgotten file to the last commit
git add forgotten_file.txt
git commit --amend --no-edit
```

> Only amend commits that you have **not pushed** yet.

### Reset (Soft, Mixed, Hard)

`git reset` moves the branch back to an earlier commit. `HEAD~1` means "one commit before the current one".

| Command | Commit undone? | Changes kept? | Where are the changes? |
|---|---|---|---|
| `git reset --soft HEAD~1` | Yes | Yes | **Staged** |
| `git reset HEAD~1` (mixed, default) | Yes | Yes | **Unstaged** (in working directory) |
| `git reset --hard HEAD~1` | Yes | **No** | **Deleted** |

```bash
# Soft: undo last commit, keep changes staged
git reset --soft HEAD~1

# Mixed: undo last commit, keep changes unstaged
git reset HEAD~1

# Hard: undo last commit and DELETE the changes
git reset --hard HEAD~1

# Undo the last 3 commits
git reset --soft HEAD~3
```

> **Warning:** `--hard` can permanently delete work. Never reset commits that are already pushed and shared — use `git revert` instead.

### Revert Commit

Safely undo a specific commit by creating a **new** commit that does the opposite. History is not rewritten, so it is safe for pushed commits.

```bash
# Find the commit code
git log --oneline

# Revert it
git revert commit_code
```

```text
Before:  A --- B --- C          (C has a bug)
After:   A --- B --- C --- C'   (C' undoes C)
```

### Recover Lost Commits (Reflog)

Git remembers everywhere `HEAD` has been, even after a hard reset.

```bash
# See the history of HEAD movements
git reflog

# Go back to a lost commit
git reset --hard HEAD@{2}
```

### Which Undo Should I Use?

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

A branch lets you work on a feature without affecting `main`.

```text
main:     A --- B --- C
                       \
feature:                D --- E
```

```bash
# List branches (* = current branch)
git branch

# Create a branch
git branch branch_name

# Switch to a branch
git switch branch_name

# Create + switch in one step
git switch -c branch_name

# Switch back to main
git switch main

# Rename the current branch
git branch -m new_name

# Delete a merged branch
git branch -d branch_name

# Force delete an unmerged branch
git branch -D branch_name
```

> **Note:** `git checkout branch_name` and `git checkout -b branch_name` are the older commands that do the same as `git switch` / `git switch -c`. You will see both in tutorials.

---

## Merging Branches

```bash
# 1. Switch to the branch that will RECEIVE the changes
git switch main

# 2. Merge the other branch into it
git merge branch_name
```

| Type | When it happens | Merge commit? |
|---|---|---|
| **Fast-forward** | `main` has no new commits since the branch was created | No |
| **Three-way** | Both branches have new commits | Yes |
| **Squash** | You want all branch commits as **one** commit | No (one normal commit) |
| **Octopus** | Merging 3+ branches at once | Yes (with many parents) |

### Fast-Forward Merge

`main` has no new commits, so Git just moves `main` forward.

```text
Before:
main:     A --- B
                 \
feature:          C --- D

After:
main:     A --- B --- C --- D
```

> Practice

```bash
# Step 1: Create and switch to feature branch
git switch -c feature

# Step 2: Create a new file and commit
echo "Feature Code" > feature.txt
git add .
git commit -m "Add feature file"

# Step 3: Switch back to main
git switch main

# Step 4: Merge (fast-forward)
git merge feature
```

### Three-Way Merge

Both branches have new commits, so Git creates a **merge commit** `M` that joins them.

```text
Before:
main:     A --- B --- E
                 \
login:            C --- D

After:
main:     A --- B --- E --- M
                 \         /
login:            C --- D
```

> Practice

```bash
# Step 1: Create login-feature branch
git switch -c login-feature

# Step 2: Add a file on the feature branch
echo "Login Feature" > login.txt
git add .
git commit -m "Add login"

# Step 3: Switch back to main and add a different file
git switch main
echo "Main Update" > main.txt
git add .
git commit -m "Update main"

# Step 4: Merge (-m gives the merge commit a message, so no editor opens)
git merge login-feature -m "Merge login-feature into main"
```

### Squash Merge

Combines all commits of a branch into **one** new commit on `main`. Keeps the `main` history clean.

```text
ui-feature:   A --- B --- C(navbar) --- D(footer) --- E(sidebar)

After squash merge:
main:         A --- B --- F
                          (F = "Add UI feature": navbar + footer + sidebar)
```

> Practice

```bash
# Step 1: Create ui-feature branch
git switch -c ui-feature

# Step 2: Make multiple commits
echo "Navbar" > navbar.txt
git add .
git commit -m "Add navbar"

echo "Footer" > footer.txt
git add .
git commit -m "Add footer"

echo "Sidebar" > sidebar.txt
git add .
git commit -m "Add sidebar"

# Step 3: Switch to main
git switch main

# Step 4: Squash merge (stages all changes but does NOT commit yet)
git merge --squash ui-feature

# Step 5: Create the single combined commit
git commit -m "Add UI feature (navbar, footer, sidebar)"

# Step 6: Delete the branch (-D because Git does not see it as merged)
git branch -D ui-feature
```

### Octopus Merge

Merges **several** branches at once into one merge commit.

```text
Before:
feature-a:  A --- X
feature-b:  A --- Y
feature-c:  A --- Z

After:
main:  A ─────────────── M     (one merge commit with 4 parents: A, X, Y, Z)
       ├── X (feature-a) ┤
       ├── Y (feature-b) ┤
       └── Z (feature-c) ┘
```

> Practice

```bash
# Branch 1: feature-a
git switch -c feature-a
echo "A Feature" > a.txt
git add .
git commit -m "Add feature a"

# Branch 2: feature-b
git switch main
git switch -c feature-b
echo "B Feature" > b.txt
git add .
git commit -m "Add feature b"

# Branch 3: feature-c
git switch main
git switch -c feature-c
echo "C Feature" > c.txt
git add .
git commit -m "Add feature c"

# Switch to main and merge all three at once
git switch main
git merge feature-a feature-b feature-c -m "Octopus merge all features"
```

> **Note:** An octopus merge stops if there is any conflict. Then merge the branches one by one instead.

---

## Merge Conflicts

A **conflict** happens when two branches change the **same lines** of the same file. Git cannot decide which version to keep, so you must choose.

```bash
# See which files have conflicts
git status
```

Open the conflicted file. Git marks the conflict like this:

```text
<<<<<<< HEAD
Text from the current branch (main)
=======
Text from the incoming branch
>>>>>>> branch_name
```

**Resolve it:**
1. Keep the text you want (one side, the other, or a mix).
2. Delete the markers `<<<<<<<`, `=======`, `>>>>>>>`.
3. Save the file, then:

```bash
git add .
git commit -m "Resolve merge conflict"
```

> **Tip:** VS Code shows buttons above each conflict: **Accept Current Change**, **Accept Incoming Change**, **Accept Both Changes**, **Compare Changes**.

Cancel the merge and go back to how things were:

```bash
git merge --abort
```

> Practice (create a conflict on purpose)

```bash
echo "Hello" > greet.txt
git add .
git commit -m "Add greet"

git switch -c spanish
echo "Hola" > greet.txt
git commit -am "Spanish greeting"

git switch main
echo "Salaam" > greet.txt
git commit -am "Urdu greeting"

git merge spanish   # CONFLICT in greet.txt
```

---

## Stash

**Stash** temporarily saves uncommitted changes so you can switch branches with a clean working directory.

```bash
# Save uncommitted changes
git stash

# Save with a description (and include untracked files)
git stash push -u -m "half-done login page"

# See all stashes
git stash list

# Restore the latest stash and remove it from the list
git stash pop

# Restore without removing it from the list
git stash apply

# Restore a specific stash
git stash apply stash@{1}

# Delete the latest stash
git stash drop

# Delete all stashes
git stash clear
```

> Workflow

```bash
# Nobita is working on feature-login
# He edited login.txt but it is not ready to commit

# Urgent bug needs fixing! Stash current work
git stash

# Switch to main branch
git switch main

# Fix the bug
git add bugfix.txt
git commit -m "Fix urgent bug"
git push

# Go back to the feature branch
git switch feature-login

# Bring back the stashed work and continue
git stash pop
```

---

## Git Rebase

**Rebase** moves your branch's commits so they start from the **latest** commit of another branch. The result is a straight, clean history with no merge commit.

```text
Starting point:
main:     A --- B --- C
                 \
feature:          D --- E

MERGE (git merge main on feature):
main:     A --- B --- C
                 \     \
feature:          D --- E --- M    (merge commit M)

REBASE (git rebase main on feature):
main:     A --- B --- C
                       \
feature:                D' --- E'   (commits re-created on top of C)
```

```bash
# Nobita's feature branch is behind main
git switch feature-login

# Re-apply his commits on top of the latest main
git rebase main

# If there is a conflict: fix the file, then
git add .
git rebase --continue

# Or cancel the rebase
git rebase --abort
```

| Merge | Rebase |
|---|---|
| Keeps the full true history | Creates a clean straight-line history |
| Adds a merge commit | No merge commit |
| Safe for shared branches | **Only for local / unshared commits** |

> **Golden rule:** Never rebase commits that have been pushed to GitHub and shared with others. Only rebase your own local commits.

---

## Cherry-Pick

Copy **one specific commit** from another branch onto the current branch:

```bash
# Find the commit code on the other branch
git log --oneline feature-login

# Apply that commit to the current branch
git switch main
git cherry-pick commit_code
```

> Useful when you need just one bug fix from a branch, without merging the whole branch.

---

## Tags

Tags mark important commits, usually **release versions** (`v1.0`, `v2.1`).

```bash
# Create a lightweight tag on the current commit
git tag v1.0

# Create an annotated tag with a message (recommended for releases)
git tag -a v1.0 -m "First release"

# Tag an older commit
git tag v0.9 commit_code

# List tags
git tag

# See tag details
git show v1.0

# Push one tag
git push origin v1.0

# Push all tags
git push origin --tags

# Delete a tag (local and remote)
git tag -d v1.0
git push origin --delete v1.0
```

> **Note:** `git push` does **not** push tags automatically.

---

## Remote Repository

A **remote** is a link to a repository on GitHub. The default name is `origin`.

```bash
# Add a GitHub remote
git remote add origin https://github.com/username/repository.git

# Check remotes
git remote -v

# Change the URL (e.g. switch from HTTPS to SSH)
git remote set-url origin git@github.com:username/repository.git

# Rename a remote
git remote rename origin upstream

# Remove a remote
git remote remove origin
```

**Push an existing local project to a new GitHub repo:**
1. On GitHub: **New repository** → give it a name → **do not** add a README → **Create repository**.
2. In your project folder:

```bash
git remote add origin https://github.com/username/repository.git
git branch -M main
git push -u origin main
```

---

## Clone Repository

Download a full copy of an existing GitHub repository (all files + complete history):

```bash
# Clone into a folder with the repository's name
git clone https://github.com/username/repository.git

# Clone into a folder with a different name
git clone https://github.com/username/repository.git my-folder

# Enter the repository
cd repository
```

> Cloning automatically sets up the `origin` remote.

---

## Push, Pull & Fetch

```text
             git push  ────────►
 Local Repo                         GitHub (origin)
             ◄────────  git pull / git fetch
```

### Push

Upload local commits to GitHub:

```bash
# First push of a branch: -u links local main to origin/main
git push -u origin main

# After that, just
git push
```

### Pull

Download the latest changes **and merge** them into your current branch:

```bash
git pull origin main

# or, if upstream is already set
git pull
```

### Fetch

Download remote changes **without** merging, so you can look before you merge:

```bash
# Fetch from origin
git fetch origin

# See what changed on GitHub compared to your branch
git log --oneline main..origin/main

# Merge when ready
git merge origin/main
```

> **fetch** = download changes only\
> **pull** = fetch + merge

> **Error "rejected – fetch first":** someone pushed before you. Run `git pull`, fix any conflicts, then `git push` again.

### Daily Workflow

```bash
# 1. Always start by downloading the latest code
git pull

# 2. Make your changes in the editor...

# 3. Check what changed
git status

# 4. Stage all changes
git add .

# 5. Commit with a message
git commit -m "Describe what you changed"

# 6. Upload to GitHub
git push
```

---

## Remote Branches

**Push a branch to GitHub:**

```bash
# Nobita creates a feature branch locally
git switch -c feature-login

# Makes changes and commits
git add login.txt
git commit -m "Add login page"

# Pushes the branch to GitHub
git push -u origin feature-login
```

**View branches:**

```bash
# Local branches only
git branch

# Remote branches only
git branch -r

# All branches (local + remote)
git branch -a
```

**Check out someone else's remote branch:**

```bash
# Suneo wants to see Nobita's feature branch
git fetch origin
git switch feature-login     # creates a local branch tracking origin/feature-login
```

**Delete branches:**

```bash
# Delete the branch from GitHub
git push origin --delete feature-login

# Delete the local branch
git branch -d feature-login

# Remove local references to branches already deleted on GitHub
git fetch --prune
```

---

## Fork & Pull Request Workflow

Use this when you want to contribute to a repository that you **do not own** (open source, a classmate's project).

| Remote | Points to | Meaning |
|---|---|---|
| `origin` | **Your fork** | YOU — you can push here |
| `upstream` | **Original repository** | ORIGINAL OWNER — you only pull from here |

### Step 1 — Fork the Repository

On GitHub, open the original repository → click **Fork** (top-right).

```text
gian-doraemon/school-project   (Gian's original repo)
              │
            Fork
              ▼
nobita-nobi/school-project     (Nobita's copy on GitHub)
```

### Step 2 — Clone Your Fork

Clone **your fork**, not the original repository:

```bash
git clone git@github.com:nobita-nobi/school-project.git
cd school-project

git remote -v
# origin  git@github.com:nobita-nobi/school-project.git  → your fork
```

### Step 3 — Add the Original Repo as Upstream

```bash
git remote add upstream git@github.com:gian-doraemon/school-project.git

git remote -v
# origin    → your fork
# upstream  → original repository
```

### Step 4 — Create a Branch and Make Changes

Always create a separate branch for your changes — never work directly on `main`.

```bash
git switch -c fix-homepage

# Make your changes, then:
git add homepage.txt
git commit -m "Fix homepage title"
```

### Step 5 — Push to Your Fork

```bash
git push -u origin fix-homepage
```

```text
Local branch fix-homepage  ──push──►  origin (your GitHub fork)
```

### Step 6 — Create a Pull Request

1. Open your fork on GitHub → click **Compare & pull request**.
2. Check the direction:

| | Repository | Branch |
|---|---|---|
| **base** (receives changes) | `gian-doraemon/school-project` | `main` |
| **compare** (your changes) | `nobita-nobi/school-project` | `fix-homepage` |

3. Write a clear title and description → **Create pull request**.

```text
Your fork: fix-homepage  ──Pull Request──►  Original repo: main
```

### Step 7 — Review & Merge

The original owner reviews your Pull Request:

```text
Review code → Comments / requested changes → Approve → Merge Pull Request
```

> If changes are requested, just commit and push again to the **same branch** — the Pull Request updates automatically.\
> After merging, your changes become part of the original repository.

### Step 8 — Sync Your Fork with Upstream

When the original repository gets new commits, update your fork:

```bash
git switch main
git pull upstream main
git push origin main
```

```text
Original repo ──► upstream ──► local main ──► origin ──► your fork
```

> **Tip:** You can also click **Sync fork** on your fork's GitHub page.

### Complete Fork Workflow

```text
FORK → CLONE → ADD UPSTREAM → CREATE BRANCH → MAKE CHANGES → COMMIT
     → PUSH TO ORIGIN → PULL REQUEST → REVIEW → MERGE → SYNC WITH UPSTREAM
```

---

## Team Workflow on a Shared Remote Branch

When teammates have **write access** to the same repository, they can share branches directly (no fork needed).

Suppose Suneo pushed a branch `origin/feature-database`:

```bash
# 1. Download the latest branches
git fetch origin

# 2. See remote branches
git branch -r
#   origin/main
#   origin/feature-database
#   origin/fix-homepage

# 3. Create a local branch from the remote branch
git switch -c feature-database origin/feature-database
```

```text
origin/feature-database (remote)  ──►  feature-database (local)
```

```bash
# 4. Nobita edits the files, then pushes back to the same branch
git add database.txt
git commit -m "Fix database connection string"
git push origin feature-database
```

```bash
# 5. Suneo updates his local copy
git switch feature-database
git pull origin feature-database
```

---

## Basic GitHub Workflow

```bash
git clone repository-url
cd repository

git switch -c feature-name

# Make changes

git status
git add .
git commit -m "Add feature"

git push -u origin feature-name
```

> Then create a **Pull Request** on GitHub.

---
### Author
- Author: __MUHAMMAD SHEHZAD__
- GitHub: https://github.com/dbdmlabs
