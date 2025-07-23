
# Linux File System Structure

The Linux file system is organized as a **single tree** starting from the root directory (`/`). Everything in Linux is under this root.

---

## 🌳 Top-Level Directories

| Directory | Description |
|-----------|-------------|
| `/`       | Root of the file system |
| `/bin`    | user binaries. All user specific linux commands related packages will be stored (e.g., `ls`, `cp`) |
| `/etc`    | System-wide configuration files |
| `/home`   | Home directories for users |
| `/root`   | Home directories for root user |
| `/lib`    | Essential shared libraries and kernel modules |
| `/media`  | Mount points for removable media (USB, CD-ROM) |
| `/mnt`    | Temporary mount points (e.g., for manual mounts) |
| `/opt`    | Optional or third-party software |
| `/proc`   | Virtual file system for process and kernel info |
| `/run`    | Temporary runtime files (since boot) |
| `/sbin`   | System binaries. For administrative commands (e.g., `reboot`, `shutdown`) |
| `/srv`    | Data for services (e.g., web, FTP) |
| `/sys`    | Virtual filesystem for kernel info and devices |
| `/tmp`    | Temporary files (cleared on reboot) |
| `/usr`    | User programs and data. Parent directory for sbin,bin,lib etc (secondary hierarchy) |
| `/var`    | Variable files (logs, spools, mail, etc.) |
| `/boot`   | Booting/starting/restarting (like `vmlinuz`, `initrd`) |
| `/dev`    | Device files (e.g., `/dev/sda`, `/dev/null`) |

---

## 🔍 Special Notes

- `/usr` is often used for **read-only** user applications and libraries. The data changes only on reboot or reinstall ore restart
- `/var` contains **variable data** like logs and mail. It stores run time data.
- `/proc` and `/sys` are **virtual file systems** that don't exist on disk but provide a way to interact with kernel and process data.
- `/etc` is the **brain of Linux**: almost all configuration lives here.
- `/usr/lib` contains the static libraries but `/var/lib` contains the run tine libraries
- If we install any 3rd party tool with apt, yum, or dnf, then linux uses its file system hierarchy. So these files will be stored in `/etc` not in the `/opt'
- if we install 3 rd party tol with zip or tar then those files will be in `/opt`

---

## 🏠 User-Specific Files

- Every user has a home directory under `/home/username`
- Root user has a special home at `/root`

---

## 📂 Sample Directory Tree

```
/
├── bin/
├── boot/
├── dev/
├── etc/
│   ├── hosts
│   └── ssh/
├── home/
│   └── user/
├── lib/
├── media/
├── opt/
├── proc/
├── root/
├── run/
├── sbin/
├── sys/
├── tmp/
├── usr/
│   ├── bin/
│   └── lib/
└── var/
    ├── log/
    └── mail/
```

---

## 📌 Summary

- The Linux file system is hierarchical and starts at `/`
- Everything — files, directories, devices — is a file
- Knowing what each directory is used for helps in system administration

## Easy Understanding

```
                Software / Tool / Package
                        |
        -------------------------------------
        |                                   |
     Binaries                           Libraries
        |                                   |
   -----------------                      /lib
   |               |
 Admin         Non-Admin
 (/sbin)         (/bin)
   |               |
   -----------------------------------------------
                        |
            User (Parent Directory)
                        |
                       /|\
       ---------------------------------------------
       |                      |                   |
   /usr/sbin             /usr/bin             /usr/lib
```


