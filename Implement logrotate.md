
This guide explains how to **automate log rotation** for your application using `logrotate`.  
Log rotation helps **manage disk space, compress old logs, and keep logs organized**.

---

## ✅ Step 1: Create a Logrotate Configuration File

**Explanation:**  
Create a custom configuration for your application logs.

```bash
sudo nano /etc/logrotate.d/myapp
```

Add the following content:

```
/var/log/myapp/*.log {
    daily
    rotate 7
    compress
    missingok
    notifempty
    create 0640 root root
}
```

> **Breakdown:**  
> - `daily` → Rotate logs every day  
> - `rotate 7` → Keep 7 rotated logs  
> - `compress` → Compress old logs  
> - `missingok` → Ignore if log file is missing  
> - `notifempty` → Skip empty logs  
> - `create 0640 root root` → Set permissions for new log files

---

## ✅ Step 2: Test Logrotate Configuration

**Explanation:**  
Test your configuration to ensure it works correctly without actually rotating logs.

```bash
sudo logrotate -d /etc/logrotate.d/myapp
```

---

## ✅ Step 3: Force a Log Rotation (Optional)

**Explanation:**  
Force log rotation immediately for testing purposes.

```bash
sudo logrotate -f /etc/logrotate.d/myapp
```

---

## ✅ Step 4: Verify Rotated Logs

**Explanation:**  
Check your log directory to ensure old logs are rotated and compressed.

```bash
ls -lh /var/log/myapp/
```

---

## 🎉 Logrotate Setup Complete!

Your application logs are now **automatically rotated, compressed, and managed**, saving disk space and keeping logs organized.
