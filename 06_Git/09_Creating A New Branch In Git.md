# 🌿 Creating a New Branch in Git

## 📌 Overview

When working with Git, making all changes directly on the `main` branch may work for very small projects. However, as projects grow or when contributing to open-source repositories, **branches become essential**.

Branches allow you to work on new features or bug fixes **without affecting the main branch**, keeping your project stable and organized.

---

## 🚦 Why Branches Are Important

* Helps separate features and bug fixes
* Prevents unstable code from entering `main`
* Makes collaboration easier in teams
* Simplifies contributing to open-source projects
* Allows easy switching between tasks

---

## 🛣️ Understanding Branches (Simple Analogy)

Think of the `main` branch as a **highway**:

* Each commit is a car on the highway
* A branch is like taking an **exit** to explore something new
* If the work is good, you merge back onto the highway
* If not, you can safely discard the branch

---

## 🔍 Viewing Existing Branches

To see all branches in your repository:

```bash
git branch
```

Example output:

```text
* main
```

➡️ The `*` symbol shows the branch you are currently on (checked out).

---

## 🌱 Creating a New Branch

To create a new branch named `feature`:

```bash
git branch feature
```

Check branches again:

```bash
git branch
```

Output:

```text
  feature
* main
```

➡️ The branch is created, but you are still on `main`.

---

## 🔄 Switching to a Branch (Checkout)

To switch to the new branch:

```bash
git checkout feature
```

OR (modern command):

```bash
git switch feature
```

Now check branches:

```text
* feature
  main
```

---

## ⚡ Create and Switch in One Command

Instead of two steps, you can create and switch at once:

```bash
git checkout -b feature
```

OR

```bash
git switch -c feature
```

---

## ✍️ Working on the New Branch

Check branch status:

```bash
git status
```

Create a new file:

```bash
echo "This is our new feature" > feature.md
```

Check status again:

```text
On branch feature
Untracked files:
  feature.md
```

---

## 📦 Staging and Committing Changes

Stage the file:

```bash
git add feature.md
```

Commit the changes:

```bash
git commit -m "my new feature"
```

---

## 🚀 Pushing the Branch to GitHub

Push the feature branch:

```bash
git push -u origin feature
```

➡️ The `-u` flag sets upstream tracking so future pushes only need:

```bash
git push
```

---

## ❓ Knowledge Check

### 1️⃣ What does creating a new branch allow you to do?

✅ Make changes without affecting the main branch.

### 2️⃣ What does `*` mean in `git branch` output?

✅ The branch is currently checked out.

### 3️⃣ What does `git push -u origin feature` do?

✅ Pushes the branch and sets it to track the remote branch.

---

## 📚 What’s Next?

➡️ Learn how to:

* Create Pull Requests (PRs)
* Merge branches
* Resolve merge conflicts

---

## 👩‍💻 Author

**Sakshi Hanwat**
Learning Git, GitHub & Open-Source Collaboration 🚀
