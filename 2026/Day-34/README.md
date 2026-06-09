# PRACTICE LAB
# Day 34 – Linux Mein Aliases Create, Manage aur Delete Karna
## June 10th, 2026

> Linux Administration aur Alias Management 

---

# Objective

Is lab ka maqsad yeh seekhna hai ke:

1. Alias kya hota hai.
2. Existing aliases kaise dekhe jate hain.
3. Temporary aliases kaise create ki jati hain.
4. Aliases ko commands ki shortcut ke tor par kaise use kiya jata hai.
5. Temporary aliases kaise remove ki jati hain.
6. Permanent aliases kaise create ki jati hain.
7. Permanent aliases ko verify kaise kiya jata hai.
8. Permanent aliases ko remove kaise kiya jata hai.
9. Linux Administration mein aliases productivity kaise improve karti hain.

---

# Table of Contents

| Task | Title |
|------|--------|
| 1 | Alias Kya Hota Hai? |
| 2 | Existing Aliases Dekhna |
| 3 | Temporary Alias Create Karna |
| 4 | Temporary Alias Use Karna |
| 5 | Temporary Alias Delete Karna |
| 6 | Permanent Alias Create Karna |
| 7 | Permanent Alias Verify Karna |
| 8 | Permanent Alias Remove Karna |
| 9 | Apne Khud Ke Admin Aliases Banana |
| 10 | Review Questions |
| 11 | Lab Summary |

---

# Introduction

## Alias Kya Hota Hai?

Alias kisi command ka doosra naam hota hai.

Aliases Linux Administrators ko allow karti hain:

- Shortcut commands banane ke liye
- Lambi commands ko simplify karne ke liye
- Productivity improve karne ke liye
- Typing mistakes kam karne ke liye
- Time bachane ke liye

Misal ke tor par:

Agar aap baar baar yeh command run karte hain:

~~~bash
ls -l /root
~~~

To aap iska alias bana sakte hain:

~~~bash
alias lh='ls -l /root'
~~~

Ab sirf:

~~~bash
lh
~~~

type karne se Linux yeh command run karega:

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
| alias_name | Shortcut naam |
| actual_command | Asal command jo execute hogi |

---

# Task 1 - Existing Aliases Dekhna

## Objective

System mein pehle se mojood aliases dekhna.

### Run

~~~bash
alias
~~~

### Questions

1. Kitni aliases display hui?
2. Kaunsi aliases pehle se mojood hain?
3. Linux default aliases kyun provide karta hai?

### Notes

Aksar Linux distributions mein yeh aliases hoti hain:

~~~bash
alias ll='ls -l'
alias la='ls -a'
alias l='ls -CF'
~~~

---

# Task 2 - Temporary Alias Create Karna

## Objective

Current session ke liye alias create karna.

### Run

~~~bash
alias lh='ls -l /root'
~~~

### Verify

~~~bash
alias
~~~

### Questions

1. Kya aap ko alias `lh` nazar aa raha hai?
2. Yeh alias kaunsi command execute karta hai?

---

# Task 3 - Temporary Alias Use Karna

## Objective

Naye alias ko use karna.

### Run

~~~bash
lh
~~~

### Expected Result

Directory:

~~~text
/root
~~~

ki listing display hogi.

### Questions

1. Kya alias successfully kaam kar raha hai?
2. Kya yeh poori command likhne se asaan tha?

---

# Task 4 - Multiple Temporary Aliases Create Karna

## Objective

Mukhtalif aliases create karne ki practice karna.

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

### Test Karein

~~~bash
mydate
myuser
myhost
myup
~~~

### Questions

1. Sab se useful alias kaunsi thi?
2. Aap apni daily work ke liye kaunsi alias create karenge?

---

# Task 5 - Temporary Alias Delete Karna

## Objective

Current session se alias remove karna.

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

1. Alias delete karne ke liye kaunsi command use hoti hai?
2. Alias delete hone ke baad kya hua?

