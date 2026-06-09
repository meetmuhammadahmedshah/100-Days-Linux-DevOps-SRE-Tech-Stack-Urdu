# PRACTICE LAB
# Day 34 – Creating, Managing and Deleting Aliases in Linux
## June 10th, 2026

> Based on Linux Administration Concepts and Alias Management

---

# Objective

The objective of this lab is to learn how to:

1. Understand what an Alias is.
2. View existing aliases.
3. Create temporary aliases.
4. Use aliases to simplify commands.
5. Delete temporary aliases.
6. Create permanent aliases.
7. Verify permanent aliases.
8. Remove permanent aliases.
9. Understand how aliases improve Linux Administration.

---

# Table of Contents

| Task | Title |
|------|--------|
| 1 | What is an Alias? |
| 2 | View Existing Aliases |
| 3 | Create a Temporary Alias |
| 4 | Use a Temporary Alias |
| 5 | Delete a Temporary Alias |
| 6 | Create a Permanent Alias |
| 7 | Verify a Permanent Alias |
| 8 | Remove a Permanent Alias |
| 9 | Review Questions |
| 10 | Lab Summary |

---

# Introduction

## What is an Alias?

An Alias is another name for a command.

Aliases allow Linux Administrators to:

- Create shortcut commands
- Simplify long commands
- Increase productivity
- Reduce typing mistakes
- Improve efficiency

For example:

Instead of typing:

~~~bash
ls -l /root
~~~

you can create an alias:

~~~bash
alias lh='ls -l /root'
~~~

Now simply typing:

~~~bash
lh
~~~

will run:

~~~bash
ls -l /root
~~~

---

# Alias Command Syntax

## General Syntax

~~~bash
alias alias_name='actual_command'
~~~

### Components

| Component | Description |
|------------|-------------|
| alias | Alias command |
| alias_name | New shortcut name |
| actual_command | Real command executed |

---

# Task 1 - View Existing Aliases

## Objective

Display all aliases currently configured.

### Run

~~~bash
alias
~~~

### Questions

1. How many aliases are displayed?
2. Which aliases already exist?
3. Why might Linux create default aliases?

### Notes

Linux distributions often include aliases such as:

~~~bash
alias ll='ls -l'
alias la='ls -a'
alias l='ls -CF'
~~~

---

# Task 2 - Create a Temporary Alias

## Objective

Create an alias that works only in the current session.

### Run

~~~bash
alias lh='ls -l /root'
~~~

### Verify

~~~bash
alias
~~~

### Questions

1. Do you see the alias `lh`?
2. What command does `lh` execute?

---

# Task 3 - Use a Temporary Alias

## Objective

Use the newly created alias.

### Run

~~~bash
lh
~~~

### Expected Result

The contents of:

~~~text
/root
~~~

should be displayed.

### Questions

1. Did the alias work?
2. Was it easier than typing the full command?

---

# Task 4 - Create Additional Temporary Aliases

## Objective

Practice creating multiple aliases.

### Run

~~~bash
alias mydate='date'
alias myuser='whoami'
alias myhost='hostname'
alias myup='uptime'
~~~

### Verify

~~~bash
alias
~~~

### Test Each Alias

~~~bash
mydate
myuser
myhost
myup
~~~

### Questions

1. Which alias was most useful?
2. Which command would you personally create an alias for?

---

# Task 5 - Delete a Temporary Alias

## Objective

Remove an alias from the current session.

### Run

~~~bash
unalias lh
~~~

### Verify

~~~bash
alias
~~~

### Test

~~~bash
lh
~~~

### Expected Result

~~~text
bash: lh: command not found
~~~

### Questions

1. What command removes an alias?
2. What happened when you tried to run `lh` again?

---

# Understanding Temporary Aliases

## Important Note

Temporary aliases:

- Exist only in the current session.
- Are removed automatically when you:
  - Log out
  - Close the terminal
  - Restart the system

---

# Task 6 - Create a Permanent Alias

## Objective

Create an alias that remains available after logout and reboot.

### Step 1 - Open .bashrc

Run

~~~bash
vi ~/.bashrc
~~~

OR

~~~bash
nano ~/.bashrc
~~~

---

### Step 2 - Add the Following Alias

Add this line at the bottom of the file:

~~~bash
alias llroot='ls -l /root'
~~~

Save and exit.

---

### Step 3 - Reload .bashrc

Run

~~~bash
source ~/.bashrc
~~~

---

### Verify

Run

~~~bash
alias
~~~

### Test

~~~bash
llroot
~~~

### Questions

1. Why did we modify `.bashrc`?
2. Why did we run `source ~/.bashrc`?

---

# Task 7 - Verify Permanent Alias

## Objective

Verify that the alias survives future sessions.

### Run

~~~bash
exit
~~~

Log back into the system.

### Verify

~~~bash
alias
~~~

### Test

~~~bash
llroot
~~~

### Questions

1. Did the alias remain available?
2. Why is it called a permanent alias?

---

# Task 8 - Remove a Permanent Alias

## Objective

Delete a permanent alias.

### Step 1 - Open .bashrc

Run

~~~bash
vi ~/.bashrc
~~~

OR

~~~bash
nano ~/.bashrc
~~~

---

### Step 2 - Locate

~~~bash
alias llroot='ls -l /root'
~~~

Delete the line.

---

### Step 3 - Reload Configuration

Run

~~~bash
source ~/.bashrc
~~~

---

### Verify

~~~bash
alias
~~~

### Test

~~~bash
llroot
~~~

### Expected Result

~~~text
command not found
~~~

### Questions

1. Why did the alias disappear?
2. What file stores permanent aliases?

---

# Task 9 - Create Your Own Administrator Aliases

## Objective

Create useful aliases that a Linux Administrator might use daily.

### Examples

~~~bash
alias mylogs='ls -l /var/log'
alias mynet='ip addr'
alias mydisk='df -h'
alias mymem='free -h'
alias myproc='ps -ef'
~~~

### Test

~~~bash
mylogs
mynet
mydisk
mymem
myproc
~~~

### Discussion

Which aliases would make your daily work easier?

---

# Review Questions

1. What is an Alias?
2. Why are aliases useful?
3. What command displays all aliases?
4. What command creates an alias?
5. What command removes an alias?
6. What is the difference between a temporary alias and a permanent alias?
7. Which file is commonly used to store permanent aliases?
8. What does `source ~/.bashrc` do?
9. Why should Linux Administrators use aliases?
10. Give three examples of aliases you would use daily.

---

# Lab Summary

In this lab you learned how to:

- View existing aliases
- Create temporary aliases
- Use aliases
- Delete temporary aliases
- Create permanent aliases
- Store aliases in `.bashrc`
- Reload shell configuration
- Remove permanent aliases
- Improve efficiency using shortcut commands

---

# Important Lesson

Aliases are one of the easiest ways to become more productive as a Linux Administrator.

Instead of typing long commands repeatedly:

~~~bash
ls -l /var/log
~~~

you can simply create:

~~~bash
alias logs='ls -l /var/log'
~~~

and use:

~~~bash
logs
~~~

This saves time and reduces typing errors.

---

# End of Lab

🐧 Happy Learning Linux Administration!