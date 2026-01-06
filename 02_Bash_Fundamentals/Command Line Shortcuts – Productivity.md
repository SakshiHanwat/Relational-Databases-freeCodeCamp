# Command Line Shortcuts to Improve Productivity

## Introduction

Using the terminal and command line efficiently can significantly improve your productivity as a developer. Most operating systems provide keyboard shortcuts that help you navigate command history, auto-complete commands, manage running processes, and keep your workspace clean.

Linux and macOS are Unix-based systems, so many shortcuts are shared between them. Windows, especially PowerShell, supports several similar shortcuts but also has some differences.

This document covers essential and commonly used command line shortcuts that every beginner should know to work faster and more effectively.

---

## Command History Navigation

### Up Arrow Key (↑)

* Cycles backward through previously executed commands.
* Useful when you want to re-run or slightly modify a command you used earlier.

### Down Arrow Key (↓)

* Cycles forward through your command history.
* Helps you move ahead after using the up arrow.

These shortcuts save time by avoiding the need to retype long commands.

---

## Auto-Completion Using the Tab Key

Most command line shells provide an auto-completion feature.

* Pressing the Tab key completes commands, file names, or directory paths.
* Suggestions depend on the shell you are using.

Examples:

* In zsh, suggestions are influenced by your recent command history.
* In PowerShell, suggestions are based on available commands, variables, and arguments.

Auto-completion reduces typing effort and minimizes errors.

---

## Clearing the Terminal Screen

Sometimes commands produce a lot of output, which can clutter the terminal.

### Linux and macOS (*nix systems)

* Press Control + L to clear the screen and move to a clean prompt.

### Windows PowerShell

* Use the `cls` command to clear the screen.
* This command can also be bound to a keyboard shortcut like Control + L.

Clearing the screen helps you focus on the next task without distractions.

---

## Interrupting a Running Command

* Press Control + C to stop a currently running command.
* This immediately terminates the process and returns you to a new prompt.

In PowerShell:

* Control + C is also used for copying text.
* It stops a process only when no text is selected.

This shortcut is useful when a command hangs or takes too long to execute.

---

## Managing Background Processes (*nix Only)

These shortcuts are available on Linux and macOS, but not directly in PowerShell.

### Control + Z

* Suspends the current running process.
* Sends it to the background and returns control to the terminal.

### fg Command

* Brings the suspended background process back to the foreground.

This is helpful when you want to temporarily pause a task and resume it later.

---

## Re-running the Last Command

* Typing `!!` and pressing Enter will re-run the last executed command.
* This is faster than scrolling through command history.

This shortcut is especially useful when you need to repeat a command multiple times.

---

## Conclusion

Command line shortcuts can dramatically improve your workflow and efficiency. While different shells and operating systems may offer additional shortcuts, the ones covered here are widely supported and form a strong foundation.

Exploring the documentation for your specific terminal and shell can help you discover even more productivity-enhancing features.
