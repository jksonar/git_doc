Here’s a comprehensive list of Git commands for managing branches:

---

### **1. View Branches**
- **List all branches (local and remote):**
  ```bash
  git branch -a
  ```

- **List only local branches:**
  ```bash
  git branch
  ```

---

### **2. Create a Branch**
- **Create a new branch:**
  ```bash
  git branch <branch-name>
  ```

- **Create and switch to a new branch:**
  ```bash
  git checkout -b <branch-name>
  ```
  OR (newer Git versions):
  ```bash
  git switch -c <branch-name>
  ```

---

### **3. Switch Between Branches**
- **Switch to an existing branch:**
  ```bash
  git checkout <branch-name>
  ```
  OR (newer Git versions):
  ```bash
  git switch <branch-name>
  ```

---

### **4. Rename a Branch**
- **Rename the current branch:**
  ```bash
  git branch -m <new-name>
  ```

- **Rename a specific branch:**
  ```bash
  git branch -m <old-name> <new-name>
  ```

---

### **5. Delete a Branch**
- **Delete a local branch:**
  ```bash
  git branch -d <branch-name>
  ```
  (Use `-D` instead of `-d` to force delete an unmerged branch.)

- **Delete a remote branch:**
  ```bash
  git push origin --delete <branch-name>
  ```

---

### **6. Merge Branches**
- **Merge another branch into the current branch:**
  ```bash
  git merge <branch-name>
  ```

---

### **7. Rebase a Branch**
- **Rebase the current branch onto another branch:**
  ```bash
  git rebase <branch-name>
  ```

---

### **8. Track Remote Branches**
- **Create a local branch that tracks a remote branch:**
  ```bash
  git checkout -b <branch-name> origin/<branch-name>
  ```
  OR (newer Git versions):
  ```bash
  git switch --track origin/<branch-name>
  ```

- **Set an existing branch to track a remote branch:**
  ```bash
  git branch --set-upstream-to=origin/<branch-name>
  ```

---

### **9. View Branch Tracking Information**
- **Check which remote branch a local branch is tracking:**
  ```bash
  git status
  ```

- **Show branch tracking information:**
  ```bash
  git branch -vv
  ```

---

### **10. Stash Changes Before Switching Branches**
- **Stash uncommitted changes:**
  ```bash
  git stash
  ```

- **Apply stashed changes after switching branches:**
  ```bash
  git stash apply
  ```

---

### **11. Compare Branches**
- **Compare the current branch with another branch:**
  ```bash
  git diff <branch-name>
  ```

- **Compare two specific branches:**
  ```bash
  git diff <branch1> <branch2>
  ```

---

### **12. Push and Pull Branches**
- **Push a branch to a remote repository:**
  ```bash
  git push origin <branch-name>
  ```

- **Pull updates from the remote repository:**
  ```bash
  git pull origin <branch-name>
  ```

---

### **13. Create a Branch from a Specific Commit**
- **Create a branch from a specific commit hash:**
  ```bash
  git checkout -b <branch-name> <commit-hash>
  ```

---

### **14. View Branch History**
- **View a branch’s commit history:**
  ```bash
  git log <branch-name>
  ```

- **View a graphical representation of branches:**
  ```bash
  git log --oneline --graph --all
  ```

---

### **15. Sync a Branch with Another Branch**
- **Reset a branch to match another branch (force sync):**
  ```bash
  git reset --hard <branch-name>
  ```

---

### **Common Workflows**
- **Create a new feature branch and push to remote:**
  ```bash
  git checkout -b feature/new-feature
  git push -u origin feature/new-feature
  ```

- **Update a feature branch with changes from `main`:**
  ```bash
  git checkout feature/new-feature
  git rebase main
  ```

- **Delete a merged branch:**
  ```bash
  git branch -d feature/old-feature
  ```

Let me know if you want to dive deeper into any of these commands!