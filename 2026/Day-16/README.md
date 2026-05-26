# PRACTICE LAB - PROJECT 101
## Introduction
> May 24th, 2026

Yeh project un tamam cheezon par mabni hai jo aap ne ab tak seekhi hain. Zaroori hai ke aap tamam STEPS ko carefully follow karein.

---

# Table of Contents

| Task | Title |
|------|--------|
| 1 | [Reading Exercise - IT Journey ki Shuruaat](#task-1---reading-exercise---it-journey-ki-shuruaat) |
| 2 | [Reading Exercise - Local Repository Samajhna](#task-2---reading-exercise---local-repository-samajhna) |
| 3 | [Reading Exercise - Remote Repository Kya Hai](#task-3---reading-exercise---remote-repository-kya-hai) |
| 4 | [Reading Exercise - GIT Architecture](#task-4---reading-exercise---git-architecture) |
| 5 | [Operational Excellence using GIT](#task-5---operational-excellence-using-git) |

---

# Task 1 - Reading Exercise - IT Journey ki Shuruaat

## NOTE: Do (2) Important Cheezein Samajhna Zaroori Hai

---

## (1) Browser Kya Hota Hai?

Web Browser ek software application hoti hai jo aapke computer, phone ya tablet par install hoti hai aur internet tak pohanchne ke liye ek window ka kaam karti hai.

Iska primary kaam World Wide Web se information fetch karna aur usko aapki screen par display karna hota hai.

---

## Browsers ki Examples

- Google Chrome
- Microsoft Edge
- Mozilla Firefox
- Safari

---

## (2) File Folder Kya Hota Hai?

Windows mein Folder (Directory) ek virtual container hota hai jo files ko organize aur store karne ke liye use hota hai.

Bilkul office ke physical folders ki tarah, digital folders khud data contain nahi karte, balke yeh files ko organize karte hain.

Examples:

- Documents
- Images
- Videos
- Music
- Dusre folders

---

## Subfolder Kya Hota Hai?

Agar ek folder kisi dusre folder ke andar ho to usay kehte hain:

```text
Subfolder
```

---

## Windows File Path Example

Windows file path use karta hai taake exact location trace ki ja sake jahan file store hai.

Example:

```text
C:\Users\Nadeem\Documents\NIT_Academy\Lesson1.txt
```

---

## Questions

1. Kya ab aapko Browser ka concept clear hai?
2. Kya ab aapko Windows Laptop par File Folder ka concept clear hai?

---

# Task 2 - Reading Exercise - Local Repository Samajhna

Jab aap apne laptop par kaam kar rahe hote hain to usay kehte hain:

```text
LocalHost
```

"Local" ka matlab hai woh Laptop ya Computer jo aap use kar rahe hain.

Jab aap apne Local Host par ek file folder (directory) create karte hain to aap ek:

```text
Local Repository (Repo)
```

create kar rahe hote hain.

---

## Local Repository Kya Hota Hai?

Local Repository ek private storage space (directory) hoti hai jo developer ke apne computer par hoti hai jahan Git project files ki complete history track aur save karta hai.

Jab aap:

- Changes karte hain
- Code add karte hain
- Files save karte hain
- Commits create karte hain

to yeh tamam kaam Local Repository ke andar hota hai.

---

## Important Note

Local Repository:

- Aapke apne computer par hoti hai
- Internet ke baghair bhi kaam karti hai
- File history track karti hai
- Local version control provide karti hai

---

## Question

Apne alfaaz mein explain karein:

```text
Local Repository kya hoti hai?
```

---

# Task 3 - Reading Exercise - Remote Repository Kya Hai

Remote Repository ek central archive hoti hai jo cloud mein store hoti hai.

Examples:

- GitHub
- GitLab
- Bitbucket

---

## Remote Repository ka Purpose

Jab developer apne kaam se satisfied hota hai to woh apni files aur commits ko:

```text
Push (Upload)
```

karta hai cloud par.

Is se team members:

- Code dekh sakte hain
- Code download kar sakte hain
- Code edit kar sakte hain
- Collaboration kar sakte hain

---

## Question

Difference explain karein:

```text
Local Repository vs Remote Repository
```

---

# Task 4 - Reading Exercise - GIT Architecture

Neeche diya gaya diagram explain karta hai ke Local Repository modern software development workflow mein kaise fit hoti hai.

Yeh bhi show karta hai ke data kaise flow karta hai:

- Developer Machine
- Git
- Remote Cloud Repository

ke darmiyan.

---

<img src="../../.github/assets/2_how git works.jpg" width="350">

---

# Teen (3) Important Cheezein Samajhna Zaroori Hai

---

## 1. Complete Independence

Kyunke Local Repository student ki apni machine par hoti hai, student:

- Changes track kar sakta hai
- Old versions dekh sakta hai
- Branches create kar sakta hai
- Internet ke baghair kaam kar sakta hai

---

## 2. Hidden `.git` Folder

Hidden `.git` folder asal database hota hai jo project history track karta hai.

Jab aap run karte hain:

```bash
git init
```

to Git ek hidden folder create karta hai:

```text
.git
```

repository ke andar.

---

## 3. Local vs Remote

### Local Save (Commit)

Commit sirf Local Repository mein snapshot save karta hai.

---

### Global Share (Push)

Push Local Repository se commits ko Remote Repository (GitHub Cloud) par bhejta hai.

Is se teammates aapka kaam access kar sakte hain.

---

# Questions

1. `git init` kya karta hai?
2. Hidden `.git` folder ka purpose kya hai?
3. `commit` aur `push` mein kya difference hai?
4. Git internet ke baghair kaise kaam karta hai?

---

# Task 5 - Operational Excellence using GIT

<img src="../../.github/assets/4_cartoon.jpg" width="500">

---

# Reflection Questions

1. Developers ke liye Git important kyun hai?
2. Teamwork ke liye GitHub useful kyun hai?
3. Developers ko version control kyun use karna chahiye?
4. Agar code properly backup na ho to kya ho sakta hai?
5. IT mein collaboration kyun important hai?

---

# Final Activity

## Ek Short Summary Likhein

Explain karein:

- Aapne Git ke bare mein kya seekha
- Local aur Remote Repository mein difference
- GitHub ka purpose
- Modern IT environments mein Git kyun important hai

---

# Final Submission

Apni markdown practice files ko GitHub Repository par push karein.

Verify karein:

- Files GitHub par nazar aa rahi hain
- Commits visible hain
- Repository properly connected hai

---