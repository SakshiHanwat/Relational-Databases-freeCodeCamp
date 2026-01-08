# 🔀 What Is a Pull Request, and How Do You Create One?

## 📌 Introduction

In earlier lessons, you created a **feature branch**, committed changes, and pushed them to GitHub. The next important step is creating a **Pull Request (PR)**.

A pull request is the standard way to propose changes in GitHub, especially when contributing to **open‑source projects** or collaborating in a team.

---

## ❓ What Is a Pull Request?

A **pull request** is a request to **pull changes from one branch into another branch**.

Most commonly:

* Source branch (feature branch) ➜ Target branch (`main`)

Pull requests allow:

* Code review by maintainers
* Discussion through comments
* Suggestions and improvements
* Safe merging of changes

---

## 🌐 When Do You Use Pull Requests?

* Contributing to open‑source projects
* Working in a team
* Reviewing code before merging
* Keeping `main` branch clean and stable

---

## 🧭 Creating a Pull Request on GitHub (Step‑by‑Step)

### 1️⃣ Go to Your Repository on GitHub

After pushing a new branch, GitHub may show a banner suggesting to create a PR. For learning purposes, we will **ignore the banner**.

### 2️⃣ Open Pull Requests Tab

* Click on **Pull Requests** tab
* Click **New Pull Request**

---

## 🔁 Understanding Base and Compare

* **Base branch** → Where changes will be merged (usually `main`)
* **Compare (Head) branch** → Branch containing your changes (e.g. `feature`)

➡️ Set:

* Base: `main`
* Compare: `feature`

GitHub will now show:

* Commits not yet in `main`
* A **diff view** (visual changes)

---

## 🧾 What Is a Diff?

A **diff** shows:

* Added lines
* Deleted lines
* Modified lines

This helps reviewers understand exactly what changed. With practice, reading diffs becomes easy.

---

## 🔀 Compare Across Forks (Important Note)

* Used when contributing from a **fork**
* Allows targeting the **original repository**

⚠️ Do **not** create pull requests with only practice changes in real projects.

---

## ✍️ Filling Pull Request Details

### 🔹 Title

* Auto‑generated from commit message or branch name
* Follow project contribution guidelines

### 🔹 Description

* Often pre‑filled using a PR template
* Explain **what** and **why** of changes

Always read the project’s **CONTRIBUTING.md** file.

---

## 👥 Extra Options (Repo Owner Only)

If it’s your own repository, you can:

* Add reviewers
* Assign users
* Add labels
* Set milestones and projects

In other people’s repos, you usually can only **request a review**.

---

## ✅ Creating the Pull Request

Once everything looks good:

* Click **Create Pull Request**

🎉 Your pull request is now live!

---

## 🔍 Code Review Process

For open‑source projects:

* Maintainers review your code
* They may request changes
* Once approved → PR is merged

For your own repo:

* You can directly merge after reviewing

---

## 🔄 After Merging the Pull Request

### 1️⃣ Switch to Main Branch

```bash
git checkout main
```

### 2️⃣ Pull Latest Changes

```bash
git pull
```

### 3️⃣ View Commit History

```bash
git log
```

You’ll see:

* Your commit
* A **Merge pull request #X** commit

---

## 🔧 Merge Strategies in GitHub

### 1️⃣ Merge (Default)

* Keeps all commits
* Adds a merge commit

### 2️⃣ Squash and Merge

* Combines all commits into one
* Clean commit history

### 3️⃣ Rebase and Merge

* Replays commits on top of base branch
* No merge commit

⚠️ Rebasing is advanced and covered later.

---

## ⚠️ Best Practice

✅ Always create a **new branch** for changes
❌ Never commit directly to `main`

This avoids conflicts and messy histories.

---

## 🧠 Knowledge Check (Answers)

### ✔ What is a pull request?

➡️ A request to pull changes from one branch into another.

### ✔ What do base and compare mean?

➡️ Base = target branch, Compare = source branch.

### ✔ Which is NOT a merge strategy?

➡️ Fork and Merge ❌

---

## 🎯 Conclusion

You have successfully learned:

* What a pull request is
* How to create one
* How merging works
* Why branches are important

🚀 You are now ready to contribute professionally on GitHub!

---

## 👩‍💻 Author

**Sakshi Mishra**
Git & GitHub Learning Notes
