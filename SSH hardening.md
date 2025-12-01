## ✅ Step 1: Backup SSH Configuration

**Explanation:**  
Before making changes, always backup the SSH configuration file.

```bash
sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.bak
```

---

## ✅ Step 2: Edit SSH Configuration

**Explanation:**  
Open the SSH configuration file to make security changes.

```bash
sudo nano /etc/ssh/sshd_config
```

**Recommended changes:**  
```
# Change default SSH port (e.g., 2222)
Port 2222

# Disable root login
PermitRootLogin no

# Disable password authentication (use keys instead)
PasswordAuthentication no
```

---

## ✅ Step 3: Restart SSH Service

**Explanation:**  
After editing, restart SSH to apply changes.

```bash
sudo systemctl restart sshd
```

---

## ✅ Step 4: Verify SSH Access

**Explanation:**  
Test the new configuration by connecting with the new port and key.

```bash
# Example: SSH to the server using the new port
ssh -i ~/.ssh/id_rsa -p 2222 user@server_ip
```

---

## ✅ Step 5: Optional Security Tips

- Use **SSH key pairs** instead of passwords.  
- Disable unused accounts from SSH access.  
- Enable **Fail2Ban** to block repeated failed login attempts.  

---

## 🎉 SSH Hardening Complete!

Your server’s SSH access is now **more secure**, protecting it from unauthorized login attempts.
