## OvertheWire

# 🚩 OverTheWire: Bandit Writeups (30-31)

Detailed solutions for Git levels and shell escape challenges in Bandit.

---

## 🚩 Bandit Level 31 → 32
**Key Concept:** Bypassing `.gitignore` and validation through Git Hooks.

### 📝 Level Goal

The server requires us to submit a specific file to the remote repository to validate our identity and obtain the next credential.<br>

* **File:** key.txt  
* **Content:** May I come in?  
* **Branch:** master  

---

### 🛠️ Step-by-Step Solution

#### 1. Clone the Repository

First, we download the repository to our local machine. As a best practice, we create a directory where we will clone `repo`.

```bash
git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo
cd repo
```

---

#### 2. Create the Access File

We create the `key.txt` file with the exact content required by the challenge.

```bash
echo "May I come in?" > key.txt
```

---

#### 3. Force File Tracking (Bypass `.gitignore`)

When attempting to add the file with `git add`, the system will reject it because there is a rule in the `.gitignore` file that ignores all `.txt` files.  

To bypass this restriction, we use the `-f` (force) parameter.

```bash
git add -f key.txt
```

#### 4. Commit and Push

We perform a local commit and push the changes to the server.

> 🔐 **Note:** The password used for the `push` command is the same one used to clone the repository:  
> `f*5S2xb7bRyFmAvQYQGEqs*********y`

```bash
git commit -m "Adding access key"
git push origin master
```

---

### 🔑 Final Result

`3*9RfhqyAlVBEZpVb6LYStsh*******K`

Even if the `git push` command returns an error at the end, the password will appear in the terminal output due to the server configuration.

---
