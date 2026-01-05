# How to Create a Project and Run Your Code Locally in VS Code

## Introduction

When working in Visual Studio Code (VS Code), projects are handled using something called a **workspace**. This guide explains, step by step, how to create a new project, add files, and run your code locally using VS Code in simple English. These notes are ideal for beginners and revision.

---

## What Is a Workspace in VS Code?

In VS Code, a **workspace** is simply the **directory (folder)** that you open in the editor. Any files and folders inside that directory become part of your project.

---

## Creating a New Project Using the Command Line

To create a new project, you first need to create a new directory (folder). For this, we use a **Command Line Interface (CLI)**.

A **CLI (Command Line Interface)** allows you to interact with your operating system using text-based commands instead of clicking buttons.

### Open the Command Line

* On **Windows**: Use **Command Prompt** or **PowerShell**.
* On **macOS**: Open the **Terminal** app.

### Steps to Create a Project Folder

1. Navigate to the home directory by typing:

```
cd ~
```

2. Create a new directory by typing:

```
mkdir my-project
```

Here, `mkdir` means **make directory**.

3. Open this new directory in VS Code.

---

## Other Ways to Open a Project in VS Code

There are also graphical ways to create and open a project:

* Right-click on a folder and choose **Open with VS Code** (if available).
* Open VS Code first, then open a folder from the File menu.
* Use the command line and type:

```
code /path/to/folder
```

Once opened, you will see a **blank workspace**.

---

## Creating Your First File

1. Click on the **File** menu in the top-left corner.
2. Select **New File**.
3. Name the file `index.html`.
4. Click **Save**.

The file will now appear in the Explorer tab. You can add basic HTML code inside this file.

---

## Running HTML Code the Right Way

You might think of opening the HTML file directly in the browser. While this may work sometimes, it can cause **unexpected bugs**, such as:

* CSS files not loading properly
* JavaScript issues

To avoid these problems, it is recommended to use a **proper web server**.

---

## Using Live Server Extension

VS Code provides an easy way to run a local web server using the **Live Server** extension.

### Installing Live Server

1. Click on the **Extensions** tab on the left side.
2. Search for **Live Server**.
3. Install the extension (it is free).

### Running Live Server

* Open your `index.html` file.
* Click the **Go Live** button in the status bar.

Your webpage will open automatically in the browser. If it does not open, you can manually visit:

```
http://localhost:5500/
```

---

## Conclusion

You have now:

* Created a project folder
* Opened it as a workspace in VS Code
* Added an HTML file
* Run your project using Live Server

This setup allows you to see live changes while coding and helps avoid common browser-related issues.

---

## Summary

* Workspace = the folder opened in VS Code
* CLI is used to create and manage directories
* `mkdir` creates a new folder
* Live Server helps run HTML files properly
* `http://localhost:5500/` shows your running project

You are now ready to build and run projects locally in VS Code.
