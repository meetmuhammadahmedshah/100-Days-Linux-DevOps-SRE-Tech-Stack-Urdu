# Practice Lab — Linux Inodes Ko Samajhna
> NIT Academy Linux Practice Lab  
> Topic: Inodes, Metadata aur Directory Structure

---

# Table of Contents

| Task | Title |
|------|--------|
| 1 | [Checking Inodes with `ls -li`](#task-1---checking-inodes-with-ls--li) |
| 2 | [Understanding Directory Metadata with `ls -ld`](#task-2---understanding-directory-metadata-with-ls--ld) |
| 3 | [Comparing `ls -l` vs `ls -ld`](#task-3---comparing-ls--l-vs-ls--ld) |
| 4 | [Checking Filesystem Inode Usage](#task-4---checking-filesystem-inode-usage) |
| 5 | [Creating Files and Watching Inodes Change](#task-5---creating-files-and-watching-inodes-change) |
| 6 | [Important Concepts Explained](#task-6---important-concepts-explained) |

---

# Introduction

Linux filesystem do cheezon ko alag rakhta hai:

| Component | Kya Store Karta Hai |
|---|---|
| **Inode** | File ka metadata |
| **Data Blocks** | File ka asal content |

---

## Simple Explanation

Isko aise samjhein:

| Real Life Example | Linux Equivalent |
|---|---|
| Library catalog card | Inode |
| Kitab ke asal pages | Data blocks |

Catalog card batata hai:

- kitab ka owner kaun hai
- size kitna hai
- location kya hai
- timestamps
- permissions

Lekin kitab ka asal text alag jagah store hota hai.

---

# In Linux Har File Aur Directory Ka Ek Inode Hota Hai

Inode ek special data structure hai jo store karta hai:

- File permissions
- Owner
- Group
- File size
- Timestamps
- Data blocks ke pointers

> ⚠️ Important:
>
> Inode filename ko store NAHI karta.

---

Filename directory entry ke andar hota hai jo inode number ki taraf point karta hai.

Example:

| Filename | Inode |
|---|---|
| report.txt | 3470012 |

Directory mapping:

```text
report.txt → inode 3470012
```

Phir Linux inode `3470012` ko read karta hai jo actual data blocks ki taraf point karta hai.

---

# Practice Task

Run karein:

```bash
echo "hello" > file1
```

Linux create karta hai:

## Directory Entry

| Filename | Inode |
|---|---|
| file1 | 5001 |

---

## Inode 5001

Ye information store karta hai:

```text
Owner: root
Permissions: rw-r--r--
Size: 6 bytes
Data block pointer: 9021
```

---

## Data Block 9021

Isme asal content hota hai:

```text
hello
```

Agar aapko yeh samajh aa gaya to aap inode ka concept achi tarah samajh gaye.

Ab hum commands run karke practice karte hain.

---

# Task 1 - Checking Inodes with `ls -li`

Run karein:

```bash
ls -li /var
```

Example Output:

```bash
3470012 drwxr-xr-x. 20 root root 4096 May 20 10:00 log
3470013 drwxr-xr-x.  2 root root 4096 May 20 10:00 tmp
3470014 drwxr-xr-x.  5 root root 4096 May 20 10:00 spool
```

---

## Explanation

| Field | Meaning |
|---|---|
| 3470012 | Inode number |
| d | Directory |
| rwxr-xr-x | Permissions |
| root | Owner |
| root | Group |
| 4096 | Size |
| log | Filename |

---

## Key Learning

Linux pehle directory contents ko read karta hai:

```bash
cd /var
ls -l
```

Directory ke andar yeh mappings hoti hain:

| Filename | Inode |
|---|---|
| log | 3470012 |
| tmp | 3470013 |
| spool | 3470014 |

Phir Linux inode number use karke metadata aur data blocks ko locate karta hai.

---

# Task 2 - Understanding Directory Metadata with `ls -ld`

Run karein:

```bash
ls -ld /
```

Example Output:

```bash
dr-xr-xr-x. 22 root root 287 Jul 28 01:23 /
```

---

# "287" Ka Matlab Kya Hai?

Iska matlab hai:

```text
'/' root directory ko apni filenames aur inode mappings store karne ke liye 287 bytes ki zarurat hai.
```

Ye cheezon ka matlab NAHI hai:

- `/` ke andar tamam files ka total size
- filesystem size
- used disk space

---

# Simple Explanation

Directory ko ek:

📒 **Phone Book**

ki tarah samjhein.

Directory sirf store karti hai:

- filenames
- inode numbers

Example:

| Filename | Inode |
|---|---|
| etc | 1200 |
| var | 1201 |
| home | 1202 |

Actual data disk par kisi aur jagah hota hai.

---

# Important Clarification

Linux filesystems mukhtalif block sizes use karte hain:

- 1 KB
- 2 KB
- 4 KB
- ya kabhi isse zyada

Block size check karne ke liye:

```bash
stat -f /
```

ya:

```bash
dumpe2fs /dev/sdaX | grep "Block size"
```

---

# Better Explanation

Value:

```text
287
```

sirf yeh batati hai:

> Directory metadata is waqt 287 bytes occupy kar raha hai.

Jaise jaise files/directories add hongi, directory ka size bhi grow karega.

---

# Task 3 - Comparing `ls -l` vs `ls -ld`

## Command 1

```bash
ls -l /
```

Ye show karta hai:

✅ `/` ke andar ki contents ka metadata

---

## Command 2

```bash
ls -ld /
```

Ye show karta hai:

✅ `/` directory ka apna metadata

---

## Command 3

```bash
ls -li /
```

Ye show karta hai:

✅ inode numbers + metadata

---

## Command 4

```bash
ls -ild /
```

Ye show karta hai:

✅ `/` ka inode number

---

# Task 4 - Checking Filesystem Inode Usage

Run karein:

```bash
df -i
```

Example:

```bash
Filesystem      Inodes  IUsed   IFree IUse% Mounted on
/dev/sda1      655360 655360       0  100% /
```

---

# INTERVIEW QUESTION

Hum new files/directories create kyun nahi kar pa rahe jabke disk space available hai?

Run karein:

```bash
df -h
```

Example:

```bash
20G available
```

Phir bhi files create nahi ho rahi.

Kyun?

❌ Kyunki saare inodes use ho chuke hain.

---

# Very Important Concept

Filesystem mein do resources hote hain:

| Resource | Purpose |
|---|---|
| Disk blocks | Actual file data |
| Inodes | Metadata |

Aapko dono chahiye:

- ✅ Free blocks
- ✅ Free inodes

---

# Example

Agar aap:

- 5 million choti log files create karein
- har file sirf 1 byte ki ho

Toh:

- Disk space bahut kam use hogi
- Lekin millions of inodes consume ho jayenge

Eventually:

```bash
No space left on device
```

Aayega chahe:

```bash
df -h
```

free space show kare.

---

# Task 5 - Creating Files and Watching Inodes Change

Practice directory create karein:

```bash
mkdir ~/inode_lab
cd ~/inode_lab
```

Files create karein:

```bash
touch file1
touch file2
touch file3
```

Inode numbers check karein:

```bash
ls -li
```

Example:

```bash
3475001 file1
3475002 file2
3475003 file3
```

---

# Delete a File

```bash
rm file2
```

Nayi file create karein:

```bash
touch newfile
```

Phir check karein:

```bash
ls -li
```

Observe karein:

✅ Linux purane freed inode numbers dobara use kar sakta hai.

---

# Task 6 - Important Concepts Explained

# Kya Inodes Fixed Hote Hain?

✅ YES.

Jab filesystem create hota hai:

```bash
mkfs.ext4
```

Linux pehle hi fixed number of inodes allocate karta hai.

---

# Kyun?

Kyuki Linux ko inode tables ke liye pehle se space reserve karna hota hai.

---

# Kya Baad Mein Inodes Increase Kar Sakte Hain?

Aksar:

❌ Nahi (asaan tareeqe se nahi)

Aapko filesystem dobara create karna padta hai.

---

# Inodes Kahan Store Hote Hain?

Inodes special filesystem structures mein store hote hain jinhein kehte hain:

```text
inode tables
```

Ye formatting ke waqt create hote hain.

---

# Key Commands Summary

| Command | Purpose |
|---|---|
| `ls -li` | Inode numbers show karta hai |
| `ls -ld` | Directory metadata show karta hai |
| `df -i` | Inode usage show karta hai |
| `df -h` | Disk usage show karta hai |
| `stat file` | Detailed inode metadata |
| `find / -inum NUMBER` | Inode number se search |

---

# Final Summary

| Concept | Meaning |
|---|---|
| Inode | Metadata store karta hai |
| Filename | Directory entry mein hota hai |
| Directory | Names ko inode numbers se map karti hai |
| Disk Blocks | Actual data store karte hain |
| `df -h` | Block usage |
| `df -i` | Inode usage |
| No free inodes | Files create nahi hongi |
| `ls -ld /` | `/` directory ka metadata |

---

# Practice Questions

1. Inode kya store karta hai?
2. Kya inode filename store karta hai?
3. `ls -l /` aur `ls -ld /` mein kya difference hai?
4. System inodes se kyun khatam ho sakta hai?
5. Kaunsa command inode usage show karta hai?
6. `df -h` free space show kare phir bhi file create kyun nahi hoti?

---

# Final Summary

Run karein:

```bash
stat /etc/passwd
```

Identify karein:

- inode number
- timestamps
- permissions
- size
- owner

Apne findings LinkedIn par post karein.

---