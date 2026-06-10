# PRACTICE LAB
# Day 36 – Linux Command Line Par Date aur Time Change Karna
## June 12th, 2026

> Linux Date aur Time Administration Concepts par Mabni

---

# Objective

Is lab ka maqsad yeh seekhna hai:

1. Current date aur time display karna.
2. Linux system clock ko samajhna.
3. Date aur time ko mukhtalif formats mein display karna.
4. System date change karna.
5. System time change karna.
6. Date aur time dono ko ek saath change karna.
7. System clock mein ki gayi changes ko verify karna.
8. Samajhna ke ghalat date aur time kis tarah masail paida kar sakte hain.
9. Lab environment mein date aur time safely change karna.
10. Correct date aur time restore karna.

---

# Table of Contents

| Task | Title |
|------|--------|
| 1 | [Current Date aur Time Display Karna](#task-1---current-date-aur-time-display-karna) |
| 2 | [Date Ko Mukhtalif Formats Mein Display Karna](#task-2---date-ko-mukhtalif-formats-mein-display-karna) |
| 3 | [System Clock Ko Samajhna](#task-3---system-clock-ko-samajhna) |
| 4 | [System Date Change Karna](#task-4---system-date-change-karna) |
| 5 | [System Time Change Karna](#task-5---system-time-change-karna) |
| 6 | [Date aur Time Dono Ko Change Karna](#task-6---date-aur-time-dono-ko-change-karna) |
| 7 | [Changes Verify Karna](#task-7---changes-verify-karna) |
| 8 | [Correct Date aur Time Restore Karna](#task-8---correct-date-aur-time-restore-karna) |
| 9 | [Date aur Time Ki Importance Samajhna](#task-9---date-aur-time-ki-importance-samajhna) |
| 10 | [Review Questions](#review-questions) |
| 11 | [Lab Summary](#lab-summary) |
| 12 | [Important Lesson](#important-lesson) |
| 13 | [Golden Rule](#golden-rule) |

---

# Introduction

## Date aur Time Kyun Important Hain?

Linux date aur time ko use karta hai:

- System logging ke liye
- Security auditing ke liye
- User authentication ke liye
- Scheduled tasks (cron jobs) ke liye
- Backups ke liye
- Monitoring systems ke liye
- Databases ke liye
- SSL Certificates ke liye
- Network troubleshooting ke liye

Agar date aur time ghalat hon to kai services fail ho sakti hain ya unexpected behavior dikha sakti hain.

---

# Task 1 - Current Date aur Time Display Karna

## Objective

Current system date aur time dekhna.

### Run

~~~bash
date
~~~

### Example Output

~~~text
Fri Jun 12 10:45:22 AM CDT 2026
~~~

### Questions

1. Aaj ki tareekh kya hai?
2. Current time kya hai?
3. Kaunsa timezone display ho raha hai?

---

# Task 2 - Date Ko Mukhtalif Formats Mein Display Karna

## Objective

Date aur time ko custom formats mein display karna.

### Run

#### Sirf Date Display Karna

~~~bash
date +"%Y-%m-%d"
~~~

Example:

~~~text
2026-06-12
~~~

#### Sirf Time Display Karna

~~~bash
date +"%H:%M:%S"
~~~

Example:

~~~text
10:45:22
~~~

#### Full Date aur Time Display Karna

~~~bash
date +"%A %d %B %Y %H:%M:%S"
~~~

Example:

~~~text
Friday 12 June 2026 10:45:22
~~~

### Questions

1. Aap ko kaunsa format pasand aaya?
2. Mukhtalif date formats kyun useful ho sakte hain?

---

# Task 3 - System Clock Ko Samajhna

## Objective

System clock verify karna.

### Run

~~~bash
date
~~~

### Notes

Linux operating system ek internal system clock maintain karta hai.

Zyada tar applications isi clock par depend karti hain.

### Questions

1. Agar system clock ghalat ho jaye to kya ho sakta hai?
2. Kaunsi applications affect ho sakti hain?

---

# Task 4 - System Date Change Karna

## Objective

Sirf date change karna.

### Important Note

Aap ko root user hona zaroori hai.

### Run

~~~bash
date +%Y%m%d -s "20260615"
~~~

### Verify

~~~bash
date
~~~

### Questions

1. Kya date change hui?
2. Kya cheez unchanged rahi?

---

# Task 5 - System Time Change Karna

## Objective

Sirf time change karna.

### Run

~~~bash
date +%T -s "14:30:00"
~~~

### Verify

~~~bash
date
~~~

### Questions

1. Kya time change hua?
2. Kya date wahi rahi?

---

# Task 6 - Date aur Time Dono Ko Change Karna

## Objective

Date aur time dono ko ek command se modify karna.

### Run

~~~bash
date -s "2026-06-20 09:15:00"
~~~

### Verify

~~~bash
date
~~~

### Questions

1. Ab kaunsi date display ho rahi hai?
2. Ab kaunsa time display ho raha hai?

---

# Task 7 - Changes Verify Karna

## Objective

Confirm karna ke system clock successfully update hui hai.

### Run

~~~bash
date
~~~

### Additional Verification

~~~bash
uptime
~~~

### Questions

1. Kya displayed date configured date se match karti hai?
2. Kya displayed time configured time se match karta hai?

---

# Task 8 - Correct Date aur Time Restore Karna

## Objective

System ko correct date aur time par wapas lana.

### Method 1 - Manual Configuration

### Run

~~~bash
date -s "2026-06-12 10:45:00"
~~~

### Method 2 - Network Time Synchronization

### Run

~~~bash
timedatectl status
~~~

### Notes

Aksar Linux systems NTP ke zariye automatically time synchronize karte hain.

NTP servers dekhne ke liye:

~~~bash
systemctl status chronyd
~~~

Configuration file dekhne ke liye:

~~~bash
cat /etc/chrony.conf
~~~

Connected NTP sources dekhne ke liye:

~~~bash
chronyc sources -v
~~~

### Notes

- `^*` symbol current active NTP source ko show karta hai.
- `-v` option additional explanation provide karti hai.

### Run

~~~bash
timedatectl
~~~

### Questions

1. Kya NTP enabled hai?
2. Automatic time synchronization kyun useful hai?

---

# Task 9 - Date aur Time Ki Importance Samajhna

## Objective

Accurate system time ki importance samajhna.

### Run

~~~bash
ls -l /var/log
~~~

### Observation

Files ke timestamps ko observe karein.

### Discussion

Ghalat date aur time ki wajah se:

- Incorrect logs
- Backup failures
- Authentication failures
- Certificate errors
- Scheduled jobs wrong time par run hona

jaise masail paida ho sakte hain.

### Questions

1. Timestamps kyun important hain?
2. Linux Administrator accurate time ki fikr kyun karta hai?

---

# Real World Administrator Scenario

Ek user report karta hai:

~~~text
I cannot access the company website.
~~~

Investigation ke baad aap discover karte hain:

~~~text
SSL Certificate Not Yet Valid
~~~

Masla yeh tha:

~~~text
Server ki date incorrect thi.
~~~

Yeh demonstrate karta hai ke accurate system time kitni important hai.

---

# Review Questions

1. Current date aur time display karne ki command kya hai?
2. System time kyun important hai?
3. Sirf date change karne ki command kya hai?
4. Sirf time change karne ki command kya hai?
5. Date aur time dono change karne ki command kya hai?
6. System Administrator ko changes verify kyun karni chahiye?
7. NTP kya hai?
8. Timestamps kyun important hain?
9. Ghalat time ki wajah se kaun se masail paida ho sakte hain?
10. Current system time kaise verify karte hain?

---

# Lab Summary

Is lab mein aap ne seekha:

- Current date aur time display karna
- Custom date formats display karna
- Linux system clock ko samajhna
- System date change karna
- System time change karna
- Date aur time dono ko change karna
- Time changes verify karna
- Correct time restore karna
- NTP synchronization samajhna
- Date aur time related issues troubleshoot karna

---

# Important Lesson

Jab bhi Linux system troubleshoot karein to hamesha check karein:

~~~bash
date
timedatectl
uptime
~~~

Ghalat date aur time bohat se aise masail paida kar sakte hain jo pehli nazar mein clock se related nahi lagte.

---

# Golden Rule

~~~text
Complex Troubleshooting Shuru Karne Se Pehle Hamesha System Time Verify Karein
~~~

---

# End of Lab

🐧 Happy Learning Linux Administration!