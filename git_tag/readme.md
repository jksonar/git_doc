### **How to Use Git Tags**

Git tags are used to mark specific points in a repository's history, typically to denote releases or significant milestones. There are two types of tags in Git: **lightweight** and **annotated**.

#### **1. Creating a Tag**
- **Lightweight Tag**: A simple pointer to a specific commit.
  ```bash
  git tag <tag_name>
  ```
- **Annotated Tag**: Includes metadata (e.g., message, author, date). This is recommended for releases.
  ```bash
  git tag -a <tag_name> -m "Tag message"
  ```

#### **2. Viewing Tags**
To list all tags:
```bash
git tag
```
To filter tags:
```bash
git tag -l "v1.*"
```

#### **3. Pushing Tags to a Remote Repository**
After creating a tag, you must push it to the remote repository:
- Push a specific tag:
  ```bash
  git push origin <tag_name>
  ```
- Push all tags:
  ```bash
  git push origin --tags
  ```

#### **4. Deleting Tags**
- Locally:
  ```bash
  git tag -d <tag_name>
  ```
- Remotely:
  ```bash
  git push origin --delete <tag_name>
  ```

#### **5. Checking Out a Tag**
To check out a tag, creating a "detached HEAD" state:
```bash
git checkout <tag_name>
```

If you want to make changes, create a branch:
```bash
git checkout -b <branch_name> <tag_name>
```

---

### **Best Practices for Git Tags**

1. **Use Semantic Versioning**  
   Follow a standard like Semantic Versioning (e.g., `v1.0.0`, `v2.1.3`) to clearly convey the significance of changes:
   - `MAJOR.MINOR.PATCH`
   - Increment MAJOR for incompatible changes, MINOR for backward-compatible features, and PATCH for fixes.

2. **Use Annotated Tags for Releases**  
   Annotated tags provide more information, such as the author and message, making them ideal for releases.

3. **Automate Tagging in CI/CD Pipelines**  
   Automatically create and push tags as part of your release process. For example:
   ```bash
   git tag -a "v$(date +%Y%m%d%H%M%S)" -m "Automated release"
   ```

4. **Include Descriptive Messages**  
   Always add a meaningful message to explain the purpose of the tag:
   ```bash
   git tag -a v1.0.0 -m "Initial stable release"
   ```

5. **Protect Tags in the Remote Repository**  
   Use repository settings to prevent accidental deletion or overwriting of important tags.

6. **Avoid Overwriting Tags**  
   Tags should be immutable. If a tag is created in error, delete it and create a new one instead of overwriting:
   ```bash
   git tag -d <tag_name>
   git push origin --delete <tag_name>
   git tag -a <new_tag_name> -m "Corrected tag"
   ```

7. **Standardize Tag Naming Across Teams**  
   Agree on a naming convention within your team to maintain consistency. For example:
   - Use `v` as a prefix for versions: `v1.0.0`.
   - Use tags for environment-specific releases: `prod-v1.0.0`, `staging-v1.0.0`.

8. **Document Tag Usage**  
   Include documentation in your project's README or CONTRIBUTING file about how your team uses tags.

By following these practices, you'll have a well-organized repository with clear and meaningful tags, aiding in version control and collaboration.


---
### **Add Old Commit To GIT tag**

To create a tag for an older commit in Git, you can specify the commit hash when creating the tag. Here's how:

### **Steps to Tag an Old Commit**

1. **Find the Commit Hash**  
   Locate the hash of the commit you want to tag. You can use the following command to view the commit history:
   ```bash
   git log --oneline
   ```
   Example output:
   ```
   a1b2c3d Fix bug in user login
   e4f5g6h Add new feature
   i7j8k9l Initial commit
   ```

   Note the hash (e.g., `a1b2c3d`) of the commit you want to tag.

2. **Create the Tag**  
   Use the commit hash to create a tag:
   - **Annotated Tag** (recommended):
     ```bash
     git tag -a <tag_name> <commit_hash> -m "Tag message"
     ```
   - **Lightweight Tag**:
     ```bash
     git tag <tag_name> <commit_hash>
     ```

   Example:
   ```bash
   git tag -a v1.0.0 a1b2c3d -m "Release version 1.0.0"
   ```

3. **Push the Tag to the Remote Repository**  
   After creating the tag, push it to the remote repository:
   ```bash
   git push origin <tag_name>
   ```
   Or push all tags:
   ```bash
   git push origin --tags
   ```

---

### **Example Workflow**

Suppose you want to tag the commit `e4f5g6h` as `v1.1.0`:

1. View the commit history:
   ```bash
   git log --oneline
   ```
   Output:
   ```
   a1b2c3d Fix bug in user login
   e4f5g6h Add new feature
   i7j8k9l Initial commit
   ```

2. Create an annotated tag:
   ```bash
   git tag -a v1.1.0 e4f5g6h -m "Release version 1.1.0"
   ```

3. Push the tag to the remote:
   ```bash
   git push origin v1.1.0
   ```

---

### **Verifying the Tag**

To confirm that the tag is pointing to the correct commit:
```bash
git show <tag_name>
```

Example:
```bash
git show v1.1.0
```
This will display the details of the tagged commit, including the commit message and associated changes.
---

### **Git revert to a previous tag then push to origin:master**

There are 2 ways to do that

## Reset the HEAD then force push to remote

```bash
$ git checkout master
$ git pull
$ git reset --hard tag_ABC
$ git push --force origin master
```

## Make a new revert commit then push to remote (or create a new branch and make a PR)

```bash
$ git checkout 1.1.1
$ git diff master > ~/diff.patch
$ git checkout master
$ cat ~/diff.patch | git apply
$ git commit -am 'Rolled back to version 1.1.1'
$ git push origin master
```

## Create new Branch form git tag
```bash
git checkout -b newbranch v1.0
```