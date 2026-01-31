![standard](https://github.com/user-attachments/assets/2be85dd7-4540-4105-80a6-db2976948eed)



# Discord Server Backup Tool

A Discord.js v15 bot that can fully back up and restore a Discord server, including structure, permissions, and emojis.

This project is focused on correctness, clean code structure, and predictable behavior.

---

## ✨ Features

- Slash command based
- Backup support:
  - Roles
  - Role permissions
  - Categories
  - Channels
  - Channel permission overwrites (including @everyone)
  - Custom emojis 
- Restore support:
  - Roles with correct permissions
  - Categories restored before channels
  - Channels restored in correct categories
  - Channel permission overwrites restored correctly
  - @everyone overwrites preserved
  - Emojis restored
- Server wipe command
- One-command startup (`npm start`)
- Discord.js v15 compatible

---

## 📁 Project Structure

```bash
backup-tool/
├── backups/     (backups saved here, do not delete)
│ 
│
├── src/
│ ├── commands/
│ │   ├── backup.js
│ │   ├── restore.js
│ │   └── wipe.js
│ │
│ ├── services/
│ │   ├── backupService.js
│ │   ├── restoreService.js
│ │   └── wipeService.js
│ │
│ ├── utils/
│ │   └── permissionUtils.js
│ │
│ ├── clearCommands.js
│ └── index.js
│
├── .env   (You need to create this yourself and enter the data)
└── package.json
```
---

## ⚙️ Requirements

- Node.js 18 or newer
- Discord bot with:
  - Administrator permission
  - Server Members intent enabled

---

## 📦 Installation
```
git clone https://github.com/ariqel/backup-tool.git 
cd backup-tool  
npm install  
```
Change the data in the .env with your data:
```
DISCORD_TOKEN=BOT_TOKEN_HERE
CLIENT_ID=APPLICATION_ID_HERE
GUILD_ID=SERVER_ID_HERE
```
---

## ▶️ Running the Bot

npm start

This will:
- Register slash commands
- Log the bot in
- Make commands available in your server

---

## 🧾 Slash Commands

/backup  
Creates a full backup of the server and saves it to `backup-tool/backups`

/restore  
Restores the server from the backup file. Usage: /restore "entire file name including extension"

/wipe  
Deletes all channels, categories, and roles (except @everyone)

---

## ⚠️ Important Notes

- Always back up before wiping a server
- The bot must have Administrator permissions
- Large servers may take time to restore due to Discord rate limits

---
