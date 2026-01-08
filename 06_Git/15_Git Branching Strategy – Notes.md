# Best Practices for Developing a Git Branching Strategy

## Introduction

In Git, branches are used to work on different parts of a project independently. Instead of putting all changes directly into the main branch, developers create branches to keep their work isolated, clean, and organized. A good branching strategy helps teams collaborate better, reduce bugs, and keep the project stable.

---

## Why You Should Not Commit Directly to the Main Branch

The **main branch** (also called the default branch) should always be in a **stable and working condition**. At any point in time, someone should be able to pull the main branch and successfully build, run, and test the application.

If developers push partially completed features or work-in-progress (WIP) commits directly to main, the branch may break. This can cause errors, failed builds, or unstable behavior. That is why direct commits to main should be avoided.

Another important reason is that developers often work on **multiple features at the same time**. If all incomplete work is pushed to main together, it becomes very difficult to debug issues. There is no isolation between changes, and context switching between tasks becomes messy and confusing.

---

## When Should You Create a Branch?

A simple and effective rule is:

**Create a new branch for every isolated unit of work.**

This means:

* A new feature should have its own branch
* A bug fix should have its own branch
* A UI redesign should have its own branch

### Examples:

* Working on OAuth login feature → create a dedicated OAuth branch
* Fixing a bug in password authentication → create a separate bug-fix branch
* Redesigning the user profile page → create another separate branch

This keeps each change independent and easy to manage.

---

## Always Create Branches from Main

Whenever you want to create a new branch, you should first switch to the **main branch** and then create the new branch.

This is important because if you create a branch from another feature branch, your new branch will also include all the commits from that feature. This mixes unrelated changes and makes the Git history confusing and difficult to understand.

So, best practice is:

* Checkout main
* Create a new branch from main

---

## Branch Naming Conventions

There is no single mandatory way to name branches, but following a consistent convention makes projects easier to understand.

### Common Naming Patterns:

1. **scope/description**

   * Scope indicates the type of work (feat, fix, chore, etc.)
   * Description briefly explains the change
   * Example: `feat/oauth-support`

2. **scope/issue/description**

   * Includes the issue or ticket number
   * Useful when tracking work in issue trackers
   * Example: `fix/25/password-auth`

3. **username/scope/description**

   * Useful in shared repositories where everyone works on the same repo
   * Helps identify who owns the branch
   * Example: `naomi-lgbt/feat/profile-redesign`

---

## Long-Lived Feature Work

For features that take a long time to develop (for example, beta features), keeping a branch open for too long can cause problems. The longer a branch stays unmerged, the higher the chance of merge conflicts.

A better approach for long-running features is to use **feature flags**. Feature flags allow you to merge code into main while keeping the feature disabled until it is ready. This keeps branches short-lived and reduces conflicts.

---

## Deployment and Release Branches

In some projects, teams maintain **dedicated branches for deployment or releases**.

### Examples:

* Staging branch for testing
* Production branch for live users

For example, the freeCodeCamp project uses branches like:

* `prod-staging`
* `prod-current`

Instead of deploying on every merge to main, deployments are triggered by merging main into these production branches. This allows teams to move faster while keeping deployments controlled.

---

## Release Branches

Release branches represent major versions of a product (for example, v1, v2, etc.). These branches provide a clean snapshot of each major release.

They are very useful when:

* You need to apply a security patch to an older version
* You want to avoid including new features from the latest version

Release branches make maintenance easier and safer.

---

## Always Use Pull Requests to Merge

You should avoid merging branches into main directly using the local command line.

Instead, always:

* Create a **Pull Request (PR)**
* Review the changes
* Let CI tests run
* Verify the diff before merging

This process ensures code quality, prevents mistakes, and keeps the project stable.

---

## Conclusion

A good Git branching strategy keeps your codebase clean, stable, and easy to manage. By creating branches for isolated work, naming them clearly, avoiding long-lived branches, and using pull requests, you can work efficiently and collaborate successfully.

---

## Practice Questions

### Question 1

**Why should you avoid committing directly to the main branch?**

* Because the main branch should remain reliably stable at all times ✅

### Question 2

**Which is a best practice when creating a new branch?**

* Always create new branches from main ✅

### Question 3

**How should long-lived feature work be handled?**

* Use feature flags rather than long-lived branches ✅
