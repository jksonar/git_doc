Here’s a curated list of essential Git commands you’ll likely use daily, organized by common tasks:

---

### **1. Basic Commands**
- **Check the status of your repository:**
  ```bash
  git status
  ```
  Shows untracked files, changes staged for commit, and the current branch.

- **View the commit history:**
  ```bash
  git log
  ```
  Use `--oneline` for a concise view:
  ```bash
  git log --oneline
  ```

- **See changes in your working directory:**
  ```bash
  git diff
  ```
  To view changes staged for commit:
  ```bash
  git diff --staged
  ```

---

### **2. Branch Management**
- **List all branches:**
  ```bash
  git branch -a
  ```

- **Create a new branch:**
  ```bash
  git checkout -b <branch-name>
  ```
  OR:
  ```bash
  git switch -c <branch-name>
  ```

- **Switch branches:**
  ```bash
  git checkout <branch-name>
  ```
  OR:
  ```bash
  git switch <branch-name>
  ```

- **Delete a branch:**
  ```bash
  git branch -d <branch-name>
  ```
  Use `-D` to force delete an unmerged branch:
  ```bash
  git branch -D <branch-name>
  ```

---

### **3. Pull, Push, and Fetch**
- **Pull the latest changes from a remote branch:**
  ```bash
  git pull
  ```
  With rebase:
  ```bash
  git pull --rebase
  ```

- **Push changes to a remote branch:**
  ```bash
  git push origin <branch-name>
  ```

- **Fetch updates without merging:**
  ```bash
  git fetch
  ```

---

### **4. Staging and Committing**
- **Stage files for commit:**
  ```bash
  git add <file>
  ```
  Stage all changes:
  ```bash
  git add .
  ```

- **Commit changes:**
  ```bash
  git commit -m "Commit message"
  ```

- **Amend the last commit (e.g., to fix a commit message):**
  ```bash
  git commit --amend
  ```

---

### **5. Stashing**
- **Stash uncommitted changes:**
  ```bash
  git stash
  ```

- **View stashed changes:**
  ```bash
  git stash list
  ```

- **Apply the latest stash:**
  ```bash
  git stash apply
  ```

- **Apply and drop the stash:**
  ```bash
  git stash pop
  ```

---

### **6. Rebasing and Merging**
- **Rebase the current branch onto another branch:**
  ```bash
  git rebase <branch-name>
  ```

- **Merge another branch into the current branch:**
  ```bash
  git merge <branch-name>
  ```

- **Abort a merge or rebase:**
  ```bash
  git merge --abort
  git rebase --abort
  ```

- **Continue rebase after resolving conflicts:**
  ```bash
  git rebase --continue
  ```

---

### **7. Viewing and Managing Remotes**
- **List remote repositories:**
  ```bash
  git remote -v
  ```

- **Add a remote:**
  ```bash
  git remote add origin <repository-URL>
  ```

- **Remove a remote:**
  ```bash
  git remote remove <name>
  ```

---

### **8. Undoing Changes**
- **Discard unstaged changes:**
  ```bash
  git checkout -- <file>
  ```

- **Unstage a file:**
  ```bash
  git reset <file>
  ```

- **Reset the branch to a previous commit:**
  ```bash
  git reset --hard <commit-hash>
  ```

- **Undo the last commit (keep changes):**
  ```bash
  git reset --soft HEAD~1
  ```

---

### **9. Viewing and Comparing**
- **View details of a specific commit:**
  ```bash
  git show <commit-hash>
  ```

- **Compare branches:**
  ```bash
  git diff <branch1> <branch2>
  ```

- **View file history:**
  ```bash
  git log -- <file>
  ```

---

### **10. Tagging**
- **Create a tag:**
  ```bash
  git tag <tag-name>
  ```

- **Push tags to remote:**
  ```bash
  git push origin --tags
  ```

- **Delete a tag:**
  ```bash
  git tag -d <tag-name>
  ```

---

### **11. Cloning and Initializing**
- **Clone a repository:**
  ```bash
  git clone <repository-URL>
  ```

- **Initialize a new repository:**
  ```bash
  git init
  ```

---

### **12. Git Configurations**
- **Set global username:**
  ```bash
  git config --global user.name "Your Name"
  ```

- **Set global email:**
  ```bash
  git config --global user.email "you@example.com"
  ```

- **Check configurations:**
  ```bash
  git config --list
  ```

---

### **Daily Workflow Example**

1. **Start Your Work:**
   ```bash
   git checkout -b feature/new-feature
   ```

2. **Work on Files:**
   ```bash
   git add .
   git commit -m "Implemented new feature"
   ```

3. **Sync With Remote:**
   ```bash
   git fetch origin
   git rebase origin/main
   ```

4. **Push Your Changes:**
   ```bash
   git push origin feature/new-feature
   ```

5. **Create a Pull Request:** 
   Use your Git platform (GitHub, GitLab, etc.) for this.

---
