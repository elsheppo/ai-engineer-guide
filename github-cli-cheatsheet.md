# GitHub CLI Cheatsheet

Everyone is becoming an AI engineer these days – some of us are just doing it more quickly than others. 

If you’ve arrived in the AI space without a traditional engineering background (like me!), then using Github is likely a new skill for you. TL;DR, Github is essential for development projects, and even if you’re not an expert there are a few things you should know.

Github is basically where most of the engineering world manages their software projects. It’s how we do version control of our projects (v1, v2, v3, etc), work on one new feature at a time without worrying about breaking our whole app, collaborate with others, etc. 

Basically, if you are coding (even without AI) you will end up using Github.

You’ll generally be developing on your own computer, and once you get your software to a “good place” - e.g. it’s working without any bugs - you’ll want to “push it” to Github.

The easiest way to do this from your computer is to use Github CLI (Command Line Interface). 

A CLI is like what you see hackers using in every famous movie – a stripped down black interface with just text where they’re typing away, smashing the enter button, and watching a progress tracker race to 100% before the target comes back to their computer!

On Mac the native CLI app is called Terminal, and on Windows it’s Windows Terminal. Go figure.

I know it’s tempting to let AI handle EVERYTHING for us when we’re coding, but there are still many times where we need to manually push a change, make a tweak, etc. because it’s easier than having AI do it for us.

While tools like Github MCP are an easy mode option, I do believe you need to know the basics in order to approve the commands/requests your AI agent sends you if its making changes to your codebase.

Personally, I’m always asking my AI assistant to remind me of common Github CLI commands.

So I put together a list of the most common commands most developers use and included a little note on the use case.

I know we can all ask AI for this, but in case you’re the type of person who wants to see it all in one place or have a cheatsheet for yourself, here you go.

You can download this as a markdown file via Github here and add it to your Obsidian vault, or just bookmark this page and come back when you need it.

## Basic Setup

### Configure Git (First Time Setup)
```sh
# Set your name and email (required for commits)
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```
*This sets your identity for commits. It is required before making any commits.*

### Authenticate GitHub CLI
```sh
gh auth login
```
*Logs you into GitHub through the CLI. Follow the prompts to authenticate.*

---

## Working with Repositories

### Clone an Existing Repository
```sh
git clone <repository-url>
```
*Copies an existing repository from GitHub to your local machine.*

### Create a New Repository (GitHub CLI)
```sh
gh repo create <repo-name> --public
```
*Creates a new repository on GitHub and makes it public. Use `--private` for private repos.*

### Link Local Directory to GitHub Repository
```sh
git init
```
*Initializes a new Git repository in your current directory.*

```sh
git remote add origin <repository-url>
```
*Links your local repository to the remote GitHub repository.*

```sh
git branch -M main
```
*Renames the default branch to `main` (optional but recommended).*

```sh
git push -u origin main
```
*Pushes your initial commit to GitHub and sets upstream tracking.*

---

## Branching

### Check Current Branch
```sh
git branch
```
*Displays the list of branches and highlights the current branch.*

### Create a New Branch
```sh
git checkout -b <new-branch-name>
```
*Creates and switches to a new branch. Useful when starting a new feature.*

### Switch to Another Branch
```sh
git checkout <branch-name>
```
*Switches to an existing branch.*

### Delete a Branch
```sh
git branch -d <branch-name>
```
*Deletes the specified branch. Use `-D` to force delete an unmerged branch.*

### Push a New Branch to GitHub
```sh
git push -u origin <branch-name>
```
*Pushes the branch to GitHub and sets upstream tracking.*

---

## Making Changes

### Check Status of Files
```sh
git status
```
*Shows which files have been modified, staged, or are untracked.*

### Add Files to Staging
```sh
git add <file-name>  # Add specific file
git add .            # Add all changes
```
*Moves files to the staging area, preparing them for commit.*

### Commit Changes
```sh
git commit -m "Your commit message"
```
*Saves your changes locally with a descriptive message.*

### Push Changes to GitHub
```sh
git push origin <branch-name>
```
*Uploads your committed changes to the specified branch on GitHub.*

---

## Pulling and Merging

### Pull Latest Changes from Remote
```sh
git pull origin <branch-name>
```
*Fetches and integrates the latest changes from GitHub into your local branch.*

### Merge Branches
```sh
git checkout <main-branch>
git merge <feature-branch>
```
*Combines changes from one branch into another. Typically used to merge features into `main`.*

---

## Handling Issues & PRs

### Create a Pull Request (GitHub CLI)
```sh
gh pr create --title "PR Title" --body "PR description"
```
*Creates a new pull request on GitHub with a title and description.*

### List Pull Requests
```sh
gh pr list
```
*Shows open pull requests for the current repository.*

### Checkout a Pull Request Locally
```sh
gh pr checkout <PR-number>
```
*Fetches and switches to the pull request branch for local testing.*

### Merge a Pull Request (GitHub CLI)
```sh
gh pr merge <PR-number> --merge
```
*Merges the specified pull request using GitHub CLI.*

---

## Undoing Changes

### Undo Last Commit (Keep Changes Staged)
```sh
git reset --soft HEAD~1
```
*Reverts the last commit but keeps the changes staged.*

### Undo Last Commit (Remove Changes)
```sh
git reset --hard HEAD~1
```
*Completely removes the last commit and discards changes.*

### Remove a File from Staging
```sh
git reset <file-name>
```
*Unstages a file but keeps its changes.*

### Revert a Pushed Commit
```sh
git revert <commit-hash>
git push origin <branch-name>
```
*Creates a new commit that undoes a previous commit, keeping history intact.*

### Reset to a Previous Commit
```sh
git reset --hard <commit-hash>
```
*Resets the repository to a specific commit, discarding all changes after it. Use with caution as this cannot be undone easily.*

```sh
git reset --soft <commit-hash>
```
*Resets to a previous commit but keeps changes staged.*

```sh
git reset --mixed <commit-hash>
```
*Resets to a previous commit but keeps changes unstaged.*

---

## Miscellaneous

### View Commit History
```sh
git log --oneline --graph --decorate --all
```
*Displays a compact commit history with branch and merge details.*

### Show Remote URLs
```sh
git remote -v
```
*Lists the remote URLs associated with your repository.*

### Stash Changes (Temporarily Save Work)
```sh
git stash
```
*Saves changes for later without committing them.*

### Apply Stashed Changes
```sh
git stash pop
```
*Restores the most recently stashed changes.*

---

This should cover most common GitHub CLI operations. Let me know if you need more details or explanations!

