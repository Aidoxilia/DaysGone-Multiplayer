# Days Gone Multiplayer — Co-op Mod

An unofficial, fan-made co-op mod for **Days Gone on PC**.

**This repository is for releases, installation information and player feedback only. The development source code is not published here.**

> [!IMPORTANT]
> **Experimental / Early Alpha — 0.35.96, build 206, protocol 65.**
> Expect desynchronization, FPS drops, freezes, crashes and unfinished story/revival cases.
> Every player must use build 206. Earlier builds are incompatible with this protocol.

## Download

**[Release 0.35.96 — build 206](https://github.com/Aidoxilia/DaysGone-Multiplayer/releases/tag/v0.35.96-build206)**

- **[FULL ZIP — first installation](https://github.com/Aidoxilia/DaysGone-Multiplayer/releases/download/v0.35.96-build206/DaysGoneCoop-0.35.96-build206.zip)**: includes the pinned UE4SS loader, required Microsoft x64 runtime, and English/French guides.
- **[UPDATE ZIP — existing compatible installation](https://github.com/Aidoxilia/DaysGone-Multiplayer/releases/download/v0.35.96-build206/DaysGoneCoop-0.35.96-build206-UPDATE.zip)**: mod-only update; preserves existing settings and loader configuration.
- **[SHA-256 checksums](https://github.com/Aidoxilia/DaysGone-Multiplayer/releases/download/v0.35.96-build206/SHA256SUMS-build206.txt)**.

Use the release assets above. GitHub's automatically generated **“Source code”** archives contain this release repository's documentation, not the playable mod.

## Install — extract and play

1. Close Days Gone.
2. In Steam, right-click **Days Gone → Manage → Browse local files**.
3. Extract the **FULL ZIP contents directly into the game root**, the folder containing `BendGame`. Do not add an extra nested folder.
4. Launch the game through Steam.
5. Select **MULTIPLAYER** in the main menu or pause menu.

No installer, command prompt, SDK, compiler or separate loader download is needed.

**Already using mods?** Back up your existing loader and configuration first. The FULL ZIP is a fresh-install integration and cannot detect conflicts with another `dwmapi.dll` or UE4SS installation. Follow the included guide to merge compatible files; do not blindly overwrite another mod's loader. Use UPDATE only with our pinned loader installation. Back up valuable saves before testing.

**Français :** fermez le jeu, extrayez le ZIP COMPLET dans la racine contenant `BendGame`, puis lancez par Steam et choisissez MULTIPLAYER. Le guide français détaillé est inclus dans le ZIP.

## Requirements and connection

- A legitimate **Steam PC copy of Days Gone 1.13 / build 19221447** (AppID 1259420), on **Windows x64**.
- Everyone uses the **same mod build: 206 / protocol 65**.
- Other stores/builds, Linux/Proton and Steam Deck are not validated.
- Designed for **2–4 players**; complete four-player gameplay coverage is still being validated.

**HOST DIRECT:** choose a save, create the session, then START GAME. Guests join by IP and port. Default **UDP 43919**; LAN and localhost are supported. UPnP attempts automatic router mapping, but router support, firewalls and CGNAT can still prevent Internet joins. Automatic LAN server discovery is not implemented yet.

**HOST WITH STEAM / JOIN STEAM LOBBY:** Steam lobbies and friend invitations are implemented. Players have used remote Steam sessions; the newest join fixes and reliable gameplay across different PCs still need validation. Direct hosting remains available.

## What build 206 changes

- Sends the host generator's fuel, running and repair state to guests through its native Blueprint restoration path.
- Fixes the Blueprint function lookup implicated in guest job objective refresh exceptions.
- Corrects the boolean-layout check that blocked mission HUD publication and affected shared interaction/state readers.
- Keeps a failed generator restoration pending instead of recording a false application success.

**Generator interactions initiated by a guest are not forwarded to the host yet.** Native lights, particles, audio and mission/HUD results in this candidate still require in-game confirmation.

## Current feature status

| System | Actual status |
|---|---|
| Native multiplayer menu, host save selection and START | Available; previously confirmed by the owner. |
| Persistent co-op campaigns and autosaves | Available; persistent autosaves previously confirmed by the owner. |
| Missions, jobs, objective HUD and scripted interactions | Synchronization implemented; fixes included, with remaining scenario-specific problems. |
| NPCs, combat, damage and animations | Implemented, with remaining animation, smoothness and performance problems. |
| Doors, vehicle hoods/trunks, world loot and destructibles | Synchronization implemented; coverage and regressions still require testing. |
| Generator state | Host → guest implemented in 206; guest → host operation remains open. |
| Motorcycles, time/weather, cutscenes, QTEs and revival | Systems exist, but coverage and edge cases remain incomplete. |

This is not a claim that every mission, enemy, animation, physics interaction or effect is synchronized perfectly.

### Saves

Co-op campaigns use `Saved/MultiplayerSaves/<campaign>/SaveGames`, separate from personal campaign saves. A copy of the host's selected save seeds a campaign. Guests load a campaign copy; return to the title menu to access personal saves again. Global player profiles/settings remain native. See the included EN/FR guides for manual saves and loading behavior.

### Verification and known limits

Build 206 was compiled and installed on three local instances. **25/25 automated tests passed**, 27 runtime file hashes matched, and 194 save files were checked unchanged. These are build/deployment checks, not proof of native visuals, four-player gameplay, stable Internet play or 60 FPS.

Known open areas include severe stutter/FPS drops in some sessions, NPC motion/animations, guest interaction authority, generator guest → host operation, and story/cutscene/QTE/revival/load edge cases. Build 206 is **not** advertised as resolving all earlier freeze, dead-NPC audio or corpse-loot reports.

For a bug report, include the mod/game versions, host or guest role, steps and what each side saw. Use `/bug description` in chat to mark the telemetry. Remove personal information and IP addresses before sharing logs.

## Development videos

- [First multiplayer test](https://www.youtube.com/watch?v=WiVKn-ZAMDI)
- [Chat, NPCs and networking update](https://www.youtube.com/watch?v=g3zG5G9H4ZQ)

Videos show development progress; they are not a guarantee for every scenario in this release.

## Credits, permissions and disclaimer

Thanks to the **Days Gone modding community** for its tools, knowledge and testing.

- **UE4SS / UE4SS-RE, Narknon and contributors** — pinned MIT-licensed loader and its own injection proxy.
- **ENet / Lee Salzman and contributors** — MIT-licensed networking library.
- **Microsoft** — separately licensed Visual C++ runtime.
- Full acknowledgements, component licenses and permissions are included under `DaysGoneCoop-docs` in the ZIP.

**© 2026 Mod authors. All rights reserved for original mod content.** Free personal, non-commercial use is allowed. Do not re-upload, mirror, repack, sell or convert the original mod to another game. Modification or reuse of original code/assets requires prior permission; normal settings changes are allowed. Do not earn donations or Donation Points from redistribution or derivatives using the original content. These conditions do not override third-party licenses or rights provided by law.

Unofficial fan project; not affiliated with or endorsed by **Sony Interactive Entertainment** or **Bend Studio**. Days Gone and its related intellectual property belong to their respective rights holders. A legitimate copy of the base game is required.
