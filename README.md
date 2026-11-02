# Days Gone Multiplayer

**Development status:** build 276 is prepared but not yet published. The latest changes have passed offline checks and still need in-game validation.

Experimental community co-op mod for Windows x64 and Days Gone 1.13, Steam build 19221447. Players in a session must use the same compatible build. The upcoming build 276 uses protocol 71 and is incompatible with build 217 (protocol 68).

## What's synchronized?

**✅ Working in previous tests · 🟡 Partial or being tested · ❌ Not available**

These descriptions cover development toward build 276. The latest changes still need in-game validation.

| Feature | Status | Current state |
|---|---|---|
| Player movement and appearance | ✅ | Movement, rotation and selected characters are shared. Additional outfits and transitions need testing. |
| Multiplayer lobby and chat | 🟡 | Hosting, joining, save selection and chat are available. The four-player 3D lobby and faster opening need wider testing. |
| Co-op saves | 🟡 | Campaigns use separate saves and a shared catalogue. The original solo save is kept when creating a co-op copy; recovery and transitions need testing. |
| Missions and progression | 🟡 | Some objectives and world changes are shared. Others still depend on the host; independent quests by separated players are not guaranteed to synchronize. |
| Distant enemies and encounters | 🟡 | Some enemies and encounters are now more likely to appear near separated players. Others may remain absent or inactive until players regroup. |
| NPC movement and AI | 🟡 | NPCs and animations are shared, but distant enemies can be stuck, repeat animations, fail to navigate or be unable to attack. |
| Combat and damage | 🟡 | Damage and enemy reactions work in supported cases. Weapon effects and combat edge cases need more testing. |
| Doors and bunker hatches | 🟡 | Door state, timing and bunker hatch presentation have improved; some interactions and effects remain incomplete. |
| Loot and destructibles | 🟡 | Supported interactions are shared; missing effects and state mismatches can still occur. |
| Generators and level effects | 🟡 | Some interactions have improved, but generator actions and mission-specific power effects are not fully synchronized. |
| Motorcycles and passengers | 🟡 | Vehicle and passenger features are available, but movement and physics can still be unreliable. |
| Resource sharing | ✅ | Supported crafting resources can be shared and picked up. |
| Time and weather | 🟡 | Time is shared. Weather transitions still need work. |
| Revival and respawn | 🟡 | Input and recovery have been improved, including failed ground checks; native revival and edge cases still need testing. |
| Cutscenes, tutorials and QTEs | 🟡 | Some sequences and transitions may become stuck or differ between players. |
| Audio, voices and effects | 🟡 | Some sounds and effects can be missing, duplicated or continue incorrectly. |
| Map markers | 🟡 | Shared pings, pins, player colours and routing options have been added; further testing is needed. |
| Automatic LAN server list | ❌ | Join by IP or use the Steam lobby path for now. |

## Changes since build 217

- A 3D multiplayer lobby, character previews, co-op settings, player IDs, ping display and shared map markers.
- Improvements to saves, session recovery, world interactions, combat effects and equipment presentation.
- Improvements for players exploring apart. Missing or inactive enemies and movement problems remain open issues.
- A faster recovery attempt when the local character stays hidden after the camera moves away. It does not fix every case where the game hides the character again; weapon visibility has not been measured.
- Faster opening of the multiplayer menu.

The latest NPC, visibility and menu changes have **not yet been confirmed in game**. Earlier successful tests do not guarantee that every mission or interaction works.

## Install

1. Close the game. In Steam, open Days Gone's local files.
2. Extract the FULL ZIP into the game root containing `BendGame`.
3. Launch through Steam and select MULTIPLAYER. The full package includes the required UE4SS integration and Microsoft runtime.

If another mod uses `dwmapi.dll` or UE4SS, back up its files and settings first. A ZIP cannot merge loader configurations; use a separate clean installation or merge against the exact loader recorded in the manifest.

## Update

Before updating an existing installation, back up any custom files and remove the old `BendGame/Binaries/Win64/ue4ss/Mods/DaysGoneCoopLobby/Scripts` and `DaysGoneCoop-docs` folders. The ZIP restores the current scripts and guides; settings and saves are stored outside those folders.

The UPDATE ZIP contains the mod and documentation only. It requires an existing compatible installation and does not replace the loader or your personal `daysgonecoop.ini`, saves or other mods. Close the game before extracting it into the game root. Back up your saves and settings first.

## Play

Choose a save and host from MULTIPLAYER, then start the session. Other players can join by address and port (default UDP 43919), including LAN or localhost. UPnP can request a router mapping; a firewall, router or CGNAT can prevent Internet connections. Steam host and join paths are available; reliability with two separate Steam accounts still needs validation. Automatic LAN discovery is not included.

Co-op campaigns are kept under `Saved/MultiplayerSaves`, separate from personal saves. The host owns the campaign; return to the title screen before resuming personal play. The game's normal save restrictions still apply.

Open chat with Enter and use `/help` for player commands. The co-op settings screen lets you change supported keys and display options. Appearance and shared map features are available from the multiplayer interface.

## Current limits

This build and its public packaging have not been confirmed in game together. Distant-player world loading, population types and encounters are experimental; some enemies can remain absent until the host approaches. Revive and respawn, missions, cinematics, interaction effects and some weapon or appearance visuals still need wider playtesting. Independent quests and progression are not guaranteed to stay synchronized. Loader failure before the mod starts cannot be detected by the mod itself.

## Remove

Close the game. Remove only files listed in `DaysGoneCoop-docs/manifest.json` and restore any shared loader files you backed up. Keep personal saves, co-op campaigns and other mods. Credits and third-party licenses are in `DaysGoneCoop-docs`.

## Videos

- [First multiplayer test](https://www.youtube.com/watch?v=WiVKn-ZAMDI)
- [Chat, NPCs and networking update](https://www.youtube.com/watch?v=g3zG5G9H4ZQ)

## Credits and permissions

Thanks to the **Days Gone modding community**, **UE4SS / UE4SS-RE, Narknon and contributors**, **ENet / Lee Salzman and contributors**, and **Microsoft**. Full credits and component licenses are included in the package.

Free for personal, non-commercial use. Don't re-upload, repack, sell or convert the original mod to another game, or earn donations/Donation Points from redistributing it or its derivatives. Ask me before modifying or reusing original mod code/assets; gameplay settings changes are fine. Third-party licenses and rights provided by law remain unchanged.

Unofficial fan project, not affiliated with Sony Interactive Entertainment or Bend Studio. Days Gone belongs to its respective rights holders. A legitimate game copy is required.

**This repository is only for releases and their documentation.**
