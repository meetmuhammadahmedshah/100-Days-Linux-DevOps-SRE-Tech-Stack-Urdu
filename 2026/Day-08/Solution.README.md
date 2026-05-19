# Module 01 – Introduction to IT & Linux
## Roman Urdu Solution Guide (Day 08)
> Saturday 16th May, 2026

---

# Task 1 - Student Introduction & Goal Setting

## Sample Answer

1. Mera naam John Doe hai  
2. Meri background customer service aur basic computer usage mein hai  
3. Maine Linux training join ki taake IT aur Cloud Computing mein career shuru kar sakun  
4. Mera career goal Linux System Administrator ya DevOps Engineer banna hai  
5. Main aglay 10–12 hafton mein Linux administration, networking, virtualization aur cloud technologies seekhna chahta hoon

---

# Task 2 - Understanding the IT Ecosystem

## Answers

### Linux Real World mein kahan use hota hai?

Linux use hota hai:

- Uber aur Lyft servers mein
- AWS Cloud mein
- Google servers mein
- Android phones mein
- Banking systems mein
- Web hosting servers mein
- Cybersecurity systems mein
- Supercomputers mein

---

### Linux Distro kya hota hai?

Linux Distro (Distribution) Linux ka aik version hota hai jisme shamil hotay hain:

- Linux Kernel
- Software packages
- Desktop environment
- Package manager
- System utilities

Examples:

- Ubuntu
- Rocky Linux
- Debian
- Fedora

---

### Virtualization kya hoti hai?

Virtualization aik process hai jisme aik physical machine par multiple virtual machines chalayi jaati hain. Iske liye hypervisor software use hota hai.

---

### Server kya hota hai?

Server aik computer hota hai jo doosray computers ya users ko network par services provide karta hai.

Examples:

- Web Server
- File Server
- Database Server
- Mail Server

---

### RHCSA kyun important hai?

RHCSA important hai kyunke yeh Linux administration skills ko validate karta hai aur students ko Linux jobs ke liye tayyar karta hai.

---

# Task 3 - Home Network Exploration

## Answers

### LAN kya hota hai?

LAN ka matlab Local Area Network hai. Yeh ghar, office ya building ke andar ka network hota hai.

---

### Gateway kya hota hai?

Gateway woh router hota hai jo local network ko internet se connect karta hai.

---

### Public IP aur Private IP mein difference

| Public IP | Private IP |
|------------|------------|
| Internet par visible hoti hai | Local network ke andar use hoti hai |
| ISP assign karta hai | Router assign karta hai |
| Duniya mein unique hoti hai | Bohat homes mein repeat hoti hai |

---

# Task 4 - Router ke Server-Like Functions

| Service | Purpose |
|----------|----------|
| DHCP | Devices ko automatically IP deta hai |
| DNS | Domain names ko IP addresses mein convert karta hai |
| NAT | Multiple devices ko aik public IP share karne deta hai |
| Firewall | Network ko unwanted traffic se protect karta hai |
| Port Forwarding | External access ke liye ports open karta hai |

---

# Task 5 - Data Center aur Server Concepts

## Answers

### Server kya hota hai?

Server aik machine hoti hai jo network par clients ko services provide karti hai.

---

### Server ki services

- Web hosting
- File sharing
- DNS
- DHCP
- Email
- Database hosting

---

### Data Center kya hota hai?

Data center aik facility hoti hai jahan servers, networking devices, storage systems aur cooling systems hotay hain.

---

### AWS aur Azure

AWS aur Azure cloud platforms hain jo duniya bhar ke data centers use karte hain cloud services provide karne ke liye.

---

# Task 6 - Server vs Laptop Comparison

| Feature | Laptop/Desktop | Server |
|---------|-----------------|--------|
| Purpose | Personal use | Multiple users ko serve karta hai |
| Uptime | Limited | 24/7 operation |
| Hardware | Consumer-grade | Enterprise-grade |
| Storage | Kam capacity | Zyada capacity |
| Reliability | Moderate | Bohat zyada reliable |

---

# Task 7 - Server Hardware Identification

| Component | Purpose |
|------------|----------|
| CPU | Instructions process karta hai |
| RAM | Temporary memory |
| Disk | Permanent storage |
| RAID | Disk redundancy aur performance |
| NIC | Network connectivity |
| GPU | Graphics processing |
| iDRAC | Remote server management |

---

### RAID kyun important hai?

RAID provide karta hai:

- Data redundancy
- Better performance
- Fault tolerance
- Disk failure protection

---

# Task 8 - Simplified Linux Boot Process

## Boot Sequence

1. BIOS hardware initialize karta hai  
2. POST hardware check karta hai  
3. Boot Loader operating system load karta hai  
4. Kernel hardware aur services initialize karta hai  
5. Operating System user environment start karta hai

---

### Bonus Answer

Ji haan, GRUB menu boot ke waqt appear hota hai aur operating systems select karne deta hai.

---

# Task 9 - Linux History

## Answers

### UNIX

