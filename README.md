# Days Gone Multiplayer

I'm building this mod to play **Days Gone with friends**, with shared missions, combat and world interactions. It's free and still in **early alpha**.

## Download

**0.35.102 · Build 212**

### [Download the full mod](https://github.com/Aidoxilia/DaysGone-Multiplayer/releases/download/v0.35.102-build212/DaysGoneCoop-0.35.102-build212.zip)

**[Update an existing installation](https://github.com/Aidoxilia/DaysGone-Multiplayer/releases/download/v0.35.102-build212/DaysGoneCoop-0.35.102-build212-UPDATE.zip)** · [Release notes](https://github.com/Aidoxilia/DaysGone-Multiplayer/releases/tag/v0.35.102-build212) · [Checksums](https://github.com/Aidoxilia/DaysGone-Multiplayer/releases/download/v0.35.102-build212/SHA256SUMS-build212.txt)

Use the **full ZIP** for your first installation. It includes the loader, required runtime and English/French guides. UPDATE needs the compatible loader already installed.

GitHub's “Source code” archives are not the mod download.

**Antivirus reports:** the reports linked below are for the older build 206. Build 212 contains a new `main.dll`; those scan results do not describe this new binary.

## Install

1. Close the game. In Steam, right-click **Days Gone → Manage → Browse local files**.
2. Extract the **full ZIP contents into that folder**, alongside `BendGame`.
3. Launch through Steam and select **MULTIPLAYER** in the main menu or pause menu.

No installer or separate loader download. Don't add an extra subfolder.

**Requirements:** Windows x64, **Steam Days Gone 1.13 / build 19221447**. Everyone must use **build 212**. Other stores, game builds and Linux/Proton aren't validated.

**Other mods installed?** Back up your loader and settings first. Follow the included compatibility guide before replacing an existing `dwmapi.dll` or UE4SS setup.

**Français :** extrayez le ZIP complet dans la racine contenant `BendGame`, puis lancez par Steam. Le guide français est inclus.

## What's synchronized?

**✅ Synced / working · 🟡 In progress · ❌ Not yet**

| Feature | Status | Current state |
|---|---|---|
| Player movement and appearance | ✅ Synced | Movement, rotation and selected character are shared. |
| Multiplayer menu and session setup | ✅ Working | Host, choose a save, join and start together. |
| Persistent co-op saves | ✅ Working | Separate campaigns with persistent autosaves. |
| Missions, jobs and objectives | 🟡 In progress | Some objectives still require the host. New mission/HUD fixes need testing. |
| NPC movement and animations | 🟡 In progress | Shared, but guests can still see stuttering or incorrect animations. |
| Combat and damage | 🟡 In progress | Uses the game's damage system; guest combat still needs work. |
| Doors, vehicle hoods and trunks | 🟡 In progress | Open/loot states are shared; recent fixes need more testing. |
| Ground loot and destructibles | 🟡 In progress | False loot, missing effects and state mismatches can still happen. |
| Generators | 🟡 In progress | On/off works both ways in earlier tests. Guest refuelling is now forwarded; the latest changes need testing. |
| Resource sharing | 🟡 In progress | Press L to share crafting resources. Native pickup added in 212; /drop and /take remain available. |
| Motorcycles and passengers | 🟡 In progress | Shared movement and passenger systems; physics still needs work. |
| Time and weather | 🟡 In progress | Time is shared. Weather transitions still need work. |
| Cutscenes, tutorials and QTEs | 🟡 In progress | Some sequences and transitions can still get stuck. |
| Teammate revival | 🟡 In progress | Prompts, getting up and story-related cases still need work. |
| Audio, voices and effects | 🟡 In progress | Some can be missing, duplicated or keep playing. |
| Automatic LAN server list | ❌ Not yet | Join by IP or Steam lobby for now. |

**Performance is still a priority.** Some sessions have heavy FPS drops, freezes and desynchronization. The mod targets **2–4 players**, but full four-player gameplay is still being tested. Back up important saves before playing.

## New in build 212

- Cached object searches to reduce the periodic stalls and slow-motion effect reported even at a good FPS count.
- Native interaction-key pickup for shared crafting resources, with host arbitration. The **L** share panel and chat commands remain available.
- Visibility repair and diagnostics for dropped beer resources.
- Includes the join-recovery, guest generator-refuelling, mission-marker and already-open hood fixes added since 206.

The newest fixes are compiled and installed, but still need in-game testing. Everyone must update to **212 / protocol 66**.

## Play together

- **Steam:** choose **HOST WITH STEAM**, then invite friends or use **JOIN STEAM LOBBY**. Connection issues can still happen.
- **Direct / LAN:** choose **HOST DIRECT**, select a save, then **START GAME**. Guests enter the host's IP and **UDP port 43919**. Localhost works too.
- **Direct over the Internet:** UPnP attempts automatic port mapping. Some routers, firewalls and CGNAT setups still need another connection method or manual configuration.

Co-op campaigns use their own folders under `Saved/MultiplayerSaves`. Return to the title menu for your personal saves. Global profiles and settings remain managed by the game.

## VirusTotal reports — previous build 206

Checked **25 October 2026 (UTC+4)** for **build 206**. The `main.dll` report below is historical; it does not scan the new build 212 DLL. The bundled UE4SS loader and proxy are unchanged.

Build 212 public `main.dll` SHA-256: `94851017E70DC3A8B61D4D998282D0FFA73441C63FA60D2577D1B639AC464AA4`.

| File | Report | Latest analysis shown |
|---|---|---|
| Mod `main.dll` | [**2/70 detections (False Positives)** — Cynet and Microsoft](https://www.virustotal.com/gui/file/0440de35252ae22e6eb245863a9b3e85b7b14a62a295e5f50abe2d728303b0d0/detection) | 25 Oct 2026 |
| `UE4SS.dll` | [0/70 detections](https://www.virustotal.com/gui/file/b6c3833120285cb49e90849dbca39d658573c4b8bac07ab2b62f78428cf3b1d3/detection) | 25 Sep 2026 |
| `dwmapi.dll` loader proxy | [0/71 detections](https://www.virustotal.com/gui/file/9dfdccff36d7c081cff7380b2d446386d9a56e5dd26ef97fe9eac23920446838/detection) | 16 Oct 2026 |

**Why is `main.dll` flagged? (Confirmed False Positive)**
The 2 detections on `main.dll` (**Microsoft** `Trojan:Win32/Wacatac.C!ml` and **Cynet** `Malicious`) are **heuristic / machine-learning false positives** (`!ml` stands for Machine Learning). 

Because this is an unsigned indie C++ multiplayer mod that hooks into the game's memory in real time and opens network sockets (ENet/Steam) to synchronize players, automated AI scanners flag its behavior as suspicious. All other 68 security vendors—including Kaspersky, BitDefender, ESET, CrowdStrike, and Malwarebytes—confirm the file is clean. The loader and proxy (`UE4SS.dll` and `dwmapi.dll`) match the official upstream UE4SS files with 0 detections.

**If Windows Defender deletes or blocks `main.dll`:** Allow the file in Windows Security (*Protection history*) or add your Days Gone game folder to your Windows Defender exclusions.

## Report a bug

Tell me your version, whether you were hosting or joining, and what each player saw. Use `/bug description` in chat to mark the logs. Remove personal information and IP addresses before sharing them.

## Videos

- [First multiplayer test](https://www.youtube.com/watch?v=WiVKn-ZAMDI)
- [Chat, NPCs and networking update](https://www.youtube.com/watch?v=g3zG5G9H4ZQ)

## Credits and permissions

Thanks to the **Days Gone modding community**, **UE4SS / UE4SS-RE, Narknon and contributors**, **ENet / Lee Salzman and contributors**, and **Microsoft**. Full credits and component licenses are included in the ZIP.

Free for personal, non-commercial use. Don't re-upload, repack, sell or convert the original mod to another game, or earn donations/Donation Points from redistributing it or its derivatives. Ask me before modifying or reusing original mod code/assets; gameplay settings changes are fine. Third-party licenses and rights provided by law remain unchanged.

Unofficial fan project, not affiliated with Sony Interactive Entertainment or Bend Studio. Days Gone belongs to its respective rights holders. A legitimate game copy is required.

**This repository is only for releases and their documentation.**
