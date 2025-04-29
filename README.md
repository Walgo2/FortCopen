# 🛡️ FortCopen

FortCopen is a defensive application designed to protect Minecraft servers. I was a victim of the **Copenheimer** project, which motivated me to develop this tool that guards servers against similar group attacks and sends real-time alerts to **Discord**.

## 🚨 Why FortCopen?

After my server was targeted by a coordinated attack, I realized that typical Minecraft server protection wasn't enough. FortCopen was created as a response — a simple yet effective firewall companion that detects suspicious activity and notifies administrators instantly.

## ⚙️ How It Works

- **Monitors traffic on a selected port (e.g., 25565)** using the `scapy` library.
- Analyzes Minecraft handshake and login packets.
- Compares IP addresses with a whitelist.
- Automatically:
  - blocks unauthorized IPs via Windows Firewall (`netsh`),
  - sends alerts to Discord webhooks including IP and username.
- Comes with a **graphical interface (Tkinter GUI)** where you can:
  - manage the whitelist/blacklist,
  - add/remove Discord webhooks,
  - change the target port,
  - open firewall logs.

## 📁 Project Contents

- `FortCopen.py` – main application file.
- `env.txt` – configuration file for whitelist, webhooks, and port.
- `_internal/` – internal dependencies required for execution.
- `dogo.ico` – application icon.
- `.iss` file – installer script for Inno Setup.

## 🧪 Requirements

- Windows OS (with firewall logging enabled)
- Administrator privileges

## 🔧 Installation

The installer creates all required files, including `env.txt`. If `Npcap` is not installed, FortCopen will prompt to download it automatically.

## 📡 Discord Alerts

You can add one or more Discord webhook URLs via the GUI. When an unauthorized connection attempt is detected, FortCopen will send an alert with the IP address and player name.

---

💬 Feel free to open an issue or pull request if you have suggestions or questions.