UNIX 1969 mein Bell Labs mein create hua tha aur aaj kay jadeed (modern) operating systems ko isnay rasta dikhaaya hai (inspird by).

---

### Linus Torvalds

Linus Torvalds ne 1991 mein Linux Kernel create kiya.

---

### GNU Project

GNU Project ne free software tools provide kiye jo Linux ke saath use hotay hain.

---

### Linux Kernel

Kernel Linux ka core part hota hai jo hardware ke saath communicate karta hai.

---

### Linux revolutionary kyun tha?

Linux revolutionary (inqalaabi) tha kyunke yeh:

- Open source tha (paysay kharch kiyeah baghair istimaal)
- Free tha
- Portable tha
- Community (anjuman) driven tha 

---

### UNIX ko C language mein rewrite karna kyun important tha?

C language mein rewrite (phir sey likhna) karne se UNIX different hardware par run kar saka.

---

# Task 10 - Linux Distribution Research

## Lightweight Distros

| Distro | Lightweight? |
|---------|--------------|
| Red Hat | Nahin |
| Rocky Linux | Moderate |
| Ubuntu | Moderate |
| Debian | Haan |
| Fedora | Moderate |
| SUSE | Moderate |

---

# Task 11 - Linux Shell Exploration

## Commands

```bash
cat /etc/shells
echo $SHELL
ps $$
date
whereis date
```

---

## Answers

### Shell kya hota hai?

Shell aik command-line interpreter hota hai jo user ko operating system ke saath interact karne deta hai.

---

### Aap kaunsa shell use kar rahe hain?

Usually:

```bash
/bin/bash
```

---

### `ps $$` kya display karta hai?

Yeh current shell session ka Process ID (PID) show karta hai.

---

# Task 12 - Basic Linux Commands

## Commands aur Meanings

| Command | Purpose |
|---------|----------|
| uname -a | Complete system information show karta hai |
| uname -r | Kernel version show karta hai |
| lscpu | CPU information display karta hai |
| free -m | RAM usage show karta hai |
| df -h | Disk space display karta hai |
| ip a | Network interfaces show karta hai |
| pwd | Current directory show karta hai |

---

# Task 13 - Linux Help Commands

## Commands

```bash
uptime --help
man date
```

---

## Answers

### `man` command kya karta hai?

Yeh Linux commands ki manual/help page show karta hai.

---

### Help systems kyun important hain?

Yeh administrators ko commands seekhne aur troubleshooting mein madad dete hain.

---

# Task 14 - Keyboard Shortcut Practice

| Shortcut | Function |
|----------|-----------|
| Ctrl + C | Process interrupt karta hai |
| Ctrl + D | Shell exit karta hai |
| Ctrl + L | Screen clear karta hai |
| Ctrl + U | Current line clear karta hai |
| Ctrl + Z | Process stop karta hai |
| Tab | Command auto complete karta hai |

---

# Task 15 - Provisioning vs Configuration

## Answers

### Provisioning kya hota hai?

Provisioning ka matlab machine create aur prepare karna hota hai jisme CPU, RAM, Disk aur Operating System setup hota hai.

---

### Configuration kya hoti hai?

Configuration ka matlab machine ki settings customize karna hota hai.

---

### Provisioning ki example

Rocky Linux ke saath Virtual Machine create karna.

---

### Configuration ki example

Static IP address ya firewall rules configure karna.

---

## Reboot, Shutdown aur Poweroff mein difference

| Command | Meaning |
|----------|----------|
| Reboot | Machine restart karta hai |
| Shutdown | Operating system safely stop karta hai |
| Poweroff | Machine completely band karta hai |

---

# Task 16 - Virtualization Concepts

## Answers

### Virtualization kya hoti hai?

Virtualization aik physical machine par multiple virtual machines chalane ki technology hai.

---

### Companies virtualization kyun use karti hain?

- Better hardware utilization
- Cost savings
- Scalability
- Isolation
- Easy management

---

### Type 1 aur Type 2 Hypervisors

| Type 1 | Type 2 |
|---------|--------|
| Direct hardware par run karta hai | Operating system ke upar run karta hai |
| Faster hota hai | Thora slower hota hai |
| Enterprise use | Desktop/lab use |

Examples:

- Type 1: VMware ESXi, Xen
- Type 2: VirtualBox

---

### VirtualBox kyun use karte hain?

VirtualBox students ko apni machine par Linux virtual machines create aur manage karne deta hai.

---

### Rocky Linux ya Red Hat kyun use karte hain?

Yeh enterprise Linux distributions hain jo production environments mein widely use hoti hain.

---

# Task 17 - Final Reflection

## Sample Reflection

Module 01 mein maine Linux, servers, virtualization, networking aur Linux boot process ke bare mein seekha. Sabse interesting topic virtualization tha kyunke isse aik machine par multiple systems chal sakte hain. Linux commands shuru mein mushkil lag rahi thi lekin practice se understanding improve hui. Main future mein Linux administration aur networking skills aur improve karna chahta hoon.

---