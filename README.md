# 🌲 Minecraft Server Backups 🌲

```text
     _      _      _
   _( )_  _( )_  _( )_
  (_ % _)(_ % _)(_ % _)
    (_)    (_)    (_)
   |  |   |  |   |  |
   |  |   |  |   |  |
  =====================
      MINECRAFT BETA
  =====================
       [ ]  [ ]
       [ ]  [ ]
       [ ][ ][ ]  
     [ ][ ][ ][ ]
```
> *"You spawn in a new world. The sun is setting. You quickly punch some wood, build a small dirt shelter, and place your first torch. Outside, you hear the distant groans of zombies and the hiss of spiders. This is where the adventure begins..."*

Welcome back, Admin. This repository houses the memories and data of our server. Below are the scrolls needed to resurrect this world in the future.

---

## 📜 How to Resurrection / Restore the Server

To keep these scrolls light and save space on our hard drives, large compiled binaries (`.jar` files) and library books are excluded. Follow these ancient steps to bring the server back to life:

### 1. Dig up the Backup Archive
1. Go to the **Releases** tab of this repository.
2. Download the latest backup chest (`backup-YYYY-MM-DD_HH-MM-SS.tar.gz`).
3. Create a clean folder and extract the chest there:
   ```bash
   mkdir mc-server && cd mc-server
   tar -xzvf path/to/backup-YYYY-MM-DD_HH-MM-SS.tar.gz
   ```

### 2. Procure the Server Jar (Paper 26.1.2)
This world is bound to **Minecraft 26.1.2** (Paper build `26.1.2-72-1a6b910`). 
Download the executable server jar:
```bash
wget -O server.jar https://fill-data.papermc.io/v1/objects/0555a0b0468a5198d8fb1a16e1f9e95c81a917a2dc8f2e09867b4044742f6401/paper-26.1.2-72.jar
```

### 3. Restore the Plugin Runes
The backup contains all configurations and scripts (including the legendary `herobrine.sk`), but excludes the plugin binaries. Download these plugin jars and place them inside the `plugins/` directory:

| Rune / Plugin Name | Expected File Name | Purpose / Download Source |
|---|---|---|
| AdvancedPortals | `AdvancedPortals.jar` | Portal magic |
| AuthMe | `AuthMe.jar` | Password locks for security |
| AxGraves | `AxGraves.jar` | Keeps your inventory safe when you perish |
| EssentialsX | `EssentialsX.jar` | Commands, spawn points, and economy |
| PacketEvents | `PacketEvents.jar` | Low-level packet hook |
| Sentinel | `Sentinel.jar` | Brave NPC guards |
| SimpleTPA | `SimpleTPA.jar` | Teleporting requests between players |
| Skript | `Skript.jar` | Custom script engine (powers `clones.sk`, `herobrine.sk`) |
| WIT | `WIT.jar` | Watching containers closely |
| Chunky | `chunky.jar` | Pre-generating chunks to avoid lag spikes |
| Citizens | `citizens2.jar` | Spawns NPCs to populate the towns |
| UltimateClaims | `claims.jar` | Declaring land ownership |
| LuckPerms | `luckperms.jar` | Permissions and ranks |
| OpenInv | `openinv.jar` | Open chests and player inventories |
| UltimateTools | `tools.jar` | Mystical items and tools |
| Turrets | `turret.jar` | Autonomous defense turrets |
| UltimateRifts | `ultimaterifts.jar` | Dimensional gates |
| WorldEdit | `worldedit.jar` | World shaper |
| spark | (folder already restored) | Profiler |

*Make sure the file names match exactly so the old configs recognize them!*

### 4. Ignite the Server
Run the startup script to start the world:
```bash
java -Xms7G -Xmx7G -jar server.jar nogui
```

---
* **Note:** *Always sleep in a bed to set your spawn point.*
* **Update Log:**
  - *Restored backup scripts.*
  - *Added nostalgic lore.*
  - *[BUGFIX] Removed Herobrine.*
