
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

* Use the `ls -l` command to check file permissions:

```bash
ls -l
```

**Example Output:**

```
-rw-r--r--. 1 navitha.r domain users 1563 Jun 25 12:47 sample.txt
```

* To View Directory Permission Itself:

Use `-d` flag:

```bash
ls -ld <directory-name>
```

---

## 🧱 Numeric (Octal) Representation

| Permission | Value |
|------------|-------|
| `r`        | 4     |
| `w`        | 2     |
| `x`        | 1     |

### Example:

`rwxr-xr--` = `7 5 4`

---

## 🛠️ Changing Permissions

- Use `chmod` to change permissions  
- Use `chown` to change owner/group  

### Using symbolic mode:

```bash
chmod u+w file.txt   # Add write to owner
chmod g+w file.txt   # Add write to group
chmod o+w file.txt   # Add write to others
chmod a+x script.sh  # Add execute to all
```

### Using numeric mode:

```bash
chmod 755 file.txt   # rwxr-xr-x
chmod 644 file.txt   # rw-r--r--
```

### Recursively (for folders and contents):

```bash
chmod -R g+w my-folder
```
