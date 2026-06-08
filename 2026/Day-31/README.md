# Linux Administration Bootcamp
# Day 30/31 – Login Process, systemd, Shells aur Initialization Files
## June 6/7th, 2026

> Class Notes aur Slides par mabni NIT Academy Session :contentReference[oaicite:0]{index=0}

---

# Objective

Is class ke end tak students:

1. Linux Login Process ko samajh sakenge.
2. Linux ke pehle process (PID 1) ko identify kar sakenge.
3. PID aur PPID ka difference samajh sakenge.
4. Apni current shell aur uska PID identify kar sakenge.
5. Login Shell aur Non-Login Shell ka difference samajh sakenge.
6. Bash Initialization Files ka role samajh sakenge.
7. Global aur User Initialization Files ka difference samajh sakenge.
8. PATH variable ka purpose samajh sakenge.
9. Custom commands create kar sakenge.
10. `.bash_logout` file ka role samajh sakenge.

---

# Table of Contents

1. Linux Login Process
2. systemd aur PID 1
3. PID aur PPID
4. Task 1 – systemd Verify Karna
5. Task 2 – Apni Shell Identify Karna
6. Task 3 – Process Hierarchy Samajhna
7. Login Shell vs Non-Login Shell
8. Initialization Files
9. Global vs User Initialization Files
10. Task 4 – Initialization Files Check Karna
11. PATH Variable
12. Task 5 – PATH Check Karna
13. Task 6 – Apna Custom Command Banana
14. .bash_logout
15. Task 7 – Initialization Files Test Karna
16. Review Questions
17. Lab Summary

---

# Linux Login Process

Jab Linux boot hota hai to process kuch is tarah hota hai:

```text
Kernel
   │
   ▼
systemd (PID 1)
   │
   ▼
sshd
   │
   ▼
bash
   │
   ▼
Initialization Files
   │
   ▼
[root@server ~]#
```

Linux mein koi bhi process khud se paida nahi hota.

Har process ka ek parent process hota hai.

---

# systemd – Sab se Pehla Process

Linux kernel load hone ke baad sab se pehla process start karta hai:

```bash
systemd
```

Ye process hamesha:

```text
PID 1
```

hota hai.

systemd ki zimmedari hai:

- Services start karna
- Networking start karna
- SSH start karna
- System ko manage karna

---

# PID aur PPID

## PID

PID ka matlab:

```text
Process ID
```

Har process ka unique number hota hai.

Example:

```text
230948 = bash
```

---

## PPID

PPID ka matlab:

```text
Parent Process ID
```

Ye batata hai ke process ko kis process ne launch kiya.

Example:

```text
sshd ---> bash
```

To:

```text
sshd = PPID
bash = PID
```

---

# Task 1 – systemd Verify Karna

## Objective

Linux ka pehla process verify karna.

### Run

```bash
ps 1
```

### Expected Output

```text
PID TTY      STAT   TIME COMMAND
1   ?        Ss     0:16 /usr/lib/systemd/systemd
```

---

## Discussion

1. PID 1 kaunsa process hai?
2. systemd ka role kya hai?
3. Agar PID 1 crash ho jaye to kya hoga?

---

# Task 2 – Apni Shell Identify Karna

## Objective

Current shell identify karna.

### Run

```bash
echo $SHELL
```

Example:

```text
/bin/bash
```

---

### Login Shell Verify Karein

Run:

```bash
shopt login_shell
```

Output:

```text
login_shell on
```

---

### Apni Shell ka PID Check Karein

Run:

```bash
echo $$
```

Example:

```text
230948
```

---

### Verify Karein

Run:

```bash
ps $$
```

Example:

```text
PID TTY      STAT TIME COMMAND
230948 pts/0 Ss   0:00 -bash
```

---

## Discussion

1. Aapki shell ka PID kya hai?
2. Bash ke aagay "-" sign kyun laga hua hai?

Example:

```text
-bash
```

---

# Task 3 – Process Hierarchy Samajhna

## Objective

Parent aur Child process relationship dekhna.

### Parent Process Check Karein

Run:

```bash
ps -fp $PPID
```

Example:

```text
sshd: root@pts/0
```

---

### Process Tree Dekhein

Run:

```bash
pstree -p $PPID
```

Example:

```text
sshd
 └── sshd
      └── bash
           └── pstree
```

---

## Discussion

1. Bash ko kis process ne launch kiya?
2. sshd ko kis process ne launch kiya?
3. systemd ko kis ne launch kiya?

---

# Login Shell vs Non-Login Shell

## Login Shell

Login Shell tab create hoti hai jab Linux aapse authentication karta hai.

Examples:

- SSH Login
- Guacamole Login
- Console Login

Execute hone wali files:

```text
/etc/profile
~/.bash_profile
~/.profile
```

---

## Non-Login Shell

Jab aap pehle se logged in hon aur nayi shell start karein:

```bash
bash
```

ya

```bash
/bin/bash
```

To ye Non-Login Shell hoti hai.

Execute hone wali files:

```text
/etc/bashrc
~/.bashrc
```

---

## Comparison

