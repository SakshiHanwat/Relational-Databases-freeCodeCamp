# What Is Bash, and What Are Some Basic Commands?

## Introduction

Bash stands for **Bourne Again SHell**. It is one of the most commonly used shells in Unix-like operating systems such as Linux and macOS. Because Bash is so widely used, learning its basic commands is extremely helpful for navigating systems, managing files, and performing everyday development tasks.

This document introduces Bash and explains several essential commands that beginners should know to work confidently in a terminal.

---

## pwd – Print Working Directory

The `pwd` command prints the **current working directory** to the terminal.

The working directory is the folder where the terminal is currently focused. Many other commands depend on knowing your current directory, so this command is often used to confirm your location.

---

## cd – Change Directory

Sometimes the terminal is pointed to the wrong directory. The `cd` command allows you to move between directories.

You can:

* Use an **absolute path**, which starts with a forward slash (`/`).
* Use a **relative path**, which does not start with a slash and is relative to the current directory.
* Use `..` (double-dot) to move up to the parent directory.

Changing directories correctly is essential for accessing files and folders.

---

## ls – List Directory Contents

The `ls` command lists the files and folders inside the current working directory.

This helps you check whether a file or directory exists.

Common flags include:

* `-a` to show hidden files
* `-l` to display detailed information such as permissions

You can also use commands like `cat` or `less` to view the contents of files.

---

## Creating Files and Directories

If a required file or folder does not exist, you can create it using the following commands:

### mkdir

* Creates a new directory (folder).

### touch

* Creates a new file.

Example:

* `touch readme.md` creates a new Markdown file named `readme.md`.

---

## mv – Move or Rename Files

The `mv` command is used to move or rename files.

It takes two arguments:

1. The old file name
2. The new file name

This command can rename files or move them to a different directory.

---

## rm – Remove Files or Directories

The `rm` command deletes files.

* Using the `-r` flag allows you to delete directories.
* Using the `-f` flag forces deletion, even for protected files.

This command should be used carefully because deleted files are not easily recoverable.

---

## cp – Copy Files or Directories

The `cp` command copies files or directories to a new location.

* The original file remains unchanged.
* To copy a directory, the `-r` flag is required.

---

## echo – Print Output to the Terminal

The `echo` command prints text to the terminal.

It works similarly to `console.log()` or `print()` in programming languages.

You can combine `echo` with control symbols:

* `>` creates or overwrites a file
* `>>` appends text to a file

Example:

* `echo "Naomi was here." > readme.md`

---

## man – Command Manual

There are many more Bash commands such as `head`, `tail`, `chown`, and `chmod`.

Because it is impossible to remember all commands, Bash provides the `man` command.

* `man command-name` opens the manual page for that command.

This is one of the most useful tools for learning Bash.

---

## Conclusion

You will naturally remember the commands you use most often. For less common commands, the manual pages are always available.

By understanding these basic Bash commands, you build a strong foundation for working efficiently in Unix-like environments.
