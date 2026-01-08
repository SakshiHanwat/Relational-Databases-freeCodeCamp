# Bash Scripting Review – Complete Notes

This README file contains a complete review of Bash scripting concepts. It is written in easy English and is suitable for notes, revision, interviews, and practice. Nothing has been skipped, and all topics are explained in a structured way.

---

## Bash Scripting Basics

Bash scripting means writing a sequence of Bash commands inside a file and then executing that file using the Bash shell. Instead of typing commands one by one in the terminal, we can automate tasks by putting commands in a script file.

### Shebang

The shebang is the first line of a Bash script. It tells the system which interpreter should be used to run the script.

```
#!/bin/bash
```

This means the script should be executed using the Bash shell.

---

## Variables in Bash

### Variable Assignment

Variables are created using the syntax:

```
VARIABLE_NAME=value
```

There must be no spaces around the `=` sign.

Examples:

```
NAME=John
MESSAGE="Hello World"
COUNT=5
TEXT="The next number is, "
```

Arrays can also be created:

```
servers=("prod" "dev")
```

### Variable Usage

To access a variable, use `$` before its name.

```
echo $NAME
echo "The message is: $MESSAGE"
```

### Variable Interpolation

Variables can be used inside strings and commands.

```
TEXT="The next number is, "
NUMBER=42
echo $TEXT B:$NUMBER
echo $TEXT I:$NUMBER
```

Example with command:

```
echo "Pulling $server"
rsync --archive --verbose $server:/etc/nginx/conf.d/server.conf configs/$server.conf
```

### Variable Scope

Bash scripts run from top to bottom, so variables must be defined before they are used.

```
NAME="Alice"
echo $NAME
```

---

## User Input

The `read` command is used to take input from the user.

```
read USERNAME
echo "Hello $USERNAME"
```

---

## Comments

Comments are ignored by the shell and are used for explanation.

### Single-line Comment

```
# This is a comment
NAME="John"  # Comment at end of line
```

### Multi-line Comment

```
: '
This is a multi-line comment
Everything inside is ignored
'
```

---

## Built-in Commands and Help

Bash has built-in commands that are executed directly by the shell.

```
help
help if
help function
```

---

## Finding Command Locations

The `which` command shows where an executable is located.

```
which bash
which python
which ls
```

---

## Manual Pages

The `man` command shows detailed documentation.

```
man echo
man ls
man bash
```

---

## Help Flags

Many commands support `--help` for quick help.

```
ls --help
chmod --help
mv --help
```

---

## Echo Command Options

The `-e` option enables escape characters like `\n`.

```
echo -e "Line 1\nLine 2"
echo ""
echo -e "\n~~ Program Title ~~\n"
echo "Line 1\nLine 2"
```

---

## Script Arguments

Script arguments are accessed using `$` variables.

```
echo $*
echo $@
echo $1
echo $2
```

---

## Double Bracket Expressions [[ ]]

Used for conditional testing.

```
[[ $variable == "value" ]]
[[ $number -gt 10 ]]
[[ -f filename.txt ]]
```

### String Comparison

```
[[ "apple" == "apple" ]]
[[ "apple" != "orange" ]]
[[ "apple" < "banana" ]]
[[ "zebra" > "apple" ]]
```

### Numeric Comparison

```
[[ $number -eq 5 ]]
[[ $count -ne 0 ]]
[[ $age -ge 18 ]]
[[ $score -lt 100 ]]
```

### Logical Operators

```
[[ $age -ge 18 && $age -le 65 ]]
[[ $name == "John" || $name == "Jane" ]]
[[ ! -f missing_file.txt ]]
```

### File Test Operators

```
[[ -e /path/to/file ]]
[[ -f script.sh ]]
[[ -d /home/user ]]
[[ -x program ]]
```

### Pattern Matching with =~

```
[[ "hello123" =~ [0-9]+ ]]
[[ "email@domain.com" =~ ^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$ ]]
[[ "filename.txt" =~ \.txt$ ]]
```

### Variable Existence

```
[[ ! $variable ]]
```

---

## Double Parentheses Expressions (( ))

Used for arithmetic operations.

```
(( result = 10 + 5 ))
(( count++ ))
(( total += value ))
```

### Arithmetic Operators

```
+  -  *  /  %  **
```

### Assignment Operators

```
(( counter += 5 ))
(( total -= cost ))
```

### Increment / Decrement

```
(( ++counter ))
(( index++ ))
```

### Comparison and Logical Operators

```
(( age >= 18 ))
(( score < 100 ))
(( age >= 18 && age <= 65 ))
```

### Bitwise Operators

```
& | ^ ~ << >>
```

### Ternary Operator

```
(( result = (score >= 60) ? 1 : 0 ))
```

### Command Substitution

```
result=$(( 10 + 5 ))
echo "The answer is $(( a * b ))"
```

---

## Control Flow – If Statements

```
if (( NUMBER <= 15 ))
then
    echo "B:$NUMBER"
elif [[ $NUMBER -le 30 ]]
then
    echo "I:$NUMBER"
else
    echo "O:$NUMBER"
fi
```

---

## Command Execution and Exit Status

```
ls -l; echo "Done"
echo $?
bad_command; echo $?
```

---

## Subshells and Command Substitution

```
( cd /tmp; echo "Current dir: $(pwd)" )
current_date=$(date)
```

---

## Sleep Command

```
sleep 3
sleep 0.5
```

---

## Loops

### While Loop

```
while [[ $I -ge 0 ]]
do
    echo $I
    (( I-- ))
done
```

### Until Loop

```
until [[ $QUESTION =~ \?$ ]]
do
    read QUESTION
done
```

### For Loop

```
for server in "${servers[@]}"
do
    echo "Processing $server"
done
```

---

## Arrays

```
RESPONSES=("Yes" "No" "Maybe")
echo ${RESPONSES[@]}
```

Inspect array:

```
declare -p RESPONSES
```

---

## Functions

```
GET_FORTUNE() {
    read QUESTION
}
```

With arguments:

```
GET_FORTUNE again
```

---

## Random Numbers

```
NUMBER=$(( RANDOM % 6 ))
DICE=$(( RANDOM % 6 + 1 ))
```

Random array access:

```
N=$(( RANDOM % 6 ))
echo ${RESPONSES[$N]}
```

---

## Environment Variables

```
echo $HOME
echo $PATH
printenv
```

---

## File Creation and Scripts

```
touch script.sh
bash script.sh
./script.sh
```

Add execute permission:

```
chmod +x script.sh
```

---

## Script Organization Best Practices

* Start with shebang
* Add comments
* Define variables at top
* Functions in middle
* Main logic at bottom

---

## Sequential Script Execution

```
./setup.sh
./interactive.sh
./processing.sh
./cleanup.sh
```

---

## Assignment

Review all Bash Scripting topics and complete the assignment.
