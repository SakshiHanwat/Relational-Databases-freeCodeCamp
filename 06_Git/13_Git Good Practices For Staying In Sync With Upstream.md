# Good Practices for Remaining in Sync with Remote Repositories

## Introduction

When working with Git, especially in **forked repositories**, it is very important to follow proper practices to stay in sync with the original (upstream) repository. These practices help avoid problems like conflicting changes, broken histories, and difficult merges. This document explains why you should avoid committing directly to the `main` branch, how to correctly sync your local repository with the upstream repository, and what to do if things go wrong.

---

## Why You Should Not Commit Directly to the Main Branch

The `main` branch should always represent a **clean and stable version** of the project that matches the upstream repository. If you directly commit changes to your local `main` branch and the upstream repository also accepts new changes from other contributors, your local history and the upstream history will no longer match.

This situation is called a **divergent history**. A divergent history makes it very hard to pull or merge changes from upstream and can create conflicts that are difficult to resolve. Because of this, best practice is to **create a new branch** for your work and keep the `main` branch only for syncing with upstream.

---

## Forking and Setting Up an Upstream Remote

To follow proper workflow, you should:

1. Fork the original repository on GitHub.
2. Clone your forked repository to your local machine.
3. Add a remote called `upstream` that points to the original repository.

Use the following command to add the upstream remote:

```
git remote add upstream <url>
```

Here, `<url>` should be the **SSH URL of the original repository**, not your fork.

This setup allows you to pull updates from the original project while keeping your own fork separate.

---

## Correct Way to Sync Your Local Main Branch with Upstream

Once your upstream remote is properly configured, you can sync your local `main` branch with the original repository using these commands:

```
git checkout main
git fetch upstream
git merge upstream/main
```

### What These Commands Do

* `git checkout main` ensures that you are currently on your local `main` branch.
* `git fetch upstream` downloads the latest changes from the upstream repository **without modifying** your local branches.
* `git merge upstream/main` merges the upstream `main` branch changes into your local `main` branch.

This method is safer than using `git pull` because your local `main` branch tracks your fork (`origin`), not the original repository (`upstream`).

---

## Handling Merge Failures and Divergent History

If you accidentally committed changes directly to your `main` branch and Git cannot merge the upstream changes, you may need to **force reset** your local branch. This is only safe if you have **not created any pull requests from your main branch**.

Use the following command:

```
git reset --hard upstream/main
```

### Explanation

* `git reset` resets the current branch state.
* `--hard` forces both commit history and local files to exactly match the target branch.
* `upstream/main` means your local `main` branch will become identical to the upstream `main` branch.

⚠️ **Warning:** This command deletes local changes permanently. Use it carefully.

---

## Pushing Synced Changes to Your Fork

After successfully syncing your local `main` branch, you should push the changes to your remote fork (`origin`):

```
git push
```

If your fork also has a divergent history and the push fails, you may need to force push:

```
git push --force
```

⚠️ **Warning:** Force pushing rewrites remote history and can cause serious issues if used incorrectly.

Pushing updated changes ensures that your fork always contains the latest version of the original project and can be safely cloned again if needed.

---

## Starting New Work After Syncing

Once your `main` branch is clean and synced with upstream, you can safely create a new branch from it and start working on your next contribution using the latest codebase.

---

## Concept Check: Questions and Answers

### Q1. Why should you avoid committing directly to the main branch?

**Correct Answer:** It causes a *divergent history* making it difficult to sync with upstream.

### Q2. Which commands correctly update your local main branch from upstream?

**Correct Answer:**

```
git checkout main
git fetch upstream
git merge upstream/main
```

### Q3. Which command forcibly resets your main branch to match upstream?

**Correct Answer:**

```
git reset --hard upstream/main
```

---

## Conclusion

Following these Git best practices ensures smooth collaboration, clean history, and easier syncing with the original repository. Keeping your `main` branch clean and using feature branches for development is the key to professional and conflict-free Git workflows.
