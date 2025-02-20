# Git Workflow Tasklist: Pushing Changes to GitHub

This guide walks you through the **complete process** of staging, committing, and pushing changes to GitHub while avoiding common mistakes and conflicts.

---

## **🚀 Step 1: Verify You’re in the Right Directory**
Before starting, make sure you are in the correct project folder:
```bash
pwd  # Shows your current directory (Mac/Linux)
cd   # Shows current directory (Windows)
ls   # Lists files in the directory
```
If you’re **not in the correct repo folder**, navigate to it:
```bash
cd /path/to/your/repo
```

---

## **✅ Step 2: Check Git Status**
See what files have changed, been staged, or are untracked:
```bash
git status
```
### **Interpreting the Output:**
- 🔴 **Untracked files** → Not in Git yet (Needs `git add`)
- 🟡 **Modified files** → Tracked but changed (Needs `git add`)
- 🟢 **Staged files** → Ready for commit (Needs `git commit`)
- ✅ **No changes** → Nothing new to commit

---

## **✅ Step 3: Stage Your Changes**
Stage **all** modified & new files:
```bash
git add .
```
Or **stage a specific file**:
```bash
git add filename.txt
```
🔹 **To verify staged files:**
```bash
git status
```
- Files will be **green** if staged correctly.

---

## **✅ Step 4: Commit the Changes**
Commit your changes with a meaningful message:
```bash
git commit -m "Descriptive message about what changed"
```
### **Good vs. Bad Commit Messages:**
❌ `"Updated files"` (Too vague)
✅ `"Fixed login issue by correcting API call"` (Descriptive)

---

## **✅ Step 5: Verify Your Commit History**
Check that your commit was recorded:
```bash
git log --oneline --graph --decorate --all
```
This shows recent commits in a **clean, visual format**.

---

## **✅ Step 6: Verify Your Remote Repository**
Ensure you’re pushing to the correct GitHub repository:
```bash
git remote -v
```
🔹 **If the remote is incorrect, update it:**
```bash
git remote set-url origin git@github.com:your-username/repo-name.git
```

---

## **✅ Step 7: Pull Latest Changes (To Prevent Conflicts)**
Before pushing, sync your repo with GitHub to **avoid conflicts**:
```bash
git pull origin main --rebase
```
🔹 **If a merge conflict occurs:**
1. Run `git status` to see conflicting files.
2. Open the files, **manually fix conflicts**, then run:
```bash
git add .
git commit -m "Resolved merge conflicts"
```

---

## **✅ Step 8: Push to GitHub**
Once everything is staged & committed, push your changes:
```bash
git push origin main
```
If pushing a **new branch**:
```bash
git push -u origin branch-name
```
🔹 **Verify your changes on GitHub**: Go to your **repository page** and confirm the latest commit appears.

---

## **✅ Step 9: Final Verification & Cleanup**
1. Confirm everything is up-to-date:
```bash
git status
```
   - Should return: `nothing to commit, working tree clean`

2. Check your **commit history**:
```bash
git log --oneline --graph --decorate --all
```
   - This ensures your commit was **successfully added.**

3. 🎉 **You’re done!** 🎉

---

## **🚀 Quick Cheat Sheet**
```bash
# 1. Check status
git status

# 2. Stage changes
git add .

# 3. Commit changes
git commit -m "Descriptive commit message"

# 4. Pull latest updates (avoid conflicts)
git pull origin main --rebase

# 5. Push to GitHub
git push origin main

# 6. Verify everything is up to date
git status
git log --oneline --graph --decorate --all
```

---

## **🛑 Common Issues & Fixes**
| Issue | Fix |
|-------|-----|
| `fatal: not a git repository` | Run `git init` inside the project folder |
| `error: failed to push some refs` | Run `git pull origin main --rebase` first |
| `merge conflicts` | Open conflicting files, fix manually, then `git add .` and `git commit -m "Resolved conflicts"` |
| `push rejected due to branch protection` | Ensure you have write access or create a PR (pull request) |

---

### **🚀 Final Thoughts**
This workflow **prevents errors, ensures smooth commits, and avoids conflicts.**  
With practice, this will become second nature!