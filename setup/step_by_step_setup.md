# AIG 230 — Tool Installation Guide (Windows 11)

This document contains **only the steps required to install and verify the tools** needed for AIG 230 (Natural Language Processing).  
It reflects the **exact choices and constraints discussed during setup** and is written to minimize friction on Windows 11.

---

## 1. Visual Studio Code (VS Code)

**Purpose:** Primary code editor for Python, notebooks, Git, and terminal access.

### Installation
1. Download VS Code from: https://code.visualstudio.com
2. Run the installer.
3. During installation, ensure the following options are checked:
   - **Add to PATH**
   - **Add “Open with Code” action to Windows Explorer**
   - **Register Code as editor for supported file types**

### Required Extensions
After installation, open VS Code and install:
- **Python** (Microsoft)
- **Pylance** (Microsoft)
- **Jupyter** (Microsoft)

---

## 2. Python (Local Installation)

**Purpose:** Core programming language for the course.

### Version Requirement
- Install **Python 3.11.x** (e.g., 3.11.9)
- Do **not** install Python via Microsoft Store or Python Install Manager

### Installation
1. Download from: https://www.python.org/downloads/
2. Run the installer.
3. On the first screen:
   - ✔ Check **Add Python to PATH**
4. Complete installation.
5. On the final screen:
   - ✔ Click **Disable path length limit**

### Verify Installation
Open PowerShell or Command Prompt:
```powershell
python --version
pip --version
```

---

## 3. Git (Git for Windows)

**Purpose:** Version control and GitHub-based lab workflow.

### Install

1. Download Git from:  
   https://git-scm.com

2. Run the installer and use the following options:

   - **Default editor:** Visual Studio Code  
   - **PATH:** Git from the command line and also from 3rd-party software  
   - **HTTPS backend:** Use the OpenSSL library  
   - **Default branch name:** Override → `main`  
   - **SSH executable:** Use bundled OpenSSH  
   - **Line endings:** Checkout Windows-style, commit Unix-style  
   - **Terminal emulator:** Use MinTTY  
   - **Git pull behavior:** Fast-forward or merge  

3. Optional but recommended:
   - Disable daily update checks  
   - Do not create a desktop icon  

### Verify
Open PowerShell or Command Prompt and run:
```powershell
git --version
```

## 4. GitHub Account

**Purpose:** Required for accessing course repositories and submitting labs.

Create account

Create an account at:
https://github.com

Log in and verify your email address.

Configure Git identity

Run:
```powershell
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

## 5. Python Environment Management (venv)

**Purpose:** Isolate dependencies for each lab and assignment.

### Create a virtual environment

From your project folder, run:

```powershell
python -m venv aig230-env
```
### Activate the environment

PowerShell (recommended):

```powershell
aig230-env\Scripts\Activate.ps1
```

If blocked, run once:

```powershell
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

Then activate again:

```powershell
aig230-env\Scripts\Activate.ps1
```

Command Prompt:
```powershell
aig230-env\Scripts\activate
```
Bash
```bash
source aig230-env\Scripts\activate
```

## 6. Jupyter Notebook (Local)

**Purpose:** Run notebooks locally when not using Google Colab.

### Install

```powershell
pip install jupyter notebook
```
### Launch

```powershell
jupyter notebook
```

VS Code will also detect and run notebooks through the Jupyter extension.

## 7. Machine Learning & NLP Libraries

**Purpose:** Core libraries used throughout the course.

Install the following inside an active virtual environment:

```powershell
pip install -U pip
pip install numpy pandas matplotlib scikit-learn
pip install torch
pip install transformers
pip install spacy
```

## 8. Google Colab

**Purpose:** Cloud-based notebooks with free GPU access for in-class labs.

### Setup

Ensure you have a Google account.

Open: https://colab.research.google.com

### Verify you can:

- Create a new notebook

- Run Python code

- Install packages using pip

Google Colab will be used during labs even if local tools are installed.