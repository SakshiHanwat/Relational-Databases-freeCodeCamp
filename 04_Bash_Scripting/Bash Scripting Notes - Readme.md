# Bash Scripting – Notes

## What Is Bash Scripting?

Bash scripting means writing a series of Bash (Linux/Unix shell) commands inside a file and then running that file using the Bash shell. Instead of typing commands one by one in the terminal, you can automate tasks by putting them together in a script.

Bash scripting is commonly used for automation, system administration, backups, deployments, and routine maintenance tasks.

---

## Example of a Bash Script

Below is an example of a simple Bash script:

```
#!/bin/bash

servers=("prod" "dev")

for server in "${servers[@]}"
do
  echo "Pulling $server"
  rsync --archive --verbose $server:/etc/nginx/conf.d/server.conf configs/$server.conf
done
```

This script is used to pull (copy) NGINX configuration files from multiple remote servers and store them locally. This is useful for backing up configuration files into a local repository.

NGINX is a popular web server that is widely used to host websites and web applications.

---

## Explanation of the Script Line by Line

### 1. Shebang Line

```
#!/bin/bash
```

This line is called a **shebang**. It tells the operating system which interpreter should be used to execute the script. In this case, it tells the system to use Bash.

Common shebang values include:

* `/usr/bin/bash`
* `/bin/bash`
* `/bin/sh`

---

### 2. Defining an Array

```
servers=("prod" "dev")
```

This line creates an array (list) named `servers`. It contains two values:

* `prod` – production server (live environment)
* `dev` – development server (used for testing)

---

### 3. For Loop

```
for server in "${servers[@]}"
```

This line starts a `for` loop. The syntax `${servers[@]}` expands the array so that each element is accessed one by one.

During each loop iteration, the current value is stored in the variable `server`.

---

### 4. do Keyword

```
do
```

The `do` keyword marks the beginning of the loop block. All commands written after `do` will run for each value in the array.

---

### 5. Echo Command

```
echo "Pulling $server"
```

This command prints a message to the terminal. The variable `$server` is replaced with the current server name (`prod` or `dev`).

---

### 6. rsync Command

```
rsync --archive --verbose $server:/etc/nginx/conf.d/server.conf configs/$server.conf
```

This command uses `rsync` to copy the NGINX configuration file from the remote server to the local system.

* `--archive` preserves file permissions and structure
* `--verbose` shows detailed output
* `$server:` specifies the remote server
* `configs/$server.conf` saves the file locally with the server name

---

### 7. done Keyword

```
done
```

The `done` keyword marks the end of the loop.

---

## Advantages of Using Bash Scripting

### 1. Available Everywhere

Bash is available in almost every Unix and Linux environment by default. You do not need to install additional runtimes like Python or Node.js.

### 2. Easy Access to System Binaries

Bash scripts can directly run system binaries (compiled programs). For example, if a tool like `doctl` or `rsync` is installed, it can be used immediately inside a script.

### 3. Easy Testing in Terminal

The commands written in a Bash script can also be executed directly in the terminal. This makes testing and debugging much simpler.

---

## Learning Outcome

Understanding Bash scripting improves your automation skills and makes you more powerful and efficient on the command line. It helps you manage systems, automate repetitive tasks, and work like a command-line expert.

---

## Questions and Answers

### 1. What is the purpose of the "shebang" line in a Bash script?

**Correct Answer:** It indicates what interpreter should be used for the script.

### 2. In the example script, what does the line `for server in "${servers[@]}"` accomplish?

**Correct Answer:** It iterates through each element in the servers array.

### 3. Which of the following is NOT mentioned as an advantage of Bash scripting?

**Correct Answer:** Bash scripts run faster than Python or JavaScript.
