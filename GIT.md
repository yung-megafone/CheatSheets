# Git Commands Cheat Sheet

## 📌 Overview
This cheat sheet provides a structured guide to common Git commands, their usage, and where files reside in the staging process.

## 🛠 Git Workflow Stages

1. **Untracked** → File is new and not yet tracked by Git.
2. **Staged** → File is added to Git and ready to be committed.
3. **Committed** → File is stored in the local repository.
4. **Pushed** → Committed changes are sent to a remote repository (e.g., GitHub).

---

## 🔍 Checking Repository Status
| Command | Description |
|---------|-------------|
| `git status` | Show the working directory and staging area status. |
| `git log --oneline --graph --decorate --all` | View commit history in a simplified format. |
| `git diff` | Show changes between the working directory and the staging area. |
| `git branch` | List all local branches. |
| `git branch -r` | List all remote branches. |
| `git remote -v` | Show configured remote repositories. |

---

## 📂 Staging Files (Adding Changes)
| Command | Description |
|---------|-------------|
| `git add file.txt` | Stage a specific file. |
| `git add .` | Stage **all** new and modified files. |
| `git reset file.txt` | Unstage a specific file before committing. |
| `git reset` | Unstage all files while keeping changes. |

---

## 💾 Committing Changes
| Command | Description |
|---------|-------------|
| `git commit -m "Your message"` | Commit staged changes with a message. |
| `git commit -am "Your message"` | Stage **modified** files and commit (excludes untracked files). |
| `git commit --amend -m "New message"` | Edit the last commit message. |

---

## 🌍 Pushing and Pulling Changes
| Command | Description |
|---------|-------------|
| `git push origin main` | Push local commits to the `main` branch on GitHub. |
| `git pull origin main` | Pull the latest changes from the `main` branch on GitHub. |
| `git fetch origin` | Download latest changes without merging them. |
| `git merge origin/main` | Merge remote changes into your local branch. |

---

## 🔄 Undoing Changes
| Command | Description |
|---------|-------------|
| `git checkout -- file.txt` | Discard changes in a specific file. |
| `git reset --hard` | Reset all changes **(Caution: Irreversible)**. |
| `git revert <commit_hash>` | Undo a commit **without losing history**. |

---

## 🚀 Branching & Merging
| Command | Description |
|---------|-------------|
| `git branch feature-branch` | Create a new branch. |
| `git checkout feature-branch` | Switch to another branch. |
| `git checkout -b new-branch` | Create and switch to a new branch. |
| `git merge feature-branch` | Merge `feature-branch` into the current branch. |
| `git branch -d feature-branch` | Delete a local branch after merging. |

---

## 🛠 Handling Merge Conflicts
| Command | Description |
|---------|-------------|
| `git merge --abort` | Cancel a merge if there are conflicts. |
| `git status` | See which files have merge conflicts. |
| **Manually resolve conflicts, then:** |
| `git add .` | Stage resolved files. |
| `git commit -m "Resolved merge conflicts"` | Finalize the merge. |

---

## ⚡ Force Push (Use With Caution!)
| Command | Description |
|---------|-------------|
| `git push --force origin main` | Overwrite remote changes with local changes. |
| `git reset --hard origin/main` | Reset local branch to match the remote. |

---

## 🚀 Reset & Clean Up Commands
| Command | Description |
|---------|-------------|
| `git reset --soft HEAD~1` | Undo last commit but keep changes staged. |
| `git reset --hard HEAD~1` | Undo last commit and discard changes. |
| `git clean -f` | Remove untracked files (use cautiously). |

---

## 🌟 Summary: Most Common Commands
```bash
# Check repository status
git status

# Stage all changes
git add .

# Commit changes with a message
git commit -m "Commit message"

# Push to GitHub
git push origin main

# Pull latest updates
git pull origin main

# Create and switch to a new branch
git branch feature-branch
git checkout feature-branch

# Merge a branch into main
git merge feature-branch

# Delete a branch after merging
git branch -d feature-branch
```

---

## 📜 Final Notes
- 🛑 **Avoid force-pushing (`git push --force`) unless necessary** to prevent overwriting history.
- 🔥 **Commit frequently** to avoid losing progress.
- 🚀 **Use `git status` often** to track staged and unstaged changes.