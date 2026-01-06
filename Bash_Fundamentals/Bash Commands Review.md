# Bash Commands Review

This document serves as a comprehensive review of Bash commands, terminal basics, shortcuts, and command options. It is intended to be used as structured notes for revision and as a reference for anyone learning or revising command line fundamentals.

---

## Terminal, Shell, and Command Line Basics

### Command Line

A **command line** is a text-based interface where users type commands to interact with the operating system.

### Terminal

A **terminal** is an application that provides access to the command line.

### Terminal Emulator

A **terminal emulator** enhances the terminal experience by adding features such as tabs, themes, split panes, and shortcuts.

### Shell

A **shell** interprets the commands entered into the terminal and executes them. One of the most common shells is **Bash (Bourne Again Shell)**.

### Command Line Options by Operating System

* **Windows**: PowerShell, Command Prompt, Microsoft Terminal
* **macOS**: Built-in Terminal, iTerm, Ghostty
* **Linux**: Default terminals vary by distribution, with popular third‑party emulators like kitty

> Although the terms *terminal*, *shell*, and *command line* are often used interchangeably, they represent different components of the system.

---

## Command Line Shortcuts

Shortcuts help improve efficiency and speed while working in the terminal.

* **Up Arrow**: Cycle backward through previously executed commands
* **Down Arrow**: Cycle forward through command history
* **Tab**: Autocomplete commands and file names
* **Control + L** (Linux/macOS): Clear the terminal screen
* **cls** (Windows): Clear the terminal screen
* **Control + C**: Interrupt or stop a running command

  * In PowerShell, this also acts as a copy command if text is selected
* **Control + Z** (Linux/macOS only): Suspend the current process and move it to the background

  * Use `fg` to resume the process
* **!!**: Instantly re‑run the last executed command

---

## Bash Basics

### Bash

**Bash (Bourne Again Shell)** is one of the most widely used shells in Unix‑like operating systems.

### Common Bash Commands

#### Directory Navigation

* `pwd` – Prints the current working directory
* `cd` – Changes the current directory

  * `..` refers to the parent directory
  * `.` refers to the current directory

#### Listing Files and Folders

* `ls` – Lists files and directories

  * `-a` – Shows all files, including hidden files
  * `-l` – Displays detailed file information

#### Viewing File Contents

* `less` – View file contents page by page with navigation and search support
* `more` – Display file contents one screen at a time with limited navigation
* `cat` – Output the entire file content at once (best for small files)

#### File and Directory Management

* `mkdir` – Create a new directory
* `rmdir` – Remove an empty directory
* `touch` – Create a new file

#### Moving and Renaming

* `mv oldname.txt newname.txt` – Rename a file
* `mv filename.txt /path/to/target/` – Move a file to another directory

#### Copying

* `cp file target` – Copy a file
* `cp -r directory target` – Recursively copy a directory

#### Deleting

* `rm file` – Delete a file
* `rm -r directory` – Recursively delete a directory and its contents

#### Output and Redirection

* `echo "text"` – Display text in the terminal
* `>` – Overwrite file content
* `>>` – Append content to a file without overwriting

#### Other Useful Commands

* `find` – Search for files and directories

  * `-name` – Search by file name pattern (e.g., `find . -name "*.txt"`)
* `man command` – View the manual page for a command
* `clear` – Clear the terminal screen
* `exit` – Exit the terminal session

---

## Command Options and Flags

Options or flags modify how a command behaves. They are typically prefixed with hyphens.

### Long Form Options

* Use **two hyphens (--)**
* Examples:

  * `--help`
  * `--version`
* Values are attached using an equals sign:

  * `--width=50`

### Short Form Options

* Use **one hyphen (-)**
* Examples:

  * `-a`
  * `-l`
* Values are passed with a space:

  * `-w 50`
* Multiple short options can be chained together:

  * `ls -alh`

### Help Flag

* `--help` can be used with most commands to understand available options and syntax

---

## Assignment

* Review all Bash command topics and concepts covered in this document.
* Practice commands directly in the terminal to build confidence.
* Use this file as a reference while working on Bash‑based projects or lessons.

---

**End of Bash Commands Review**
