# What Is CI/CD and How CI Works with GitHub Actions

## Introduction

CI/CD is a modern software development practice that helps teams automatically test and deploy their applications. It ensures that new changes are checked properly before being released and reduces manual work and errors. This document explains what CI/CD is, how Continuous Integration (CI) works, and how GitHub Actions is used to implement CI pipelines.

---

## What Is CI/CD?

* **CI (Continuous Integration)** is the practice of automatically testing and validating code changes whenever developers push code or create pull requests.
* **CD (Continuous Delivery or Continuous Deployment)** focuses on automatically delivering or deploying those validated changes to an environment.

Together, CI/CD ensures that every change is functional, tested, and ready to be deployed without manual intervention.

---

## How CI Pipelines Work

In a CI pipeline, several checks are run automatically, such as:

* Code linting
* Build verification
* Running unit tests

CI pipelines usually run:

* When a pull request is created, to ensure new changes do not break the application
* On the `main` branch, to ensure it is always in a deployable state

If any step fails, the pipeline fails and alerts the developer.

---

## How CD Pipelines Work

CD pipelines often:

* Run on the `main` branch to deploy merged changes continuously
* Optionally run on pull requests to create preview environments

CD ensures that once changes are approved, they are automatically delivered or deployed.

---

## What Are GitHub Actions?

GitHub Actions is a tool provided by GitHub that allows you to automate workflows such as CI and CD. It uses **ephemeral runners**, which are temporary virtual machines that execute commands defined in workflows.

GitHub Actions workflows are configured using **YAML files**, and you can create multiple workflow files for different purposes (for example, one for CI and another for CD).

---

## Example: Basic CI Workflow Using GitHub Actions

```yaml
name: Node.js CI
on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  lint:
    name: Lint and Test
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Source Files
        uses: actions/checkout@v4

      - name: Use Node.js v22
        uses: actions/setup-node@v4
        with:
          node-version: 22

      - name: Setup pnpm
        uses: pnpm/action-setup@v2
        with:
          version: 10

      - name: Install Dependencies
        run: pnpm install

      - name: Lint Source Files
        run: pnpm run lint

      - name: Verify Build
        run: pnpm run build

      - name: Run Tests
        run: pnpm run test
```

---

## Explanation of the Workflow File

### Workflow Name and Triggers

```
name: Node.js CI
on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main
```

* `name` defines the workflow name shown in GitHub.
* `on` defines workflow triggers.
* This workflow runs when code is pushed to `main` or when a pull request targets `main`.

---

### Jobs Section

```
jobs:
  lint:
    name: Lint and Test
    runs-on: ubuntu-latest
```

* `jobs` defines the tasks the workflow performs.
* `lint` is an internal job identifier.
* `name` is the display name.
* `runs-on` specifies the environment (Ubuntu).

---

### Steps Section

Steps define what the job actually does.

#### Checkout Repository

```
uses: actions/checkout@v4
```

This action clones the repository into the runner.

#### Setup Node and pnpm

```
uses: actions/setup-node@v4
uses: pnpm/action-setup@v2
```

These steps install Node.js and pnpm. The `with` keyword passes configuration values.

#### Run Commands

```
run: pnpm install
run: pnpm run lint
run: pnpm run build
run: pnpm run test
```

These commands install dependencies, lint the code, build the project, and run tests.

---

## Important Behavior of GitHub Actions

By default, if **any step fails**, all remaining steps are skipped and the entire workflow run is marked as **failed**.

---

## Where Workflow Files Are Stored

GitHub Actions workflow YAML files must be placed inside:

```
.github/workflows/
```

GitHub automatically detects and runs workflows from this directory.

---

## Concept Check: Questions and Answers

### Q1. What does the `on` property define?

**Correct Answer:** The events that trigger the workflow to run.

### Q2. Where should workflow files be placed?

**Correct Answer:** In a `.github/workflows` directory.

### Q3. What happens if a step fails?

**Correct Answer:** Remaining steps are skipped and the run is marked as a failure.

---

## Conclusion

CI/CD with GitHub Actions helps automate testing and deployment, ensures code quality, and enables faster and safer software releases. Understanding workflow structure, triggers, jobs, and steps is essential for building reliable automation pipelines.
