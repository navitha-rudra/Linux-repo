
# Linux User Management and Sudo Permissions

## 1. Creating a New User

To create a new user in Linux:
```bash
sudo adduser username
```
This command creates the user and also sets up the home directory and basic configurations.

## 2. Granting Sudo Permissions

### Option 1: Add user to the `sudo` group (Recommended)
```bash
sudo usermod -aG sudo username
```

### Option 2: Use `visudo` for custom sudo rules
```bash
sudo visudo
```
Add a line like:
```bash
username ALL=(ALL) NOPASSWD:ALL
```
Or for limited command access:
```bash
username ALL=(ALL) /usr/bin/systemctl, /usr/bin/apt
```

## 3. Disable Password Login and Enable SSH Key Login

### Step 1: Copy the public SSH key to the remote server
From local machine:
```bash
ssh-copy-id username@server_ip
```
Or manually:
```bash
cat ~/.ssh/id_rsa.pub | ssh username@server_ip 'mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys'
```

### Step 2: Disable password authentication on the server

Edit the SSH config file:
```bash
sudo nano /etc/ssh/sshd_config
```
Update or add the following lines:
```bash
PasswordAuthentication no
PermitRootLogin no
```
Then restart SSH:
```bash
sudo systemctl restart sshd
```

## 4. Test SSH Key Login

From local machine:
```bash
ssh username@server_ip
```

If the setup is correct, you'll log in without being asked for a password.

---

✅ Now your Linux server is more secure with key-only login and the user has sudo access as needed.
