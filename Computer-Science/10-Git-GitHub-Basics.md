# Git & GitHub Basics

Git is a distributed version control system that tracks changes in code.
GitHub is a web-based platform to host and share Git repositories.

---

## 1. What is Git?
- Free, open-source version control system
- Tracks every change in your code
- Enables collaboration
- Works locally and remotely

---

## 2. What is GitHub?
- Cloud platform for Git repositories
- Share code with others
- Collaborate on projects
- Issues, pull requests, CI/CD

---

## 3. Basic Git Concepts

### Repository (Repo)
A folder containing your project and Git history.

### Commit
A snapshot of your code at a point in time.

### Branch
A separate line of development.
- `main` / `master`: default branch
- Feature branches: for new work

### Remote
A hosted repository (like on GitHub).

---

## 4. Essential Git Commands

### Setup
```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

### Create / Clone
```bash
git init              # Initialize new repo
git clone <url>       # Download existing repo
```

### Daily Workflow
```bash
git status            # Check changes
git add .             # Stage all changes
git commit -m "Message"  # Commit
git push              # Upload to GitHub
git pull              # Download latest changes
```

### Branch Workflow
```bash
git branch            # List branches
git branch <name>     # Create branch
git checkout <name>   # Switch branch
git merge <name>      # Merge branch
```

---

## 5. GitHub Workflow

### 1. Create repo on GitHub
### 2. Push local code to GitHub
### 3. Create branch for feature
### 4. Make commits
### 5. Open Pull Request (PR)
### 6. Review & merge
### 7. Pull latest main

---

## 6. Important Terms

### Fork
Copy someone else’s repo to your GitHub.

### Pull Request (PR)
Propose changes to a repo.

### Merge
Combine branches together.

### Conflict
When Git can’t auto‑merge changes.
Must fix manually.

### Issue
Track tasks, bugs, or ideas.

---

## 7. Collaboration Rules
- Commit often with clear messages
- Pull before you push
- Use feature branches
- Write meaningful PR descriptions
- Review code before merging

---

## 8. .gitignore
File that tells Git what to ignore:
- node_modules
- __pycache__
- .env
- .DS_Store
- build/

---

## 9. Common Git Mistakes & Fixes
- Accidental commit: `git reset`
- Wrong commit message: `git commit --amend`
- Merge conflict: edit files → commit
- Lost code: use `git reflog`

---

## 10. Why Learn Git & GitHub?
- Track code history
- Work in teams safely
- Build a professional portfolio
- Required for almost all dev jobs
- Show your work to employers

---

## 11. Common Interview Questions
1. What is Git? What is GitHub?
2. Explain commit, branch, merge
3. What is a pull request?
4. How to resolve merge conflicts?
5. What is .gitignore?
6. Git workflow in a team
7. Fork vs clone
