# Linux Basics: Paths & Links

## Absolute Path vs Relative Path

### Absolute Path

* Full path starting from the root `/` directory.
* Always begins with `/`.
* Need to use full path from where ever the user is currently on
* **Example:**

  ```bash
  /home/navitha/documents/report.txt
  ```

### Relative Path

* Path from **current working directory**.
* Does **not** start with `/`.
* Can use `.` for current directory, and `..` for parent directory.
* **Example:**

  ```bash
  ./documents/report.txt
  ../logs/system.log
  ```


## Soft Link vs Hard Link

### Soft Link (Symbolic Link)

* A **shortcut** pointing to another file or directory. or copy of the original file
* Created with `ln -s`.
* If we modify the copied file, changed will be reflected in original file and vice versa
* Breaks if the original file is deleted.
* **Example:**

  ```bash
  ln -s /var/log/nginx/access.log access_log_link
  ```

### Hard Link

* A **second name** or copy for an existing file.
* Both names point to the same data (same inode).
* Created with `ln`.
* Only works for files, not directories.
* If we modify the copied file, changed will be reflected in original file and vice versa
* If the original file is deleted, the hard link doesn't works

* **Example:**

  ```bash
  ln original.txt hardlink.txt
  ```


