# 🛠️ Build a Website Boilerplate Using Bash Commands

This repository documents the complete step-by-step process of building a **website boilerplate** using basic **Linux/Bash commands**, as practiced in a workshop-style environment (inspired by freeCodeCamp Bash lessons).

The goal of this project is to demonstrate:

* Practical command-line usage
* File & folder structure creation
* Real-world workflow using Bash
* Understanding of commands like `ls`, `cd`, `touch`, `mkdir`, `cp`, `mv`, `rm`, `find`, and `echo`

---

## 📂 Initial Navigation & Exploration

Commands used to understand the current working directory and contents:

* `pwd` – Print current directory path
* `ls` – List files and folders
* `cd <folder_name>` – Move between directories
* `cd ..` – Go back one level
* `cd .` – Stay in the same directory

These commands help in navigating and understanding the directory hierarchy.

---

## 📄 Viewing File Contents

To read files directly from the terminal:

* `more <file_name>` – Display file content page by page

Used to inspect files like:

* `package.json`
* `README.md`
* `LICENSE-MIT`
* `index.js`

---

## 🧹 Terminal Management

* `clear` – Clears the terminal screen

Used frequently to keep the workspace clean.

---

## 🏗️ Creating Project Structure

### Creating folders

* `mkdir website`
* `mkdir images`
* `mkdir fonts`
* `mkdir client`
* `mkdir client/src`
* `mkdir client/assets`
* `mkdir client/assets/images`
* `mkdir client/assets/icons`
* `mkdir client/assets/fonts`

This forms a clean and scalable project structure.

---

## 📝 Creating Files

Files were created using:

* `touch index.html`
* `touch styles.css`
* `touch index.js`
* `touch .gitignore`
* `touch package.json`
* `touch server.js`
* `touch README.md`

Assets created include:

* Images (`.jpg`, `.png`, `.jpeg`, `.svg`)
* Fonts (`.woff`, `.ttf`, `.otf`)

---

## 📋 Listing Files with Options

Different variations of `ls` were explored:

* `ls -1` – One file per line
* `ls -l` – Long listing format
* `ls --all` – Show hidden files
* `ls --help` – View help documentation

This helps understand file metadata and hidden files.

---

## 📁 Copying & Moving Files

### Copying

* `cp <file> <destination>`
* `cp -r <folder> <destination>` – Copy directories recursively

### Moving / Renaming

* `mv old_name new_name`
* `mv <file> <folder>`

Used to organize:

* Images into `assets/images`
* Fonts into `assets/fonts`
* Icons into `assets/icons`

---

## ❌ Removing Files & Folders

* `rm <file>` – Remove files
* `rm -r <folder>` – Remove folders recursively
* `rmdir <folder>` – Remove empty folders

Help command explored:

* `rm --help`

---

## 🔍 Searching Files with `find`

The `find` command was heavily used to locate files and folders:

* `find` – List everything
* `find . -name <file>` – Search by name
* `find --help` – Help documentation

Examples:

* `find -name index.html`
* `find -name images`
* `find -name header.png`

---

## ✏️ Writing to Files Using `echo`

Text was added to `README.md` directly from the terminal:

```bash
echo I made this boilerplate >> README.md
echo from the command line >> README.md
echo for the freeCodeCamp bash lessons >> README.md
```

This demonstrates output redirection using `>>`.

---

## 🔁 Project Duplication

* `mv website website-boilerplate`
* `cp -r website-boilerplate toms-website`

This simulates reusing a boilerplate for multiple projects.

---

## 🧪 Final Commands

* `echo Yay!`
* `echo I finished the boilerplate!`
* `echo goodbye terminal`
* `exit`

---

## ✅ Outcome

By the end of this project:

* A complete **website boilerplate** was built
* Proper folder structure was created
* Core Bash commands were practiced hands-on
* The workflow mirrors real-world frontend setup

This repository serves as **documentation + proof of learning** for Bash fundamentals and command-line confidence.

---

✨ Inspired by freeCodeCamp Bash lessons
