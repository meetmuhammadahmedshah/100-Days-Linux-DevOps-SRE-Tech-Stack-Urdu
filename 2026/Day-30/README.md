# Linux Administration Bootcamp
# Day 30/ Day 31 – Directories, Paths aur Files
## June 6/7, 2026

---

# Objective

Is lab ke end tak students:

1. System ki current date aur time dekh sakenge.
2. Check kar sakenge ke Linux machine kitni der se chal rahi hai.
3. Filesystem mein apni current location identify kar sakenge.
4. Absolute Path aur Relative Path ka difference samajh sakenge.
5. Absolute Path use karke directories create kar sakenge.
6. Relative Path use karke directories create kar sakenge.
7. `touch` command se files create kar sakenge.
8. `ls` command se directories aur files verify kar sakenge.

---

# Table of Contents

1. Introduction
2. Linux mein Paths Samajhna
3. Task 1 – Date aur Time Display Karna
4. Task 2 – System Uptime Check Karna
5. Task 3 – Current Directory Check Karna
6. Task 4 – Directories Create Karna
   - Absolute Path
   - Relative Path
7. Task 5 – Files Create Karna
8. Verification Checklist
9. Review Questions
10. Challenge Task
11. Lab Summary

---

# Introduction

Linux mein har cheez filesystem structure ke andar store hoti hai.

Example:

```text
/
├── root
├── home
├── var
├── opt
├── etc
└── tmp
```

User filesystem ke andar move kar sakta hai aur directories aur files create kar sakta hai.

Do important concepts hain:

- Absolute Path
- Relative Path

---

# Linux Mein Paths Samajhna

## Absolute Path

Absolute Path hamesha root directory (`/`) se shuru hota hai.

Example:

```bash
/var/opt/images
```

Chahe aap filesystem mein kahin bhi hon, Linux is directory ko locate kar lega kyunke poora path diya gaya hai.

### Examples

```bash
/etc/passwd
/home/student
/var/log/messages
/var/opt/images
```

---

## Relative Path

Relative Path aapki current location se shuru hota hai.

Example:

```bash
projects
```

Linux is directory ko aapki current location ke relative create ya access karega.

### Examples

```bash
projects
documents
file1
images/photo.jpg
```

---

# Task 1 – Date aur Time Display Karna

## Objective

Current system date aur time display karna.

### Run

```bash
date
```

### Example Output

```text
Sat Jun 6 10:15:24 UTC 2026
```

### Notes

`date` command commonly use hoti hai:

- Logs create karne ke liye
- Troubleshooting ke liye
- Server time verify karne ke liye
- Timestamp check karne ke liye

---

# Task 2 – System Uptime Check Karna

## Objective

Check karna ke Linux system kitni der se chal raha hai.

### Run

```bash
uptime
```

### Example Output

```text
10:17:10 up 5 days, 4:22, 1 user, load average: 0.00, 0.01, 0.05
```

### Notes

`uptime` command show karti hai:

- Current time
- Machine kitni der se up hai
- Logged-in users ki tadaad
- Load averages

### Discussion

Students se poochain:

- Aapki machine kitni der se chal rahi hai?
- Kitne users logged in hain?
- Load average kya show kar raha hai?

---

# Task 3 – Current Directory Check Karna

## Objective

Filesystem mein apni current location identify karna.

### Run

```bash
pwd
```

### Example Output

```text
/root
```

### Notes

`pwd` ka matlab hai:

```text
Print Working Directory
```

Yeh aapko batata hai ke aap is waqt filesystem mein kahan maujood hain.

---

# Task 4 – Directories Create Karna

---

## Part A – Absolute Path Use Karna

### Objective

Poora path use karke directory create karna.

### Run

```bash
mkdir -p /var/opt/images
```

### Verify

```bash
ls -l /var/opt/
```

### Example Output

```text
drwxr-xr-x 2 root root 6 Jun 6 10:20 images
```

### Explanation

Directory create ho gayi chahe aap filesystem mein kahin bhi thay kyunke poora path diya gaya tha.

```text
/var/opt/images
```

Isay kehte hain:

```text
Absolute Path
```

---

## Part B – Relative Path Use Karna