---

# Temporary Aliases Ko Samajhna

## Important Note

Temporary aliases:

- Sirf current session tak rehti hain.
- Logout ke baad khatam ho jati hain.
- Terminal close karne par remove ho jati hain.
- System reboot ke baad remove ho jati hain.

---

# Task 6 - Permanent Alias Create Karna

## Objective

Aisi alias create karna jo logout aur reboot ke baad bhi available rahe.

### Step 1 - .bashrc File Open Karein

### Run

~~~bash
vi ~/.bashrc
~~~

YA

~~~bash
nano ~/.bashrc
~~~

---

### Step 2 - Alias Add Karein

File ke end mein yeh line add karein:

~~~bash
alias llroot='ls -l /root'
~~~

Save karke exit karein.

---

### Step 3 - .bashrc Reload Karein

### Run

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

### Questions

1. Hum ne `.bashrc` file kyun modify ki?
2. `source ~/.bashrc` kyun run kiya?

---

# Task 7 - Permanent Alias Verify Karna

## Objective

Verify karna ke alias next session mein bhi available hai.

### Run

~~~bash
exit
~~~

Dobarah login karein.

### Verify

~~~bash
alias
~~~

### Test

~~~bash
llroot
~~~

### Questions

1. Kya alias ab bhi available hai?
2. Isay permanent alias kyun kehte hain?

---

# Task 8 - Permanent Alias Remove Karna

## Objective

Permanent alias delete karna.

### Step 1 - .bashrc Open Karein

### Run

~~~bash
vi ~/.bashrc
~~~

YA

~~~bash
nano ~/.bashrc
~~~

---

### Step 2 - Alias Dhoondein

~~~bash
alias llroot='ls -l /root'
~~~

Is line ko delete kar dein.

---

### Step 3 - Configuration Reload Karein

### Run

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

1. Alias kyun disappear ho gayi?
2. Permanent aliases kis file mein store hoti hain?

---

# Task 9 - Apni Khud Ki Administrator Aliases Banana

## Objective

Aisi aliases create karna jo Linux Administrator daily use kar sakta hai.

### Examples

~~~bash
alias mylogs='ls -l /var/log'
alias mynet='ip addr'
alias mydisk='df -h'
alias mymem='free -h'
alias myproc='ps -ef'
~~~

### Test Karein

~~~bash
mylogs
mynet
mydisk
mymem
myproc
~~~

### Discussion

Kaunsi aliases aap ki daily work ko asaan bana sakti hain?

---

# Review Questions

1. Alias kya hota hai?
2. Aliases kyun useful hoti hain?
3. Tamam aliases dekhne ki command kya hai?
4. Alias create karne ki command kya hai?
5. Alias delete karne ki command kya hai?
6. Temporary aur Permanent Alias mein kya difference hai?
7. Permanent aliases kis file mein store hoti hain?
8. `source ~/.bashrc` kya karta hai?
9. Linux Administrators aliases kyun use karte hain?
10. Aisi teen aliases likhein jo aap rozana use karenge.

---

# Lab Summary

Is lab mein aap ne seekha:

- Existing aliases dekhna
- Temporary aliases create karna
- Aliases use karna
- Temporary aliases delete karna
- Permanent aliases create karna
- `.bashrc` file mein aliases save karna
- Bash configuration reload karna
- Permanent aliases remove karna
- Productivity improve karna

---

# Important Lesson

Aliases Linux Administrator ki productivity bohat improve karti hain.

Misal ke tor par:

~~~bash
ls -l /var/log
~~~

baar baar type karne ke bajaye:

~~~bash
alias logs='ls -l /var/log'
~~~

banayein aur sirf:

~~~bash
logs
~~~

run karein.

Yeh:

- Time bachata hai
- Typing errors kam karta hai
- Commands yaad rakhna asaan banata hai

---

# End of Lab

🐧 Happy Learning Linux Administration!