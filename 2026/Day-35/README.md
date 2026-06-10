# PRACTICE LAB
# Day 35 – Linux Mein ping Command Ko Samajhna aur Use Karna
## June 11th, 2026

> NIT Academy ki Class Notes aur Ping Command Fundamentals par Mabni

---

# Objective

Is lab ka maqsad yeh seekhna hai:

1. Ping command kya hoti hai.
2. Ping command kaise kaam karti hai.
3. Network Administrators ping kyun use karte hain.
4. Network connectivity kaise test ki jati hai.
5. DNS resolution kaise test ki jati hai.
6. Internet access kaise verify ki jati hai.
7. Loopback Interface kaise test ki jati hai.
8. Specific packets kaise send kiye jate hain.
9. Packet interval kaise control kiya jata hai.
10. Ping statistics kaise display ki jati hain.

---

# Table of Contents

| Task | Title |
|------|--------|
| 1 | Ping Command Ko Samajhna |
| 2 | Internet Connectivity Test Karna |
| 3 | IP Address Ko Ping Karna |
| 4 | Running Ping Process Ko Stop Karna |
| 5 | Specific Number of Packets Send Karna |
| 6 | DNS Resolution Test Karna |
| 7 | Packet Interval Change Karna |
| 8 | Summary Statistics Display Karna |
| 9 | Loopback Interface Test Karna |
| 10 | Ping Ki Tamam Options Dekhna |
| 11 | Review Questions |
| 12 | Lab Summary |

---

# Introduction

## Ping Command Kya Hai?

Ping ka matlab hai:

```text
Packet InterNet Groper
```

Ping command use hoti hai:

- Network connectivity test karne ke liye
- Remote host reachable hai ya nahi check karne ke liye
- Network troubleshooting ke liye
- DNS resolution test karne ke liye
- Response time measure karne ke liye
- TCP/IP stack verify karne ke liye

Ping command:

```text
ICMP
```

protocol use karti hai.

ICMP ka matlab hai:

```text
Internet Control Message Protocol
```

---

# Task 1 - Ping Command Ko Samajhna

## Sawaal

Ping command ka purpose kya hai?

### Notes

Ping command remote device ko:

```text
ICMP Echo Request
```

bhejti hai.

Agar remote device reachable ho to woh:

```text
ICMP Echo Reply
```

wapas bhejti hai.

Successful reply ka matlab:

- Network connectivity maujood hai
- Destination reachable hai
- Routing sahi kaam kar rahi hai

---

# Task 2 - Internet Connectivity Test Karna

## Objective

Internet par kisi website ki connectivity test karna.

### Run

~~~bash
ping google.com
~~~

### Observation

Notice karein:

- Bytes
- Response time
- Sequence number
- Continuous replies

### Questions

1. Kya Google ne reply diya?
2. Output mein kya information nazar aayi?
3. Successful reply ka kya matlab hai?

---

# Task 3 - IP Address Ko Ping Karna

## Objective

Direct IP address ki connectivity test karna.

### Run

~~~bash
ping 8.8.8.8
~~~

### Notes

Google DNS Server:

```text
8.8.8.8
```

network testing ke liye commonly use hota hai.

### Questions

1. Kya IP reachable thi?
2. Is test se kya verify hua?
3. Hostname aur IP ko ping karne mein kya difference hai?

---

# Task 4 - Running Ping Process Ko Stop Karna

## Objective

Running process ko stop karna seekhna.

### Run

~~~bash
ping google.com
~~~

Kuch seconds ke liye chalne dein.

### Stop Karne Ke Liye

Press:

```text
Ctrl + C
```

### Observation

Summary display hogi:

- Packets Sent
- Packets Received
- Packet Loss
- Average Response Time

### Questions

1. Ctrl + C press karne ke baad kya hua?
2. Linux Administrator ke liye Ctrl + C kyun important hai?

---

# Task 5 - Specific Number of Packets Send Karna

## Objective

Packets ki specific quantity send karna.

### Run

~~~bash
ping -c 4 google.com
~~~

### Notes

Option:

~~~bash
-c
~~~

ka matlab hai:

```text
Count
```

### Observation

