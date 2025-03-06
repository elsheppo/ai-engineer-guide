# GitHub CLI Cheatsheet

## Introduction

Everyone is becoming an AI engineer these days – some of us are just doing it more quickly than others. 

If you've arrived in the AI space without a traditional engineering background, then using GitHub is likely a new skill for you. GitHub is essential for development projects, and even if you're not an expert, there are a few things you should know.

GitHub is where most of the engineering world manages their software projects. It's how we do version control (v1, v2, v3, etc.), work on one feature at a time without breaking the whole app, collaborate with others, and more.

**TL;DR:** If you are coding (even without AI), you will end up using GitHub.

---

## Why Use GitHub CLI?

You'll generally develop on your own computer, and once your software reaches a good place (working without bugs), you'll want to "push it" to GitHub.

The easiest way to do this is with **GitHub CLI** (Command Line Interface):
- It's what you see hackers using in movies – a black interface with text
- On Mac, the native CLI app is called Terminal
- On Windows, it's Windows Terminal

While tools like GitHub MCP offer an easier option, knowing the basics is essential for approving commands when AI makes changes to your codebase.

---

## Command Reference

### 🔧 Basic Setup

| Command | Description |
|---------|-------------|
| `git config --global user.name "Your Name"` | Set your name for commits |
| `git config --global user.email "your.email@example.com"` | Set your email for commits |
| `gh auth login` | Authenticate GitHub CLI (follow prompts) |

### 📁 Working with Repositories

| Command | Description |
|---------|-------------|
| `git clone <repository-url>` | Copy existing repository to your machine |
| `gh repo create <repo-name> --public` | Create new public repository (use `--private` for private) |
| `git init` | Initialize Git repository in current directory |
| `git remote add origin <repository-url>` | Link local repository to GitHub |
| `git branch -M main` | Rename default branch to `main` (recommended) |
| `git push -u origin main` | Push initial commit and set upstream tracking |

### 🌿 Branching

| Command | Description |
|---------|-------------|
| `git branch` | Show all branches (current branch highlighted) |
| `git checkout -b <new-branch-name>` | Create and switch to new branch |
| `git checkout <branch-name>` | Switch to existing branch |
| `git branch -d <branch-name>` | Delete a branch (use `-D` to force delete) |
| `git push -u origin <branch-name>` | Push branch to GitHub and set tracking |

### 📝 Making Changes

| Command | Description |
|---------|-------------|
| `git status` | Check which files have been modified |
| `git add <file-name>` | Add specific file to staging |
| `git add .` | Add all changes to staging |
| `git commit -m "Your commit message"` | Save changes locally with message |
| `git push origin <branch-name>` | Upload committed changes to GitHub |

### 🔄 Pulling and Merging

| Command | Description |
|---------|-------------|
| `git pull origin <branch-name>` | Get latest changes from GitHub |
| `git checkout <main-branch>` <br> `git merge <feature-branch>` | Merge changes from one branch to another |

### 🎫 Handling Issues & PRs

| Command | Description |
|---------|-------------|
| `gh pr create --title "PR Title" --body "PR description"` | Create a pull request |
| `gh pr list` | Show open pull requests |
| `gh pr checkout <PR-number>` | Check out PR branch locally |
| `gh pr merge <PR-number> --merge` | Merge a pull request |

### ⏪ Undoing Changes

| Command | Description |
|---------|-------------|
| `git reset --soft HEAD~1` | Undo last commit (keep changes staged) |
| `git reset --hard HEAD~1` | Undo last commit (discard changes) |
| `git reset <file-name>` | Unstage a file (keep changes) |
| `git revert <commit-hash>` <br> `git push origin <branch-name>` | Create new commit that undoes previous commit |
| `git reset --hard <commit-hash>` | Reset to specific commit (discard later changes) |
| `git reset --soft <commit-hash>` | Reset to commit (keep changes staged) |
| `git reset --mixed <commit-hash>` | Reset to commit (keep changes unstaged) |

### 🧰 Miscellaneous

| Command | Description |
|---------|-------------|
| `git log --oneline --graph --decorate --all` | View compact commit history |
| `git remote -v` | List remote URLs for repository |
| `git stash` | Temporarily save changes without committing |
| `git stash pop` | Restore most recently stashed changes |

---

## Tips for Success

1. **Commit often** - Small, frequent commits are better than large, infrequent ones
2. **Write clear commit messages** - Future you will thank present you
3. **Pull before you push** - Always get the latest changes first
4. **Create branches for features** - Don't work directly on main
5. **Double-check before hard resets** - These actions can't be easily undone

---

*You can download this as a markdown file via GitHub and add it to your Obsidian vault, or bookmark it for reference.*
