# Linux Practice Lab – Users, Directories & Files
## Roman Urdu Linux Filesystem Practice
>Date 18th May, 2026 - Day 10

> Objective: Linux navigation, user management, directories create karna, files create karna aur filesystem visualization ki practice karna.

---

# Task 1 - Current Logged-in User Verify Karna

## Run:

```bash
whoami
```

## Questions

- Kaunsa username display ho raha hai?
- Kya aap root user ke tor par login hain ya normal user?

---

# Task 2 - /home Directory mein Navigate Karna

## Run:

```bash
cd /home
```

## Apni Current Location Verify Karein

Run:

```bash
pwd
```

Expected output:

```bash
/home
```

---

# Task 3 - /home ke Contents List Karna

## Run:

```bash
ls -l
```

## Observation

- Aap kya dekh rahe hain?
- Kya koi user directories pehle se create hui hui hain?

> NOTE: Fresh installation mein normally koi regular user directory nahi hoti jab tak users pehle create na kiye gaye hon.

---

# Task 4 - Do Users Create Karein

## Run:

```bash
useradd student
useradd Alice
```

## Verify Karein ke Users Create Ho Gaye

Run:

```bash
ls -l /home
```

Expected output mein ab yeh directories honi chahiye:

```bash
student
Alice
```

---

# Task 5 - Alice ki Home Directory mein Navigate Karein

## Run:

```bash
cd /home/Alice
```

## Apni Current Location Verify Karein

Run:

```bash
pwd
```

Expected output:

```bash
/home/Alice
```

---

# Task 6 - Alice Directory ke Contents Check Karein

## Run:

```bash
ls -l
```

## Observation

- Aap kya dekh rahe hain?
- Initially Alice ki home directory ke andar kuch bhi nahi hona chahiye.

---

# Task 7 - mkdir -p Use Karke Multiple Directories Create Karein

## Run: Aap ek hi command mein tamam directories create kar sakte hain!

```bash
mkdir -p projects docs images
```

## Directories Verify Karein

Run:

```bash
ls -l
```

Expected directories:

- projects
- docs
- images

---

# Task 8 - projects Directory mein Navigate Karein

## Run:

```bash
cd projects
```

## Contents Verify Karein

Run:

```bash
ls -l
```

YA

```bash
ll
```

## Observation

- Kya directory empty hai?

---

# Task 9 - Ek File Create Karein

## Run:

```bash
touch report.txt
```

## Verify Karein ke File Create Ho Gayi

Run:

```bash
ls -l
```

Expected output mein yeh file honi chahiye:

```bash
report.txt
```

---

# Task 10 - Ek Level Upar Jayein

## Run:

```bash
cd ..
```

## Apni Current Location Verify Karein

Run:

```bash
pwd
```

Expected output:

```bash
/home/Alice
```

---

# Task 11 - Dobarah Contents List Karein

## Run:

```bash
ls -l
```

## Observation

Ab aapko yeh directories nazar aani chahiye:

- projects
- docs
- images

---

# Task 12 - images Directory mein Navigate Karein

## Run:

```bash
cd images
```

## Directory Contents Verify Karein

Run:

```bash
ls -l
```

## Observation

- Kya images directory empty hai?

---

# Task 13 - Ek Image File Create Karein

## Run:

```bash
touch logo.png
```

## File Verify Karein

Run:

```bash
ls -l
```

Expected output:

```bash
logo.png
```

---

# Task 14 - Apni Home Directory mein Wapas Jayein

## Run:

```bash
cd
```

## Questions

- Kya aapko tilde symbol `~` nazar aa raha hai?
- Tilde `~` ka matlab hai ke aap apni home directory mein hain.

---

# Task 15 - User aur Current Directory Verify Karein

## Run:

```bash
whoami
pwd
```

## Questions

- Aap kis user ke tor par logged in hain?
- Aap iss waqt kis home directory mein hain?

---

# Task 16 - tree Package Install Karein

## Run:

```bash
dnf install -y tree
```

## Important Practice

Installation ke dauran:

Press karein:

```bash
Ctrl + C
```

## Observation

- Kya hua?
- Installation interrupt/stop ho jani chahiye.

---

# Task 17 - tree Dobarah Install Karein

## Run:

```bash
dnf install -y tree
```

## Is Martaba

Installation ko successfully complete hone dein.

---

# Task 18 - Linux Directory Hierarchy Display Karein

## Run:

```bash
tree -d /home
```

## Observation

- Kya aapko directory hierarchy nazar aa rahi hai?
- Kya aap identify kar sakte hain:
  - Alice
  - projects
  - docs
  - images

---

# Final Questions

1. `whoami` kya karta hai?
2. `pwd` kya display karta hai?
3. `cd ..` ka kya matlab hai?
4. Sirf `cd` kya karta hai?
5. `touch` command ka purpose kya hai?
6. `tree` useful kyun hai?
7. Tilde `~` kya represent karta hai?
8. `mkdir -p` kya karta hai?

---

# Final Reflection

Ek chhota paragraph likhein jisme explain karein:

- Aap ne iss lab se kya seekha
- Kaunsi command sabse useful lagi
- Kaunsi command mushkil lagi
- Linux filesystem navigation kyun important hai

---