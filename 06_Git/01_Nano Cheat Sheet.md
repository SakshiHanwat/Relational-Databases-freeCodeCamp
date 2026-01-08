# Nano Text Editor Cheat Sheet

## 1. Overview

* **Nano**: Terminal-based text editor for Linux.
* **Goal**: Simple and user-friendly, ideal for quick file editing.
* **Comparison**:

  * **Vim**: powerful, steep learning curve.
  * **Emacs**: feature-rich, many shortcuts.
  * **Nano**: easy, on-screen help, minimal setup.

## 2. Starting Nano

```bash
nano <filename>
```

* Opens the specified file or creates it if it doesn't exist.
* Interface shows:

  * Top: Nano version & file name
  * Middle: File content
  * Bottom: Keyboard shortcuts

## 3. Basic Navigation

* **Arrow keys**: move cursor
* **Page Up / Page Down**: scroll by page
* **Ctrl + A**: move to start of line
* **Ctrl + E**: move to end of line

## 4. Editing Text

* Type normally to insert text.
* **Backspace / Delete**: remove characters
* **Ctrl + K**: cut current line
* **Ctrl + U**: paste cut line
* **Ctrl + J**: justify paragraph

## 5. Saving & Exiting

* **Ctrl + O**: Save (Write Out)

  * Confirm file name, press Enter
* **Ctrl + X**: Exit Nano

  * If unsaved changes, Nano asks:

    * **Y**: Save
    * **N**: Discard
    * **Ctrl + C**: Cancel exit

## 6. Searching & Replacing

* **Ctrl + W**: Search (Where Is)
* **Ctrl + **: Replace
* **Ctrl + T**: Execute external command

## 7. Special Key Notation

| Symbol | Meaning               |
| ------ | --------------------- |
| `^`    | Hold Ctrl + key       |
| `M-`   | Hold Meta (Alt) + key |

## 8. Common Shortcuts

| Action     | Shortcut      |
| ---------- | ------------- |
| Help       | Ctrl + G (^G) |
| Save       | Ctrl + O (^O) |
| Exit       | Ctrl + X (^X) |
| Cut line   | Ctrl + K (^K) |
| Paste line | Ctrl + U (^U) |
| Search     | Ctrl + W (^W) |
| Replace    | Ctrl + \ (^\) |
| Justify    | Ctrl + J (^J) |

## 9. Tips

* Ideal for remote servers without GUI.
* Minimalistic; cannot be extended with plugins.
* Focus on editing quickly and efficiently.
* On-screen shortcuts make learning intuitive.
