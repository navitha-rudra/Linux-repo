# Linux File Permissions

Linux uses a permission system to control who can read, write, or execute files and directories.

---

## 👤 Types of Users

1. **Owner (u)** – The user who owns the file
2. **Group (g)** – Users in the same group
3. **Others (o)** – Everyone else

---

## 🔐 Types of Permissions

| Symbol | Meaning        |
|--------|----------------|
| `r`    | Read           |
| `w`    | Write          |
| `x`    | Execute        |

---

## 📄 Viewing Permissions

Use the `ls -l` command to check the file permissions:

```bash
ls -l

**Example:**

-rw-r--r--. 1 navitha.r domain users 1563 Jun 25 12:47 sample.txt

To View Directory Permission

```bash
ls -ld <directory-name>

## 📄 Numeric (Octal) Representation

| Symbol | Meaning        |
|--------|----------------|
| `r`    | Read           |
| `w`    | Write          |
| `x`    | Execute        |

