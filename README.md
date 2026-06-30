# Minecraft Server Backups

This repository stores automated regular backups for the Minecraft server under the **Releases** tab.

---

## How to Restore / Recreate the Server

Because libraries, server software, and precompiled plugin binary `.jar` files are very large and can be easily downloaded, they are excluded from the backup archives to save storage space. Follow these steps to fully recreate the server from a backup:

### 1. Extract the Backup Archive
1. Go to the **Releases** page of this repository on GitHub.
2. Download the desired backup archive (`backup-YYYY-MM-DD_HH-MM-SS.tar.gz`).
3. Create a clean server directory and extract the archive there:
   ```bash
   mkdir mc-server && cd mc-server
   tar -xzvf path/to/backup-YYYY-MM-DD_HH-MM-SS.tar.gz
   ```

### 2. Download the Server Software (Paper)
The current server runs on **Minecraft 26.1.2** (Paper build `26.1.2-72-1a6b910`). 
Download the compatible Paper server jar:
```bash
wget -O server.jar https://fill-data.papermc.io/v1/objects/0555a0b0468a5198d8fb1a16e1f9e95c81a917a2dc8f2e09867b4044742f6401/paper-26.1.2-72.jar
```

### 3. Restore / Download Plugin Binaries
The backup includes all plugin configuration directories and custom Skript scripts, but excludes the executable `.jar` files. Download the correct versions of the following plugins and place them inside the `plugins/` directory:

| Plugin Name | Expected File Name | Purpose / Download Source |
|---|---|---|
| AdvancedPortals | `AdvancedPortals.jar` | Portals and teleporters |
| AuthMe | `AuthMe.jar` | Security & authentication |
| AxGraves | `AxGraves.jar` | Player death chests/graves |
| EssentialsX | `EssentialsX.jar` | Core commands, spawn, warps |
| PacketEvents | `PacketEvents.jar` | Packet API dependency |
| Sentinel | `Sentinel.jar` | NPC security guards |
| SimpleTPA | `SimpleTPA.jar` | Teleport requests |
| Skript | `Skript.jar` | Script engine for custom scripts (e.g. `clones.sk`) |
| WIT | `WIT.jar` | Inventory inspector |
| Chunky | `chunky.jar` | Pre-generation tool |
| Citizens | `citizens2.jar` | NPC engine |
| UltimateClaims | `claims.jar` | Land claims system |
| LuckPerms | `luckperms.jar` | Permissions manager |
| OpenInv | `openinv.jar` | Open player inventory container |
| UltimateTools | `tools.jar` | Custom items and tools |
| Turrets | `turret.jar` | Turrets defense |
| UltimateRifts | `ultimaterifts.jar` | Dimensional rifts |
| WorldEdit | `worldedit.jar` | World builder tool |
| spark | (folder already restored) | Profiler tool |

Ensure the `.jar` names exactly match the expected names list above so config links aren't broken.

### 4. Start the Server
Once the server software and plugin jars are in place, start the server using your standard parameters:
```bash
java -Xms7G -Xmx7G -jar server.jar nogui
```
On startup, Paper will automatically extract all library files and initialize the plugins.
