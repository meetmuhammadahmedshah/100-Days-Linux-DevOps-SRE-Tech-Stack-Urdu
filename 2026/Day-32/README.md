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
4. Apni Shell ka PID check kar sakenge.
5. `/etc` configuration directory ko explore kar sakenge.
6. `/etc/shells` file ko Absolute aur Relative Path se read kar sakenge.
7. `ping` command aur network connectivity ko samajh sakenge.
8. Basic troubleshooting commands ki importance samajh sakenge.
9. Global Bash Initialization Files identify kar sakenge.
10. Critical configuration files ka backup lena seekh sakenge.

---

# Table of Contents

| Task | Title |
|------|--------|
| 1 | Kernel aur Operating System Version Check Karna |
| 2 | systemd ko PID 1 ke Tor Par Verify Karna |
| 3 | Current Linux Shell Identify Karna |
| 4 | Apni Shell ka PID Check Karna |
| 5 | /etc Configuration Directory Explore Karna |
| 6 | /etc/shells File Read Karna |
| 7 | Ping Command Practice |
| 8 | Basic Troubleshooting Commands |
| 9 | Global Initialization Files Check Karna |
| 10 | Configuration File ka Backup Lena |
| 11 | Final Review Questions |
| 12 | Lab Summary |

---

# Task 1 - Kernel aur Operating System Version Check Karna

## Sawaal

Aap ka Linux Kernel Version aur Operating System Version kya hai?

### Run

~~~bash
uname -a
uname -r
cat /etc/os-release
~~~

### Student Observation

Neeche likhein:

~~~text
Kernel Version:
Operating System:
~~~

### Notes

- `uname -a` poori kernel aur system information dikhata hai.
- `uname -r` sirf kernel version dikhata hai.
- `cat /etc/os-release` Operating System ki detail dikhata hai.

---

# Task 2 - systemd ko PID 1 ke Tor Par Verify Karna

## Sawaal

Aap kaise verify karenge ke `systemd` run kar raha hai?

### Run

~~~bash
ps 1
ps -e
~~~

### Notes

- Linux boot hone ke baad sab se pehla process `systemd` hota hai.
- systemd aam tor par PID 1 rakhta hai.
- systemd tamam child processes ka parent hota hai.

### Student Observation

Jawab dein:

1. PID 1 par kaunsa process hai?
2. PID 1 kyun important hai?
3. `ps -e` kya show karta hai?

---

# Task 3 - Current Linux Shell Identify Karna

## Sawaal

Aap kaise maloom karenge ke aap kaunsi Linux Shell use kar rahe hain?

### Run

~~~bash
echo $SHELL
~~~

### Example Output

~~~text
/bin/bash
~~~

### Student Observation

Neeche likhein:

~~~text
Current Shell:
~~~

### Notes

Common Linux Shells:

- Bash
- Sh
- Zsh
- Ksh

Shell user aur Linux operating system ke darmiyan interface provide karti hai.

---

# Task 4 - Apni Shell ka PID Check Karna

## Sawaal

`echo $SHELL` ke ilawa aap apni shell ka Process ID kaise check karenge?

### Run

~~~bash
ps $$
echo $$
echo $0
~~~

### Student Observation

Neeche likhein:

~~~text
Shell PID:
Shell Name:
~~~

### Notes

| Command | Purpose |
|----------|----------|
| `ps $$` | Current shell process show karta hai |
| `echo $$` | Current shell ka PID show karta hai |
| `echo $0` | Shell ka naam show karta hai |

---

# Task 5 - /etc Configuration Directory Explore Karna

## Sawaal

Linux mein configuration files zyada tar kis directory mein hoti hain?

### Run

~~~bash
ls -l /etc
cd /etc
ls
~~~

### Student Observation

Jawab dein:

1. Aap ko kis qisam ki files nazar aati hain?
2. `/etc` directory kyun important hai?

### Notes

Important files:

~~~text
/etc/profile
/etc/bashrc
/etc/passwd
/etc/group
/etc/shadow
/etc/shells
~~~

---

# Task 6 - /etc/shells File Read Karna

## Sawaal

Aap `/etc/shells` file ko read-only mode mein kaise dekh sakte hain?

### Method 1 - Absolute Path

#### Run

~~~bash
cat /etc/shells
~~~

---

### Method 2 - Relative Path

#### Run

~~~bash
cd /etc
pwd
cat shells
~~~

### Student Observation

Jawab dein:

