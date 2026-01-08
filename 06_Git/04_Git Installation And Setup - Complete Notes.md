# How Do You Install and Set Up Git?

## Introduction

Before you can start using version control and platforms like GitHub or GitLab, you must first install Git on your system and configure it properly. Git needs to be available in your terminal and set up with your basic user information.

---

## Checking if Git Is Already Installed

To check whether Git is already installed on your computer, open a terminal and run:

git --version

If a version number is displayed, Git is already installed. If no version appears or the command is not recognized, then Git is not installed and you need to install it.

---

## Installing Git on Different Operating Systems

### Linux

On many Linux distributions, Git comes preinstalled. If it is not installed, you can install it using your package manager:

* For Debian/Ubuntu-based systems: sudo apt-get install git
* For Arch-based systems: sudo pacman -S git

---

### macOS

Mac users can install Git in two ways:

* Using Homebrew with the command: brew install git
* Downloading the official installer from Git’s website

---

### Windows

Windows users can install Git by:

* Downloading the executable installer from Git’s official website
* Using Chocolatey with the command: choco install git.install

On Windows, it is also recommended to install **Git Bash**, which provides a Unix-like terminal environment.

---

## Verifying the Installation

After installation, run the following command again to confirm Git is installed correctly:

git --version

---

## Configuring Git

Once Git is installed, you need to configure a few basic settings. These settings only need to be done once per system.

Git configuration is handled using the `git config` command.

---

## Viewing Current Git Configuration

To see your current Git configuration settings and where they are stored, run:

git config --list --show-origin

If Git was just installed, you will mostly see system-level settings. If Git was installed earlier, you may already see user-level settings like user name and email.

---

## Setting User Name

To set your Git user name for all projects on your system, run:

git config --global user.name "Jane Doe"

The `--global` flag means this user name will apply to all Git projects on your system. If you want a different user name for a specific project, you can run the same command inside that project without the `--global` flag.

---

## Setting User Email

To set your email address globally, run:

git config --global user.email [janedoe@example.com](mailto:janedoe@example.com)

This information is important because Git uses your name and email for every commit you make.

---

## Setting a Preferred Editor

Git uses a text editor for writing commit messages and other tasks. You can set your preferred editor using the following command:

git config --global core.editor emacs

Other editors you can use include Vim, Nano, and VS Code.

For VS Code, the configuration looks like this:

git config --global core.editor "code --wait"

If you do not set an editor, Git will use the system’s default editor.

---

### Editor Configuration on Windows

On Windows, you must provide the full path to the editor executable. Example using Notepad++:

git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"

---

## Viewing All Git Configurations

To see a simple list of all Git configuration settings, run:

git config --list

---

## Conclusion

After installing and configuring Git, your system is ready for version control. You can now start tracking changes, making commits, and collaborating on projects using Git and platforms like GitHub or GitLab.
