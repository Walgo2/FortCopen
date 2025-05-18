# 🛡️ FortCopen

**FortCopen** is a defensive application designed to protect Minecraft servers. I was a victim of the **Copenheimer** project, which motivated me to develop this tool that guards servers against similar group attacks and sends real-time alerts to **Discord**.

## 🚨 Why FortCopen?

After my server was targeted by a coordinated attack, I realized that typical Minecraft server protection wasn't enough. FortCopen was created as a response — a simple yet effective firewall companion that detects suspicious activity and notifies administrators instantly.

## ⚙️ How It Works

- Monitors traffic on a selected port
- Analyzes Minecraft handshake and login packets.
- Compares IP addresses with a whitelist.
- Automatically:
  - blocks unauthorized IPs
  - sends alerts to Discord webhooks with IP and username,
  - creates server world backups on specific events.
- Comes with a graphical interface where you can:
  - manage the whitelist and blacklist,
  - add/remove Discord webhooks,
  - change the target port,
  - edit RCON configuration,
  - open firewall logs.

## 🔐 RCON Integration (NEW in 1.5)

FortCopen now includes advanced control over your server via **RCON**:

- Grant or revoke **OP** status for players.
- Switch players between **Spectator** and **Survival** modes.
- Trigger a server **reload** directly from the app.
- Set `rcon.port`, `rcon.password`, and `enable-rcon` from the GUI.
- The server automatically stops and restarts when RCON settings are changed.

## 💾 Automated Backups

FortCopen protects your world data with automatic backups:

- **Hourly** backup of world folders.
- Additional backups are triggered when:
  - an unauthorized player attempts to connect,
  - a player’s OP status or gamemode is changed,
  - the server is manually shut down via the app,
  - you trigger a manual backup through the GUI.

Backups are stored in timestamped folders inside the server directory.

## 🚀 Auto Server Startup

- If a `BAT_PATH` is set in `env.txt`, the Minecraft server will **automatically start** when FortCopen launches (if not already running).

## 🧪 Requirements

- Windows OS (with firewall logging enabled)
- Administrator privileges
- [Npcap](https://npcap.com/) installed (installer will prompt if missing)

## 📡 Discord Alerts

You can add one or more Discord webhook URLs via the GUI. When an unauthorized connection attempt is detected, FortCopen sends an alert with the IP address and Minecraft username.

---

💬 **Feel free to open an issue or pull request** if you have suggestions, need help, or want to contribute.
