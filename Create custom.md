## ✅ Step 1: Create the Service File

**Explanation:**  
A systemd service file defines how your application runs. It tells Linux **what to run, when, and how to restart it**.

```bash
sudo nano /etc/systemd/system/myapp.service
```

Add the following content:

```ini
[Unit]
Description=My Custom Application
After=network.target

[Service]
Type=simple
ExecStart=/usr/local/bin/myapp.sh
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

---
