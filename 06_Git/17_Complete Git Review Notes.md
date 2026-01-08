# Git Review – Complete Notes

## Introduction to Version Control

A **version control system** is a tool that allows you to track, manage, and control changes in your project over time. It helps developers collaborate, view history, and revert changes if needed. Common version control systems include **Git**, **SVN**, and **Mercurial**.

---

## Cloud-Based Version Control Providers

Cloud-based version control providers host repositories online and enable collaboration between developers.

**Popular providers include:**

* GitHub
* GitLab

These platforms allow teams to manage repositories, review code, and collaborate efficiently.

---

## Installing and Setting Up Git

### Checking Git Installation

To check whether Git is installed, run:

```
git --version
```

If a version number appears, Git is installed.

### Installing Git on Different Operating Systems

* **Linux:** Often preinstalled. If not, use:

  * `sudo apt-get install git`
  * `sudo pacman -S git`
* **macOS:** Install via Homebrew using `brew install git` or download from Git’s website.
* **Windows:** Download the installer from Git’s website or use Chocolatey:

  * `choco install git.install`
  * Git Bash is recommended for a Unix-like shell.

---

## Git Configuration

Git configuration controls how Git behaves on your system.

To view current configurations:

```
git config --list --show-origin
```

### Setting User Information

Set your global username:

```
git config --global user.name "Jane Doe"
```

Set your global email:

```
git config --global user.email janedoe@example.com
```

### Setting a Preferred Editor

Example for Emacs:

```
git config --global core.editor emacs
```

If not set, Git uses the system default editor.

---

## Open Source vs Closed Source Software

* **Open-source:** Code is publicly visible. Anyone can view, modify, report issues, or propose changes.
* **Closed-source:** Only authorized users can view or modify the code.

---

## GitHub Overview

GitHub is a cloud-based platform that stores Git repositories and provides collaboration features.

### GitHub CLI

A command-line tool for performing GitHub-specific tasks without leaving the terminal.

### GitHub Pages

Used for deploying static websites and frontend-only applications.

### GitHub Actions

A feature that allows you to automate workflows such as building, testing, and deploying code.

---

## Common Git Commands

* `git init` – Initializes a new Git repository.
* `git status` – Shows the current state of the working directory.
* `git add` – Stages changes.
* `git commit` – Saves a snapshot of changes.
* `git log` – Shows commit history.
* `git remote add` – Adds a remote repository.
* `git push` – Pushes changes to a remote repository.
* `git pull` – Pulls changes from a remote repository.
* `git clone` – Creates a local copy of a repository.
* `git remote -v` – Lists remote repositories.
* `git branch` – Lists local branches.
* `git fetch upstream` – Fetches upstream changes.
* `git merge upstream/main` – Merges upstream main into current branch.
* `git reset` – Resets branch state.
* `git rebase` – Reapplies commits onto another base.

---

## Working with Branches

A **branch** is a separate workspace for development.

### Creating and Switching Branches

```
git branch feature
git checkout feature
```

Shortcut:

```
git checkout -b new-branch-name
```

Using switch:

```
git switch -c new-branch-name
```

### Branching Strategy

The `main` branch is usually stable. New features and bug fixes should be developed in separate branches.

### Merge Conflicts

Occur when Git cannot automatically resolve differences between branches.

---

## Five States of a Git Tracked File

* **Untracked:** New file not yet tracked by Git.
* **Modified:** File changed but not committed.
* **Ignored:** Excluded using `.gitignore`.
* **Deleted:** File removed after being tracked.
* **Renamed:** File name or location changed.

---

## .gitignore File

The `.gitignore` file tells Git to stop tracking specific files or folders.

---

## Working with Repositories

A **repository** stores project files and history.

### Public vs Private Repositories

* **Public:** Accessible by anyone.
* **Private:** Accessible only to authorized users.

### Creating Repositories on GitHub

Use the **New Repository** button and follow the setup steps.

### Pushing a Local Repository to GitHub

Steps:

1. `git init`
2. Make changes
3. `git status`
4. `git add`
5. `git commit`
6. `git remote add`
7. `git push`

---

## Pull Requests

A **pull request (PR)** is a request to merge changes from one branch into another. It allows review, discussion, and approval before merging.

---

## Contributing to Other Repositories

Basic contribution workflow:

1. Read contributing guidelines
2. Find an issue
3. Fork the repository
4. Clone your fork
5. Create a branch
6. Make changes
7. Create a pull request
8. Wait for review

---

## Working with SSH and GPG Keys

### GPG Keys

Used to sign commits and verify authenticity.

Generate a key:

```
gpg --full-generate-key
```

List keys:

```
gpg --list-secret-keys --keyid-format=long
```

Export public key:

```
gpg --armor --export "<key id>"
```

Configure Git signing:

```
git config --global user.signingkey <your_gpg_key_id>
git config --global commit.gpgsign true
```

---

### SSH Keys

Used for authentication and commit signing.

Generate SSH key:

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Configure Git to sign with SSH:

```
git config --global gpg.format ssh
git config --global user.signingkey <path_to_your_ssh_keys>
```

---

## Assignment

Review all Git topics and concepts covered in this document.