Sirf 4 packets send hongi.

### Questions

1. Kitni packets send hui?
2. Kitni packets receive hui?
3. Kya packet loss hua?

---

# Task 6 - DNS Resolution Test Karna

## Objective

DNS name resolution verify karna.

### Run

~~~bash
ping -c 1 google.com
~~~

### Observation

Notice karein:

```text
PING google.com (142.xxx.xxx.xxx)
```

IP address display hogi.

### Questions

1. Kaunsa IP address resolve hua?
2. Hostname ko IP mein kis service ne convert kiya?
3. Agar DNS fail ho jaye to kya hoga?

---

# Task 7 - Packet Interval Change Karna

## Objective

Packets ke darmiyan delay control karna.

### Run

~~~bash
ping -i 4 google.com
~~~

### Observation

Har 4 second baad packet send hogi.

---

### Run

~~~bash
ping -i 0.5 google.com
~~~

### Observation

Har aadha second baad packet send hogi.

### Questions

1. `-i` option kya karti hai?
2. Kis test ne zyada traffic generate ki?

---

# Task 8 - Summary Statistics Display Karna

## Objective

Sirf summary statistics display karna.

### Run

~~~bash
ping -c 10 -q google.com
~~~

### Notes

Option:

~~~bash
-q
~~~

ka matlab hai:

```text
Quiet Mode
```

### Observation

Individual replies display nahi hongi.

Sirf summary nazar aayegi.

### Questions

1. Kitni packets send hui?
2. Kitni packets receive hui?
3. Average response time kitni thi?

---

# Task 9 - Loopback Interface Test Karna

## Objective

Local TCP/IP stack verify karna.

---

## IPv4 Loopback Test

### Run

~~~bash
ping 127.0.0.1
~~~

---

## IPv6 Loopback Test

### Run

~~~bash
ping ::1
~~~

---

## Localhost Test

### Run

~~~bash
ping localhost
~~~

### Notes

Loopback Addresses:

| Protocol | Address |
|-----------|----------|
| IPv4 | 127.0.0.1 |
| IPv6 | ::1 |

### Questions

1. Kya tamam loopback tests successful thay?
2. Successful loopback test kya indicate karti hai?
3. Loopback testing kyun important hai?

---

# Task 10 - Ping Ki Tamam Options Dekhna

## Objective

Ping ki available options dekhna.

### Run

~~~bash
ping --help
~~~

### Observation

Review karein:

- -c
- -i
- -q
- aur doosri available options

### Questions

1. Kaunsi option packet count limit karti hai?
2. Kaunsi option interval change karti hai?
3. Kaunsi option summary statistics display karti hai?

---

# Review Questions

1. Ping ka full form kya hai?
2. Ping kis protocol ko use karti hai?
3. ICMP kya hai?
4. Network Administrators ping kyun use karte hain?
5. `ping google.com` kya test karta hai?
6. `ping 8.8.8.8` kya test karta hai?
7. `-c` option kya karti hai?
8. `-i` option kya karti hai?
9. `-q` option kya karti hai?
10. Ctrl + C kya karta hai?
11. IPv4 loopback address kya hai?
12. IPv6 loopback address kya hai?
13. Successful loopback test kya indicate karti hai?

---

# Lab Summary

Is lab mein aap ne seekha:

- Ping command use karna
- Network connectivity test karna
- Internet access verify karna
- DNS resolution test karna
- Specific packets send karna
- Packet intervals control karna
- Summary statistics display karna
- Loopback interface test karna
- Ping help options dekhna
- Running processes stop karna

---

# Important Lesson

Jab bhi network troubleshooting karein to hamesha is sequence mein testing karein:

~~~text
1. Ping 127.0.0.1
2. Ping localhost
3. Ping apna IP Address
4. Ping Default Gateway
5. Ping 8.8.8.8
6. Ping google.com
~~~

Yeh method aap ko exact point identify karne mein madad karta hai jahan connectivity problem maujood ho.

---

# Golden Rule

~~~text
Pehle Local Connectivity Test Karo,
Phir Gateway Test Karo,
Phir Internet Test Karo.
~~~

---

# End of Lab

🐧 Happy Learning Linux Networking!