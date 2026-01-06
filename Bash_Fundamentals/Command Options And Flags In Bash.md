# What Are Command Options and Flags?

## Introduction

When working with command line tools, you often pass arguments to commands. For example, in the command `touch readme.md`, the file name is an argument. In addition to arguments, commands also support **options**, commonly known as **flags**.

Options or flags are special arguments that modify how a command behaves. These two terms are often used interchangeably, but the term *flag* is commonly used for options that act like an on/off switch.

This document explains what command options and flags are, how they are written, and how they are used in both long-form and short-form syntax.

---

## What Are Options and Flags?

Options (or flags) change the default behavior of a command.

* They are usually prefixed with one or two hyphens (`-` or `--`).
* The hyphens help distinguish options from regular arguments.

For example, instead of just listing files with `ls`, you can change how the output looks by adding options.

---

## Long Form Options (`--`)

Long form options use **two hyphens** (`--`) followed by a full descriptive name.

Examples:

* `--version` prints the version of the application instead of running the command.
* `--help` displays usage instructions for the command.

Many commands support these options, making it easy to understand what the option does by reading its name.

---

## Short Form Options (`-`)

Short form options use a **single hyphen** (`-`) followed by a single letter.

Example:

* `ls -a` lists all files, including hidden files that start with a dot (`.`), such as `.env`.

Short form options are quicker to type and are commonly used for frequent tasks.

---

## Chaining Short Form Options

One major advantage of short form options is that they can be **combined (chained)** together.

For example, instead of writing:

```
ls --all --human-readable --size
```

You can write:

```
ls -ahs
```

This allows multiple behaviors to be enabled with a single, compact option string.

---

## Options That Require Values

Some options require an additional value to control their behavior.

### Long Form with Values

Long form options typically use an **equal sign (`=`)** to attach the value directly to the option.

Example:

```
ls --color=never
```

This command disables colored output.

---

### Short Form with Values

Short form options usually separate the value using a **space**.

Examples:

```
ls -w 50
ls --width=50
```

Here:

* `-w 50` is the short form
* `--width=50` is the long form

Understanding this difference is important to avoid passing values incorrectly as positional arguments.

---

## Using Help to Learn Options

If you are ever unsure about which options a command supports or how values should be passed, you can usually rely on the built-in help option.

Example:

```
ls --help
```

This displays all available options along with their expected syntax.

---

## Conclusion

Command options and flags are powerful tools that allow you to control how commands behave. By understanding the difference between long form and short form options, chaining flags, and passing values correctly, you can use command line tools more effectively and confidently.

When in doubt, the `--help` option is always a reliable reference.
