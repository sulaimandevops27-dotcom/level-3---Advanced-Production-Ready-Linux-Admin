# ✅ Task 4: Configure Firewall Rules

This guide explains how to **configure firewall rules** using `ufw` (Uncomplicated Firewall) on Linux.  
A firewall protects your server by **allowing or blocking network traffic**.

---

## ✅ Step 1: Check Firewall Status

**Explanation:**  
Before making changes, see if the firewall is active.

```bash
sudo ufw status verbose
```

---

## ✅ Step 2: Enable the Firewall

**Explanation:**  
Enable `ufw` to start protecting your server.

```bash
sudo ufw enable
```

> You might see a warning if no rules exist yet. That’s fine; we’ll add rules next.

---

## ✅ Step 3: Allow SSH Access

**Explanation:**  
Always allow SSH before enabling the firewall to avoid being locked out.  
Replace `2222` with your custom SSH port if changed.

```bash
sudo ufw allow 2222/tcp
```

---

## ✅ Step 4: Allow Web Traffic

**Explanation:**  
Allow HTTP and HTTPS traffic for web servers.

```bash
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
```

---

## ✅ Step 5: Deny All Other Incoming Traffic

**Explanation:**  
By default, `ufw` blocks other incoming connections. You can check or set default policies.

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

---

## ✅ Step 6: Reload and Verify Rules

**Explanation:**  
Reload `ufw` to apply rules and verify.

```bash
sudo ufw reload
sudo ufw status verbose
```

---

## 🎉 Firewall Configuration Complete!

Your server is now **protected by a firewall**, allowing only authorized traffic.
