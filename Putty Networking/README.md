# Windows to Ubuntu File Transfer using PSCP

## 📌 Overview

This project demonstrates how to securely transfer files from a Windows system to an Ubuntu Linux machine running inside VirtualBox using PuTTY’s `pscp` command over SSH.

The goal is to understand:

* Secure file transfer using SSH
* Correct PSCP command syntax
* Common beginner mistakes and how to fix them
* Practical Linux file verification

---

## 🧰 Tools & Environment

* Windows 10 (Command Prompt)
* VirtualBox
* Ubuntu Linux
* PuTTY (PSCP utility)
* SSH (Port 22)

---

## 📂 Scenario

A file (`temp1.txt`) is transferred from a Windows machine to an Ubuntu VM using the `pscp` command.

---

## ✅ Correct PSCP Command

```bash
pscp -P 22 temp1.txt user@IP:/home/user/putty-demo/
```

### Important Notes

* `-P` (capital P) specifies the SSH port
* `-p` (lowercase) is incorrect for port usage and causes errors
* Linux commands and flags are case-sensitive

---

## ❌ Common Error Explained

**Error:**

```
More than one remote source not supported
```

**Cause:**
Using `-p` instead of `-P`, causing PSCP to misinterpret the command.

---

## 🔍 Verification on Ubuntu

```bash
ls /home/user/putty-demo/
cat /home/user/putty-demo/temp1.txt
```

---

## 🎯 Learning Outcome

* Understood SSH-based file transfer
* Learned strict command syntax discipline
* Gained hands-on Linux and networking experience
* Built a beginner but real-world IT workflow

---

## Screenshot
### Folder visible in Ubuntu

![img alt](https://github.com/manojk-network/Networking-Projects/blob/03036c0e51622d948dd1ace688a8838e265354a8/Putty%20Networking/Screenshots/Folder%20Visible%20in%20Ubuntu%20GUI.png)

### Ubuntu terminal SSH Service running

![img alt](
https://github.com/manojk-network/Networking-Projects/blob/03036c0e51622d948dd1ace688a8838e265354a8/Putty%20Networking/Screenshots/Folder%20Visible%20in%20Ubuntu%20GUI.png
)

### VirtualBox running Ubuntu
![img alt](
https://github.com/manojk-network/Networking-Projects/blob/03036c0e51622d948dd1ace688a8838e265354a8/Putty%20Networking/Screenshots/Folder%20Visible%20in%20Ubuntu%20GUI.png
)

### Windows CMD-Putty session
![img alt](
https://github.com/manojk-network/Networking-Projects/blob/03036c0e51622d948dd1ace688a8838e265354a8/Putty%20Networking/Screenshots/Folder%20Visible%20in%20Ubuntu%20GUI.png
)

## Youtube demo
https://youtu.be/ttZLlej_bV8
