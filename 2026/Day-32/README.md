# PRACTICE LAB
# Day 32 – Login Process, systemd, Shells aur Initialization Files
## June 8th, 2026

> NIT Academy ki Class Notes aur Slides par Mabni

---

# Objective

Is Practice Lab ke end tak students:

1. Linux Kernel aur Operating System Version check kar sakenge.
2. Verify kar sakenge ke `systemd` PID 1 par run kar raha hai.
3. Apni current Linux Shell identify kar sakenge.
4. Apni shell ka Process ID (PID) dekh sakenge.
5. `/etc` configuration directory ko explore kar sakenge.
6. `/etc/shells` file ko Absolute aur Relative Path se read kar sakenge.
7. `ping` command ka purpose samajh sakenge.
8. Basic troubleshooting commands ki importance samajh sakenge.
9. Global Initialization Files identify kar sakenge.
10. Configuration files ka backup lena seekh sakenge.

---

# Table of Contents

| Task | Title |
|------|--------|
| 1 | [Kernel aur Operating System Version Check Karna](#task-1---kernel-aur-operating-system-version-check-karna) |
| 2 | [systemd ko PID 1 ke Tor Par Verify Karna](#task-2---systemd-ko-pid-1-ke-tor-par-verify-karna) |
| 3 | [Current Linux Shell Identify Karna](#task-3---current-linux-shell-identify-karna) |
| 4 | [Apni Shell ka PID Check Karna](#task-4---apni-shell-ka-pid-check-karna) |
| 5 | [/etc Configuration Directory Explore Karna](#task-5---etc-configuration-directory-explore-karna) |
| 6 | [/etc/shells File Read Karna](#task-6---etcshells-file-read-karna) |
| 7 | [Ping Command Practice](#task-7---ping-command-practice) |
| 8 | [Basic Troubleshooting Commands](#task-8---basic-troubleshooting-commands) |
| 9 | [Global Initialization Files Check Karna](#task-9---global-initialization-files-check-karna) |
| 10 | [Configuration File ka Backup Lena](#task-10---configuration-file-ka-backup-lena) |
| 11 | [Final Review Questions](#final-review-questions) |
| 12 | [Lab Summary](#lab-summary) |

---

# Introduction

Linux Login Process aur Shell Environment ko samajhne ke liye kuch important concepts hain:

- systemd
- PID aur PPID
- Bash Shell
- Login Shell
- Non-Login Shell
- Initialization Files
- Global Configuration Files
- User Configuration Files

Ek Linux System Administrator ko in tamam concepts ki practical understanding honi chahiye.

---

# Task 1 - Kernel aur Operating System Version Check Karna

## Question

Aap ka Kernel Version aur Operating System Version kya hai?

---

## Run:

```bash
uname -a
```

```bash
uname -r
```

```bash
cat /etc/os-release
```

---

## Notes

| Command | Purpose |
|----------|----------|
| `uname -a` | Kernel aur system ki detailed information |
| `uname -r` | Sirf kernel version |
| `cat /etc/os-release` | Operating System version aur release information |

---

## Student Observation

Likhein:

```text
Kernel Version:
Operating System:
```

---

# Task 2 - systemd ko PID 1 ke Tor Par Verify Karna

## Question

Aap kaise verify karenge ke systemd run kar raha hai?

---

## Run:

```bash
ps 1
```

```bash
ps -e
```

---

## Notes

Linux boot hone ke baad sab se pehla process:

```text
systemd
```

hota hai aur iska PID:

```text
1
```

hota hai.

systemd tamam child processes ka parent hota hai.

---

## Student Observation

Jawab dein:

1. PID 1 ka process kaunsa hai?
2. systemd kyun important hai?
3. `ps -e` kya show karta hai?

---

# Task 3 - Current Linux Shell Identify Karna

## Question

Aap kaunsi Linux Shell use kar rahe hain?

---

## Run:

```bash
echo $SHELL
```

---

## Example Output

```text
/bin/bash
```

---

## Notes

Shell user aur Linux operating system ke darmiyan interface provide karti hai.

Common Shells:

- bash
- sh
- zsh
- ksh

---

# Task 4 - Apni Shell ka PID Check Karna

## Question

Apni Shell ka Process ID kaise check karenge?

---

## Run:

```bash
ps $$
```

```bash
echo $$
```

```bash
echo $0
```

---

## Notes

| Command | Purpose |
|----------|----------|
| `ps $$` | Current shell process show karta hai |
| `echo $$` | Current shell ka PID display karta hai |
| `echo $0` | Shell ka naam display karta hai |

---

## Student Observation

Likhein:

```text
Shell Name:
Shell PID:
```

---

# Task 5 - /etc Configuration Directory Explore Karna

## Question

Linux mein configuration files zyada tar kis directory mein hoti hain?

---

## Run:

```bash
ls -l /etc
```

```bash
cd /etc
```

```bash
ls
```

---

## Notes

`/etc` Linux ki sab se important configuration directory hai.

Examples:

```text
/etc/profile
/etc/bashrc
/etc/passwd
/etc/group
/etc/shadow
/etc/shells
```

---

# Task 6 - /etc/shells File Read Karna

## Question

Read-only mode mein `/etc/shells` file kaise dekhenge?

---

## Method 1 – Absolute Path

Run:

```bash
cat /etc/shells
```

---

## Method 2 – Relative Path

Run:

```bash
cd /etc
```

```bash
pwd
```

```bash
cat shells
```

---

## Notes

### Absolute Path

```text
/etc/shells
```

Root (`/`) se start hota hai.

### Relative Path

```text
shells
```

Current directory ke mutabiq access hota hai.

---

# Task 7 - Ping Command Practice

## Question

Ping command hume kya sikhati hai?

---

## Run:

```bash
ping google.com
```

```bash
ping -c 5 google.com
```

```bash
ping 8.8.8.8
```

---

## Important Note

Running process ko stop karne ke liye:

```text
Ctrl + C
```

press karein.

Linux foran aap ko command prompt par wapas le aayega.

---

## Notes

Ping command test karti hai:

- Network connectivity
- DNS resolution
- Internet access
- Packet response time
- Remote host reachability

---

# Task 8 - Basic Troubleshooting Commands

## Question

Har Linux Administrator ko problem solve karte waqt in commands ko run karna chahiye.

---

## Run:

```bash
date
```

```bash
uptime
```

```bash
hostname
```

```bash
whoami
```

```bash
pwd
```

```bash
cd ~
```

---

## Notes

| Command | Importance |
|----------|------------|
| `date` | System date/time check karta hai |
| `uptime` | System kitni der se chal raha hai |
| `hostname` | Machine ka naam |
| `whoami` | Logged-in user |
| `pwd` | Current directory |
| `cd ~` | Home directory mein le jata hai |

---

# Task 9 - Global Initialization Files Check Karna

## Question

Do major Global Initialization Files kaunsi hain?

---

## Run:

```bash
cat /etc/profile
```

```bash
cat /etc/bashrc
```

---

## Notes

| File | Purpose |
|--------|----------|
| `/etc/profile` | Global Login Shell Initialization File |
| `/etc/bashrc` | Global Interactive Non-Login Shell Initialization File |

Yeh files system ke tamam users ko affect karti hain.

---

# Task 10 - Configuration File ka Backup Lena

## Question

Critical configuration files modify karne se pehle kya karna chahiye?

---

## Answer

Hamesha backup lena chahiye.

---

## Backup Create Karein

Run:

```bash
cp -r /etc/profile /etc/profile_bak
```

---

## Verify Karein

Run:

```bash
cd /etc
```

```bash
ls
```

Aap ko nazar aana chahiye:

```text
profile
profile_bak
```

---

## Important Warning

Kabhi bhi:

```text
/etc/profile
```

delete mat karein.

Yeh ek critical configuration file hai.

---

## Backup File Delete Karein

Run:

```bash
rm /etc/profile_bak
```

---

## Important Note

`profile_bak` ek file hai.

Is liye:

```bash
rm
```

use hoga.

`rmdir`

sirf empty directories ke liye use hota hai.

---

# Final Review Questions

1. Kernel Version dekhne ki command kya hai?
2. Operating System Version kaise check karte hain?
3. PID 1 kya hota hai?
4. systemd kyun important hai?
5. Current Shell kaise identify karte hain?
6. Shell ka PID kaise check karte hain?
7. `/etc` directory ka purpose kya hai?
8. Absolute aur Relative Path mein kya difference hai?
9. Ping command kya test karti hai?
10. Running process ko kaise stop karte hain?
11. Do major Global Initialization Files kaunsi hain?
12. Backup lena kyun zaroori hai?
13. `rm` aur `rmdir` mein kya difference hai?

---

# Lab Summary

Is lab mein aap ne seekha:

- Kernel aur OS Version check karna
- systemd ko PID 1 ke tor par verify karna
- Apni current Shell identify karna
- Shell ka PID check karna
- `/etc` configuration directory explore karna
- `/etc/shells` file read karna
- Absolute aur Relative Paths samajhna
- Ping command use karna
- Ctrl + C se process stop karna
- Basic troubleshooting commands chalana
- Global Initialization Files identify karna
- Critical configuration files ka backup lena

---

# Final Note

Har Linux System Administrator ko hamesha yaad rakhna chahiye:

```bash
date
uptime
hostname
whoami
pwd
```

Yeh commands troubleshooting ka bunyadi hissa hain.

Aur:

```text
Backup First, Change Later!
```

---
# End of Lab
🐧 Happy Learning Linux!