### Step 1 – Current Location Check Karein

Run:

```bash
pwd
```

---

### Step 2 – Home Directory Mein Wapas Jayein

Run:

```bash
cd
```

Verify:

```bash
pwd
```

Expected Output:

```text
/root
```

---

### Step 3 – /var Directory Mein Jayein

Run:

```bash
cd /var
```

Verify:

```bash
pwd
```

Expected Output:

```text
/var
```

---

### Step 4 – opt Directory Mein Enter Karein

Run:

```bash
cd opt
```

Verify:

```bash
pwd
```

Expected Output:

```text
/var/opt
```

---

### Step 5 – Directory Create Karein

Run:

```bash
mkdir -p projects
```

---

### Step 6 – Verify Karein

Run:

```bash
ls -l
```

Expected Output:

```text
images
projects
```

### Explanation

Directory `projects` current location ke relative create hui:

```text
/var/opt
```

Is liye:

```text
projects
```

ban gaya:

```text
/var/opt/projects
```

Isay kehte hain:

```text
Relative Path
```

---

# Task 5 – Files Create Karna

## Objective

`touch` command use karke files create karna.

---

### Step 1 – Current Location Verify Karein

Run:

```bash
pwd
```

Expected Output:

```text
/var/opt
```

---

### Step 2 – Ek File Create Karein

Run:

```bash
touch summary.txt
```

---

### Step 3 – Multiple Files Create Karein

Run:

```bash
touch file{1..5}
```

Yeh files create karega:

```text
file1
file2
file3
file4
file5
```

---

### Step 4 – Verify Karein

Run:

```bash
ls -l
```

Example Output:

```text
-rw-r--r-- 1 root root 0 Jun 6 10:25 summary.txt
-rw-r--r-- 1 root root 0 Jun 6 10:25 file1
-rw-r--r-- 1 root root 0 Jun 6 10:25 file2
-rw-r--r-- 1 root root 0 Jun 6 10:25 file3
-rw-r--r-- 1 root root 0 Jun 6 10:25 file4
-rw-r--r-- 1 root root 0 Jun 6 10:25 file5
```

---

# Verification Checklist

Confirm karein ke aap ne yeh tamam tasks complete kar liye hain:

- [ ] `date` command run ki
- [ ] `uptime` command run ki
- [ ] `pwd` command run ki
- [ ] `/var/opt/images` create ki
- [ ] `/var/opt/projects` create ki
- [ ] `summary.txt` create ki
- [ ] `file1` create ki
- [ ] `file2` create ki
- [ ] `file3` create ki
- [ ] `file4` create ki
- [ ] `file5` create ki

---

# Review Questions

1. `date` command kya display karti hai?
2. `uptime` command kya information deti hai?
3. `pwd` ka full form kya hai?
4. Absolute Path kya hota hai?
5. Relative Path kya hota hai?
6. `/var/opt/images` Absolute Path kyun hai?
7. `projects` Relative Path kyun hai?
8. `mkdir -p` option kya karta hai?
9. Empty file create karne ke liye kaunsi command use hoti hai?
10. Ek hi command se multiple files kaise create ki ja sakti hain?

---

# Challenge Task

Neeche diya gaya directory structure create karein:

```text
/var/opt/linuxlab
├── docs
├── scripts
└── backups
```

### Commands

```bash
mkdir -p /var/opt/linuxlab/docs
mkdir -p /var/opt/linuxlab/scripts
mkdir -p /var/opt/linuxlab/backups
```

Verify:

```bash
ls -R /var/opt/linuxlab
```

---

# Lab Summary

Is lab mein aap ne seekha:

- Date aur time display karna
- System uptime check karna
- Filesystem mein apni current location identify karna
- Absolute aur Relative Paths ka difference
- Dono methods se directories create karna
- `touch` command se files create karna
- `ls` command se filesystem changes verify karna

Yeh Linux Administration ki bunyadi skills hain jo aap poore Bootcamp ke dauran istemal karenge.

---

# Mubarak Ho!

Aap ne Linux filesystem navigation, directories aur files management ki basic practice successfully complete kar li hai.

🐧 Happy Learning Linux!