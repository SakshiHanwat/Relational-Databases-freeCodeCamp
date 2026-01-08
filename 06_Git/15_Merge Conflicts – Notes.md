# What Are Merge Conflicts, and How Can You Resolve Them?

## Introduction

When working with Git, especially in teams or on multiple features at the same time, you may encounter something called a **merge conflict**. Merge conflicts are common and completely normal in real-world development. Although they may look scary at first, they can be resolved safely if you understand what is happening.

---

## What Is a Merge Conflict?

A merge conflict occurs when Git is unable to automatically merge changes from two different branches. This usually happens when:

* Two branches modify the **same file**, and
* Both branches change the **same lines of code** in that file

For example, you might be working on a feature branch while your teammate is working on another branch. If your teammate merges their branch into `main` first, your branch becomes outdated. When you try to merge later, Git may not know which version of the code should be kept.

In such cases, Git stops the merge process and asks you to manually resolve the conflict.

---

## Why Merge Conflicts Happen

Merge conflicts usually happen because:

* Multiple developers edit the same file
* The same section of code is changed differently
* One branch is merged into main before another

Most of the time, this can be solved by merging the latest `main` branch into your feature branch. But if Git finds conflicting changes, it cannot decide automatically which changes are correct.

---

## Merge Conflict Markers

When a conflict occurs, Git adds special **merge conflict markers** inside the file to show the conflicting sections. These markers look like this:

```
<<<<<<< feat/conflict
Here's some code from my first PR :)
=======
Here's some code that was merged to main that conflicts with the code on my PR
>>>>>>> main
```

### Meaning of the Markers

* `<<<<<<< feat/conflict` → Start of changes from your current branch
* `=======` → Separator between the two versions
* `>>>>>>> main` → End of changes from the main branch

These markers help you clearly see which code belongs to which branch.

---

## How to Resolve Merge Conflicts on GitHub (Web UI)

For small and simple conflicts, GitHub provides a **Resolve conflicts** button directly in the Pull Request.

Steps:

1. Click **Resolve conflicts** in the PR
2. Edit the file and decide which code to keep
3. Remove the conflict markers
4. Click **Mark as resolved**
5. Click **Commit merge**

After this, GitHub creates a merge commit and the conflict is resolved.

---

## Ways to Resolve a Conflict

You can resolve conflicts in different ways:

* Keep both changes (remove only the conflict markers)
* Keep changes from only one branch
* Remove all conflicting changes if none are needed

Example after keeping only your branch’s change:

```
Here's some code from my first PR :)
```

---

## Resolving Merge Conflicts Locally (Using CLI)

If conflicts are complex or cannot be resolved on GitHub, you can fix them locally.

### Steps:

```
git checkout feat/conflict
git fetch origin
git merge origin/main
```

Git will tell you which files have conflicts. Open those files in your editor, resolve conflicts manually, then run:

```
git add .
git commit -m "chore: resolve conflicts"
```

This completes the merge locally.

---

## Rebasing to Handle Conflicts

Rebasing is another way to deal with conflicts. Instead of creating a merge commit, rebase **reapplies your commits on top of the latest main branch**.

This helps keep a cleaner commit history.

### Example: Creating a Rebase Branch

```
git checkout main
git pull
git checkout -b feat/rebase
```

Create multiple commits, then make a conflicting change on main. After that:

```
git checkout feat/
```
