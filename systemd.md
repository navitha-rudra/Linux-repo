
# Linux systemd Basics

`systemd` is the init system and service manager used by most modern Linux distributions. It is responsible for **booting the system**, **managing services**, and **handling dependencies**.

---

## 🔧 1. Key Concepts

| Term     | Description                                                              |
|----------|--------------------------------------------------------------------------|
| Unit     | A configuration file defining how a service, target, or mount behaves   |
| Service  | A unit type that manages background processes                            |
| Target   | A group of units (similar to SysV runlevels)                            |
| Timer    | A unit that schedules tasks (like a cron replacement)                   |
| Journal  | The system log manager handled by `journald`                            |

---

---

## 📜 2. Common `journalctl` Commands

> `systemd` comes with its own log manager: `journald`

```bash
journalctl                     # Show all logs
journalctl -u nginx.service    # Logs for nginx service
journalctl -xe                 # Recent errors and detailed logs
journalctl -f                  # Follow logs in real-time (like tail -f)
journalctl -b                  # Logs from current boot
```

---

## 📜 3. Common `systemctl` Commands

> `systemctl` is the main command to manage services and units

### 🔹 Service Management

```bash
systemctl start nginx           # Start the service
systemctl stop nginx            # Stop the service
systemctl restart nginx         # Restart the service
systemctl reload nginx          # Reload config without stopping
```

### 🔹 Enable/Disable at Boot

```bash
systemctl enable nginx          # Start on boot
systemctl disable nginx         # Do not start on boot
systemctl is-enabled nginx      # Check if enabled
```

### 🔹 Check Status

```bash
systemctl status nginx          # View status and logs
systemctl is-active nginx       # Check if running
```

### 🔹 List Services

```bash
systemctl list-units --type=service      # Show active services
systemctl --failed                      # Show failed services
```

---