1. Aap ke system par kitni shells available hain?
2. Absolute Path aur Relative Path mein kya farq hai?

### Notes

Absolute Path Example:

~~~text
/etc/shells
~~~

Relative Path Example:

~~~text
shells
~~~

---

# Task 7 - Ping Command Practice

## Sawaal

Ping command hume kya sikhati hai?

### Run

~~~bash
ping google.com
ping -c 5 google.com
ping 8.8.8.8
~~~

### Important Note

Running process ko stop karne ke liye:

~~~text
Ctrl + C
~~~

press karein.

### Student Observation

Jawab dein:

1. Kya Google reachable tha?
2. IP address ko direct ping karne par kya hua?
3. Linux Administrator ping kyun use karta hai?

### Notes

Ping command test karti hai:

- Network Connectivity
- DNS Resolution
- Internet Access
- Response Time
- Remote Host Reachability

---

# Task 8 - Basic Troubleshooting Commands

## Sawaal

Jab bhi aap kisi Linux problem ko troubleshoot karein to neeche wali commands run karein aur sochain ke yeh kyun important hain.

### Run

~~~bash
date
uptime
hostname
whoami
pwd
cd ~
~~~

### Student Observation

Table complete karein:

| Command | Yeh Kyun Important Hai? |
|----------|-------------------------|
| date | |
| uptime | |
| hostname | |
| whoami | |
| pwd | |
| cd ~ | |

---

# Task 9 - Global Initialization Files Check Karna

## Sawaal

Do major Global Initialization Files kaunsi hain?

### Run

~~~bash
cat /etc/profile
cat /etc/bashrc
~~~

### Student Observation

Jawab dein:

1. Kaunsi file Login Shell ko affect karti hai?
2. Kaunsi file Non-Login Shell ko affect karti hai?
3. Yeh files kyun important hain?

### Notes

| File | Purpose |
|--------|----------|
| `/etc/profile` | Global Login Shell Initialization File |
| `/etc/bashrc` | Global Interactive Shell Initialization File |

Yeh files tamam users ko affect karti hain.

---

# Task 10 - Configuration File ka Backup Lena

## Sawaal

Critical configuration file ko modify ya delete karne se pehle kya karna chahiye?

### Jawab

Hamesha backup lena chahiye.

### Run

~~~bash
cp -r /etc/profile /etc/profile_bak
cd /etc
ls
~~~

### Verify

Aap ko yeh files nazar aani chahiye:

~~~text
profile
profile_bak
~~~

### Important Warning

Kabhi bhi:

~~~text
/etc/profile
~~~

delete mat karein.

Yeh ek critical system file hai.

### Backup File Delete Karna

~~~bash
rm /etc/profile_bak
~~~

### Notes

- `rm` files delete karta hai.
- `rmdir` empty directories delete karta hai.
- `profile_bak` ek file hai, is liye `rm` use hoga.

---

# Final Review Questions

1. Kernel Version dekhne ki command kya hai?
2. Operating System information dekhne ki command kya hai?
3. PID 1 kya hota hai?
4. systemd kyun important hai?
5. Current Shell dekhne ki command kya hai?
6. Shell PID dekhne ki command kya hai?
7. `/etc` directory ka purpose kya hai?
8. Absolute Path aur Relative Path mein kya farq hai?
9. Ping command kya test karti hai?
10. Running process ko kaise stop karte hain?
11. Do major Global Initialization Files kaunsi hain?
12. Configuration file ka backup lena kyun zaroori hai?
13. `rm` aur `rmdir` mein kya difference hai?

---

# Lab Summary

Is lab mein aap ne practice ki:

- Kernel Version check karna
- Operating System information dekhna
- systemd ko PID 1 verify karna
- Apni current Shell identify karna
- Shell PID check karna
- `/etc` directory explore karna
- `/etc/shells` file read karna
- Absolute aur Relative Paths samajhna
- Ping command use karna
- Ctrl + C se process stop karna
- Basic troubleshooting commands chalana
- Global Initialization Files dekhna
- Critical configuration files ka backup lena

---

# Final Note

Har Linux System Administrator ko hamesha yaad rakhna chahiye:

~~~bash
date
uptime
hostname
whoami
pwd
~~~

Yeh commands troubleshooting ki bunyaad hain.

## Golden Rule

~~~text
PEHLAY BACKUP LO, PHIR CHANGE KARO
~~~

---

# End of Lab

🐧 Happy Learning Linux!