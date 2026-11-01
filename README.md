# Git & GitHub Fundamentals Practice

A hands-on practice repository for learning and understanding Git and GitHub fundamentals. This repository covers essential version control concepts, Git commands, SSH authentication, branching strategies, commits, remote repositories, and Pull Request workflows.

The goal is to build practical experience with Git and GitHub through small exercises and real-world development workflows.

---

## Learning Objectives

- Understand Git and GitHub fundamentals
- Learn basic Git commands and version control
- Configure Git username and email
- Clone and manage remote repositories
- Understand Git branches and feature-based workflows
- Stage, commit, and push changes
- Practice SSH authentication with GitHub
- Create and manage Pull Requests
- Understand the difference between committing and merging
- Learn how to collaborate through code reviews

---

## Git & GitHub Basics

### What is Git?

Git is a distributed version control system used to track changes in source code and manage project history.

### What is GitHub?

GitHub is a cloud-based platform for hosting Git repositories and collaborating with other developers.

### Git vs GitHub

| Git | GitHub |
|---|---|
| Version control system | Code hosting platform |
| Tracks changes locally | Hosts remote repositories |
| Manages commits and branches | Supports Pull Requests and code reviews |
| Works through the command line | Provides a web-based interface |

---

## Git Configuration

Configure your identity before making commits:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Verify the configuration:

```bash
git config --global user.name
git config --global user.email
```

---

## GitHub SSH Authentication

SSH allows Git to securely communicate with GitHub using an SSH key.

### 1. Generate an SSH Key

```bash
ssh-keygen -t ed25519 -C "your-email@example.com"
```

### 2. Add the Public Key to GitHub

Display the public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

Add it under:

**GitHub → Settings → SSH and GPG keys → New SSH key**

Never share your private SSH key.

### 3. Test SSH Authentication

```bash
ssh -T git@github.com
```

### 4. Clone Using SSH

```bash
git clone git@github.com:username/repository.git
```

### 5. Verify Remote Configuration

```bash
git remote -v
```

---

## Essential Git Commands

| Command | Purpose |
|---|---|
| `git init` | Initialize a Git repository |
| `git clone <url>` | Clone a remote repository |
| `git status` | Check repository status |
| `git add <file>` | Stage changes |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Save changes in Git history |
| `git log --oneline` | View commit history |
| `git diff` | View unstaged changes |
| `git restore <file>` | Discard unstaged changes |

---

## Git Branching

Branches allow developers to work on different features or fixes without directly modifying the main branch.

### Common Branch Commands

```bash
# List branches
git branch

# Create and switch to a new branch
git switch -c feature/new-feature

# Switch to an existing branch
git switch main

# Delete a local branch
git branch -d feature/new-feature
```

### Feature Branch Workflow

A typical development workflow:

```text
       main
         |
         |
    Create Branch
         |
         ▼
   feature/branch
         |
         ▼
    Make Changes
         |
         ▼
     git add
         |
         ▼
    git commit
         |
         ▼
     git push
         |
         ▼
    Pull Request
         |
         ▼
    Code Review
         |
         ▼
      Merge
         |
         ▼
        main
```

---

## Commits and Merging

### What is a Commit?

A commit saves a snapshot of staged changes in the local Git repository's history.

```bash
git add README.md
git commit -m "docs: update README"
```

### What is a Merge?

A merge combines changes from one branch into another branch.

```bash
git switch main
git merge feature/new-feature
```

### Commit vs Merge

| Commit | Merge |
|---|---|
| Saves changes in Git history | Combines changes from different branches |
| Usually records work on the current branch | Integrates another branch into the current branch |
| Does not automatically combine branches | May create a merge commit |

---

## Pull Requests (PR)

A Pull Request is a GitHub feature that allows developers to propose changes from one branch into another branch for review.

### Pull Request Workflow

1. Create a feature branch.
2. Make changes to project files.
3. Stage and commit the changes.
4. Push the feature branch to GitHub.
5. Open a Pull Request.
6. Review the proposed changes.
7. Merge the Pull Request when approved.

### Push a Feature Branch

```bash
git push -u origin feature/new-feature
```

### Creating a Pull Request

On GitHub:

- Open the repository.
- Select the Pull Requests tab.
- Click New Pull Request.
- Select the base branch (`main`).
- Select your feature branch.
- Review the changes and create the Pull Request.

A Pull Request can be opened within your own repository. You do not need to contribute to someone else's repository to practice this workflow.

---

## Remote Repository Management

```bash
# View remote repositories
git remote -v

# Download remote changes
git fetch

# Download and integrate remote changes
git pull

# Push commits to a remote repository
git push

# Push a new branch and set upstream
git push -u origin feature/new-feature
```

---

## Hands-on Practice Tasks

This repository is used to practice Git and GitHub concepts through practical exercises.

### Task 01 — Git Installation and Configuration

- Verify Git installation.
- Configure Git username and email.
- Verify global Git configuration.

### Task 02 — Repository Cloning

- Clone an existing GitHub repository.
- Navigate into the local repository.
- Check repository status and remote configuration.

### Task 03 — Branching and Pull Requests

- Create a new feature branch.
- Make a small change to a project file.
- Stage and commit the changes.
- Push the feature branch to GitHub.
- Open a Pull Request for review.
- Understand committing versus merging.
- Capture a screenshot of the created Pull Request.

### Task 04 — SSH Authentication

- Generate an SSH key pair.
- Add the public key to GitHub.
- Verify SSH authentication.
- Clone and push repositories using SSH.

---

## Standard Git Workflow

The following commands represent a typical daily Git workflow:

```bash
# Check repository status
git status

# Create a feature branch
git switch -c feature/update-readme

# Stage changes
git add README.md

# Commit changes
git commit -m "docs: update README"

# Push the feature branch
git push -u origin feature/update-readme
```

After pushing, open a Pull Request on GitHub to propose the changes for review.

---

## Repository Purpose

This repository serves as a personal learning space for understanding Git and GitHub fundamentals through hands-on practice. It will be updated with notes, command examples, exercises, and practical workflows as new concepts are learned.

**Learning by doing — one Git command at a time.**
