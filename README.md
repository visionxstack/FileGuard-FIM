<div align="center">

# FileGuard-FIM

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python&logoColor=white)
![Security](https://img.shields.io/badge/Security-File%20Integrity%20Monitoring-green?style=for-the-badge&logo=shield&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

</div>

**FileGuard-FIM** (File Integrity Monitoring) is a professional-grade, real-time security tool designed to detect unauthorized file system changes instantly. It monitors critical directories and alerts you via **Desktop Notifications** and **Email Alerts** the moment a file is accessed, modified, created, or deleted.

---

## 🚀 Features
- **Real-Time Detection**: Monitors file events (Create, Modify, Delete, Move) with zero latency.
- **Dual Alerting**:
    - 🖥️ **Desktop Pop-ups**: Instant visual feedback on your screen.
    - 📧 **Email Notifications**: Detailed activity reports sent to your inbox.
- **Spam Prevention**: Configurable cooldown periods to prevent inbox flooding.
- **Detailed Logging**: Comprehensive audit trail saved to `logs/activity.log`.
- **Cross-Platform**: Works efficiently on Linux and Windows.

---

## ⚙️ Configuration

1.  **Open `config.json`** in the project folder.
2.  **Add Folders**: Update `"monitor_folders"` with the paths you want to protect.
3.  **Setup Email** (Crucial for Alerts):
    *   **Gmail Users**: You **MUST** use an **App Password**.
    *   Go to **Google Account** > **Security** > **2-Step Verification** > **App Passwords**.
    *   Generate a new password and paste it into `"email_password"`.
    *   Set `"sender_email"` to your Gmail address.

```json
{
    "monitor_folders": [
        "/home/user/Desktop/critical_files", (Your Folder path)
        "/var/www/html"
    ],
    "sender_email": "your_email@gmail.com",
    "email_password": "abcdefghijklmnop", 
    ...
}
```

---

## 🛠️ How to Use

### 1. Prerequisites
Ensure you have Python 3 installed. Linux users should use a virtual environment to manage dependencies cleanly.

### 2. Installation (One-Time Setup)
Open your terminal in the `FileGuard-FIM` directory and run:

```bash
# Create a virtual environment
python3 -m venv venv

# Activate the environment
source venv/bin/activate

# Install required libraries
pip install watchdog plyer
```

### 3. Running the Tool
To start monitoring, simply run:

```bash
# Ensure your virtual environment is active (you should see (venv) in your prompt)
python fileguard_fim.py
```

### 4. Running in Background (Linux)
To keep the tool running even after you close the terminal:

```bash
nohup python fileguard_fim.py > /dev/null 2>&1 &
```
*To stop it later, run `pkill -f fileguard_fim.py`.*

---

## 📝 Logs
All detected activities are recorded in `logs/activity.log` with precise timestamps:
```
2025-12-28 20:38:57 - File/Folder Created - /path/to/file.txt
2025-12-28 20:39:00 - File Modified - /path/to/file.txt
```
---

## 🛡️ Security Disclaimer
This tool is intended for defensive security monitoring. Protect your `config.json` file as it contains sensitivity email credentials (`chmod 600 config.json` is recommended).

---

## 📄 License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Author
**Vision KC**<br>
[GitHub](https://github.com/vision-dev1)<br>
[Portfolio](https://visionkc.com.np)

---
