# How Do You Push a Local Repository to GitHub?

## Introduction

Sometimes you already have a project on your computer and want to upload it to GitHub. In this case, you do not clone a repository from GitHub first. Instead, you initialize Git in your local project and then push it to a remote GitHub repository.

---

## Step 1: Create an Empty Repository on GitHub

First, create a **new repository on GitHub** without adding any files (no README, no .gitignore, no license).

After creation, GitHub will show you the repository URL. This URL will be used later to connect your local project to GitHub.

---

## Step 2: Navigate to Your Local Project

Open your terminal and move into the existing project directory that you want to upload to GitHub. For example:

super-awesome-game

* README.md
* index.html
* script.js
* styles.css

---

## Step 3: Initialize Git in the Project

Run the following command inside the project folder:

git init

This command initializes an empty Git repository and creates a hidden **.git** directory. This directory stores all Git history and configuration.

⚠️ Deleting the .git folder will permanently remove all Git history.

---

## Step 4: Check Repository Status

Use the following command to check the current state of your project:

git status

You will see:

* Current branch (usually `main`)
* No commits yet
* Untracked files

---

## File States in Git

A file in Git can be in one of the following states:

* **Untracked**: New file not yet tracked by Git
* **Modified**: File changed after the last commit
* **Ignored**: File excluded using .gitignore
* **Deleted**: File removed after being tracked
* **Renamed**: File name or location changed

---

## Step 5: Stage Files

Before committing, files must be added to the **staging area**.

To stage a single file:

git add filename

To stage all files:

git add .

If you stage a file by mistake, you can unstage it using:

git reset filename

---

## Step 6: Commit Changes

A commit is a snapshot of your project at a point in time.

To commit with a short message:

git commit -m "your message"

Good commit messages clearly describe what changed. Some teams follow **Conventional Commits** like:

* feat(api): add authentication
* fix(auth): resolve token issue
* refactor: clean up logic

---

## Step 7: Verify Clean Working Tree

After committing, run:

git status

You should see:

nothing to commit, working tree clean

---

## Step 8: View Commit History

To see all commits in the project:

git log

This shows commit hash, author, date, and message.

---

## Step 9: Connect Local Repo to GitHub

Add the remote repository using SSH:

git remote add origin [git@github.com](mailto:git@github.com):your-username/your-repo-name.git

To verify the connection:

git remote -v

---

## Step 10: Push Code to GitHub

Push your local main branch to GitHub:

git push -u origin main

The `-u` flag sets the upstream branch so future pushes can be done using just `git push`.

---

## Pulling Changes from GitHub

To download new changes from a remote repository:

git pull

This is commonly used when collaborating with other developers.

---

## Summary

To push an existing local project to GitHub, you initialize Git, stage and commit files, connect the project to a remote repository, and push your changes. This workflow allows you to safely track history and collaborate using GitHub.
