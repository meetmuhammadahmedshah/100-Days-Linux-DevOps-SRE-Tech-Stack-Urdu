# Visual Studio Code ko Windows, Chromebook, aur Mac par Download karna

> Wednesday 13th May, 2026 - DIN 5

---

# APNI MACHINE KE HISAB SE SIRF EK TASK KAREIN!

## Table of Contents (Fehrist)

| Task | Unwan (Title) |
|------|----------------|
| 1 | [Windows ke liye Installation](#task-1---windows-ke-liye-installation) |
| 2 | [Chrome Book ke liye Installation](#task-2---chrome-book-ke-liye-installation) |
| 3 | [Mac ke liye Installation](#task-3---mac-ke-liye-installation) |

---

# Task 1 - Windows ke liye Installation

## Step 1: VS Code ki Website Open Karein

Is link par jayein:

```plaintext
https://code.visualstudio.com/
```

Wahan aapko ek bada neela (blue) download button nazar aayega.

---

## Step 2: Windows ke liye VS Code Download Karein

Click karein:

```plaintext
Download for Windows
```

Is se `.exe` installer download ho jayega.

---

## Step 3: Installer ko Chalayein (Run)

1. Download ki hui file ko open karein  
2. `Next` par click karein  
3. License agreement ko `Accept` karein  
4. `Next` click karte rahein  
5. `Install` par click karein  

### Behtar Options

- Add to PATH  
- Create desktop icon  

---

## Step 4: VS Code ko Launch Karein

Installation ke baad:

1. `Finish` par click karein  
2. VS Code khud-ba-khud open ho jayega  

Aap search bhi kar sakte hain:

```plaintext
Start Menu → Visual Studio Code
```

---

# Task 2 - Chrome Book ke liye Installation

## Step 1: Chromebook par Linux Enable karein

1. `Settings` open karein  
2. `Developer` par jayein  
3. `Linux Development Environment` ko Turn ON karein  

---

## Step 2: Linux Terminal Open karein

Linux install hone ke baad:

1. `Launcher` open karein  
2. `Terminal` search karein  
3. Ise open karein  

---

## Step 3: VS Code Install karein

Ye commands ek ek karke chalayein:

```bash
sudo apt update
sudo apt install wget gpg -y

wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg

sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg

echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list

sudo apt update

sudo apt install code -y
```

---

## Step 4: VS Code ko Launch Karein

1. `Launcher` open karein  
2. Search karein:

```plaintext
Visual Studio Code
```

3. Ise open karein  

---

# Task 3 - Mac ke liye Installation

## Step 1: VS Code ki Website Open Karein

Visit karein:

```plaintext
https://code.visualstudio.com/download
```

Click karein:

```plaintext
Download for Mac
```

Chunyein (Choose):

- Apple Silicon  
YA  
- Intel Chip  

---

## Step 2: Download ki hui ZIP File ko Open karein

1. `Downloads` open karein  
2. ZIP file par double-click karein  
3. Visual Studio Code ko extract karein  

---

## Step 3: VS Code ko Applications mein Move karein

Ise drag karein:

```plaintext
Visual Studio Code.app
```

Is jagah par:

```plaintext
Applications
```

---

## Step 4: VS Code Open karein

1. `Applications` open karein  
2. `Visual Studio Code` par click karein  

Agar pucha jaye:

```plaintext
Click Open
```