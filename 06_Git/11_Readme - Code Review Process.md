# Code Review Process for Open Source Projects

## Introduction

When working on your own repository, you usually have full control. You can create pull requests (PRs) and merge them yourself because you have maintainer access. However, when you contribute to someone else's open source project, the process is different. You normally do not have permission to merge your own pull request. Instead, project maintainers review your code and decide whether it should be accepted and merged.

This document explains what a typical code review process looks like in most open source projects. The exact steps can vary depending on the project or the maintainers, but the general flow is mostly the same.

---

## What Is Code Review?

Code review is the process where project maintainers carefully check your pull request. They verify that your changes follow the project’s rules, do not break existing functionality, and improve the project in a correct and safe way.

---

## Typical Steps in a Code Review Process

### 1. Continuous Integration (CI) Checks

The first step in most code reviews is to confirm that CI (Continuous Integration) checks pass.

CI checks are automated tests and style checks that run whenever you open or update a pull request. These checks make sure:

* The code follows style guidelines
* All tests pass successfully
* The project builds correctly

If the CI fails, maintainers will usually ask you to fix the issues. The CI system often provides reports that explain what went wrong. Maintainers may also leave comments to help you understand how to fix the problems.

---

### 2. Review of Code Changes

Once all CI checks pass, maintainers review your actual code changes.

They look at the diff view to see:

* What code was added
* What code was changed
* What code was removed

Maintainers may ask questions about your decisions or the approach you used. Because of this, it is important to write clean code and be thoughtful about your implementation.

They may also request changes if something can be improved, optimized, or corrected.

---

### 3. Local Testing by Maintainers

After reviewing the code, maintainers often pull your changes to their local machine.

They then:

* Run the application locally
* Test the new functionality
* Check for unexpected behavior or bugs

This step ensures that your changes work correctly in real usage and do not break anything.

---

## Approval and Merging

If everything looks good, a maintainer will approve your pull request. Sometimes they comment with "LGTM", which means "Looks Good To Me".

After approval, the pull request can be merged. Some projects require more than one approval before merging. For example, freeCodeCamp requires two approvals.

---

## When Changes Are Requested

If maintainers find issues, they may request changes instead of approving the pull request.

There are two common ways this happens:

### Comments

A maintainer may leave comments suggesting what should be changed. These comments often give flexibility in how you implement the fix.

### Request Changes (Blocking Review)

Maintainers may also leave an official "request changes" review. This usually blocks the pull request from being merged until the requested updates are made.

Once you make the changes, the same maintainer will review the pull request again and either approve it or request more changes.

---

## Handling Suggested Changes on GitHub

When maintainers have very specific changes in mind, they can suggest code changes directly through GitHub’s UI.

GitHub allows you to:

* Accept individual suggestions with a single click
* Or batch multiple suggestions together from the files view

Batching suggestions is useful because it lets you commit many changes at once. This avoids creating many small commits and prevents CI from running repeatedly on every single commit.

---

## Making Larger Changes

If the requested changes are large, it is better to:

* Make the changes locally
* Commit them to the same branch used for the pull request
* Push the changes to GitHub

GitHub will automatically update the existing pull request with the new commits.

---

## Important Things to Remember

* Maintainers are people, not robots. Most maintainers work on open source projects in their free time.
* Be patient and respectful. Avoid repeatedly pinging maintainers.
* Test your code locally before submitting or updating a pull request.
* Always follow the project’s contribution guidelines.

---

## Conclusion

Contributing to open source can be exciting and rewarding. By understanding the code review process, being patient, and putting in your best effort, you increase the chances of your pull request being approved smoothly. A well-prepared pull request leads to a successful and positive code review experience.