| Login Shell | Non-Login Shell |
|------------|----------------|
| Password Authentication | Authentication nahi |
| /etc/profile read karti hai | /etc/profile read nahi karti |
| .bash_profile read karti hai | .bashrc read karti hai |
| Pehli shell hoti hai | Additional shell hoti hai |

---

# Initialization Files

Initialization files user ka environment tayar karti hain.

Examples:

- PATH
- Prompt
- Aliases
- Functions
- Environment Variables

Prompt aane se pehle yeh files execute hoti hain.

---

# Global vs User Initialization Files

## Global Files

Sab users ko affect karti hain.

Location:

```text
/etc/profile
/etc/bashrc
```

Sirf root modify kar sakta hai.

---

## User Files

Sirf ek user ko affect karti hain.

Examples:

```text
~/.bash_profile
~/.bashrc
~/.bash_logout
```

User apni files modify kar sakta hai.

---

# Task 4 – Initialization Files Check Karna

## Global Files Dekhein

Run:

```bash
ls -l /etc/profile
ls -l /etc/bashrc
```

---

## Global Files Read Karein

Run:

```bash
cat /etc/profile
cat /etc/bashrc
```

---

## User Files Check Karein

Run:

```bash
ls -la ~ | grep bash
```

---

## Discussion

1. Kaunsi files sab users ko affect karti hain?
2. Kaunsi files sirf ek user ko affect karti hain?

---

# PATH Variable

PATH Linux ko batata hai ke commands kahan rakhi hui hain.

Run:

```bash
echo $PATH
```

Example:

```text
/root/.local/bin:/root/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin
```

---

# PATH Kaise Kaam Karta Hai

Jab aap type karte hain:

```bash
date
```

Bash left se right search karti hai.

Example:

```text
/root/bin
/usr/local/bin
/usr/sbin
/usr/bin
```

Jab command mil jaye to execute kar deti hai.

Example:

```text
/usr/bin/date
```

---

# Task 5 – PATH Check Karna

## PATH Display Karein

Run:

```bash
echo $PATH
```

---

## Commands Locate Karein

Run:

```bash
whereis date
whereis uptime
whereis ls
whereis mkdir
whereis touch
```

---

## Discussion

1. date command kahan hai?
2. ls command kahan hai?
3. Agar PATH mein command na ho to kya hoga?

---

# Task 6 – Apna Custom Command Banana

## Objective

Apni Linux command create karna.

### Directory Create Karein

Run:

```bash
mkdir -p /getstuff/bin
```

---

### Script Create Karein

Run:

```bash
echo -e '#!/bin/bash\necho "Success! The getstuff application is running!"' > /getstuff/bin/hello
```

---

### Executable Banayein

Run:

```bash
chmod +x /getstuff/bin/hello
```

---

### Test Karein

Run:

```bash
hello
```

Expected:

```text
command not found
```

---

### PATH Mein Add Karein

Run:

```bash
echo 'PATH=$PATH:/getstuff/bin ; export PATH' >> ~/.bashrc
```

---

### Reload Karein

Run:

```bash
source ~/.bashrc
```

---

### Dobarah Test Karein

Run:

```bash
hello
```

Expected:

```text
Success! The getstuff application is running!
```

---

# .bash_logout

File:

```text
~/.bash_logout
```

User logout karte waqt execute hoti hai.

Examples:

- Screen clear karna
- Goodbye message show karna
- Logout logging karna

---

# Task 7 – Initialization Files Test Karna

## User Create Karein

Run:

```bash
useradd john
passwd john
```

---

## /etc/profile Modify Karein

Run:

```bash
vi /etc/profile
```

Neeche add karein:

```bash
echo "/etc/profile executed"
```

Save karein:

```text
:wq!
```

---

## John User Se Login Karein

Observe:

```text
/etc/profile executed
```

---

## Discussion

1. Message kis file ne display kiya?
2. Sab users ko message kyun nazar aya?
3. Agar change .bashrc mein hota to kya farq hota?

---

# Review Questions

1. PID 1 kya hota hai?
2. systemd ka role kya hai?
3. PID aur PPID mein kya difference hai?
4. Login Shell kya hoti hai?
5. Non-Login Shell kya hoti hai?
6. Login ke dauran kaunsi files execute hoti hain?
7. .bashrc ka purpose kya hai?
8. .bash_profile ka purpose kya hai?
9. .bash_logout kis liye use hoti hai?
10. PATH kya hai?
11. Linux PATH ko left se right kyun search karta hai?
12. Shell ka PID kaise dekhte hain?
13. Current shell kaise identify karte hain?
14. .bashrc reload karne ki command kya hai?
15. Process tree dekhne ki command kya hai?

---

# Lab Summary

Is class mein aap ne seekha:

- Linux Login Process
- systemd PID 1 kyun hota hai
- sshd aur bash ka relationship
- PID aur PPID
- Login Shell aur Non-Login Shell
- Global aur User Initialization Files
- PATH variable
- Custom commands create karna
- .bash_logout ka role
- Bash startup process

Ye concepts bohat important hain:

- RHCSA
- RHCE
- Linux Administration
- DevOps
- System Engineering
- Infrastructure Support

---

# Mubarak Ho!

Aap ne Linux Login Process, Shells, Initialization Files aur PATH Variable ki practical understanding hasil kar li hai.

🐧 Happy Learning Linux!