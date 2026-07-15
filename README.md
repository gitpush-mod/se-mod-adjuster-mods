<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=180&color=0:0B1021,45:2563EB,100:7C3AED&text=Mod%20Adjuster%20Mods&fontColor=ffffff&fontAlignY=35&fontSize=34&desc=Balance%20patches%20for%20other%20people%27s%20SE%20mods%20on%20SG%20server&descAlignY=57&descSize=15" />
</p>

<p align="center">
  <a href="https://sghq.org/"><img src="https://img.shields.io/badge/Sturmgrenadier-server%20community-1F2937?style=for-the-badge" alt="SG HQ" /></a>
  <a href="https://github.com/gitpush-mod/se-mod-adjuster-mods/issues/new?template=bug_report.md&labels=bug"><img src="https://img.shields.io/badge/Report%20a%20bug-red?style=for-the-badge&logo=github&logoColor=white" alt="Report a bug" /></a>
  <img src="https://img.shields.io/badge/Space%20Engineers-1-0EA5E9?style=for-the-badge" alt="SE1" />
  <img src="https://img.shields.io/badge/10%20mods%20bundled-checkmark-10B981?style=for-the-badge" alt="10 mods" />
</p>

> **"Great mod, but the numbers are wrong for our server. Fixed."**

Ten small **Mod Adjuster** mods that re-tune other people's popular Space Engineers mods to fit the balance conventions of the **Sturmgrenadier community server**. Each adjuster is a thin data-only overlay — it doesn't replace the original mod, it just adjusts stats so blocks fit alongside SG Core and NJFL.

## 🧩 The ten adjusters

| Adjuster | Target mod | Steam Workshop |
|---|---|---|
| **Artillery MKII Turret — Goliath** | Goliath Artillery MK II | [3621015746](https://steamcommunity.com/sharedfiles/filedetails/?id=3621015746) |
| **Dense Colorable Solar Panels** | Dense Colorable Solar Panels | [3363402453](https://steamcommunity.com/sharedfiles/filedetails/?id=3363402453) |
| **Federal Industrial — Utilities** | Federal Industrial Utilities | [3376841882](https://steamcommunity.com/sharedfiles/filedetails/?id=3376841882) |
| **Isy's Dense Solar Panels** | Isy's Dense Solar Panels | [3363402596](https://steamcommunity.com/sharedfiles/filedetails/?id=3363402596) |
| **Life'Tech — Algae Technology** | Life'Tech Algae Technology | [3361336150](https://steamcommunity.com/sharedfiles/filedetails/?id=3361336150) |
| **ModCubeBlocks Refinery x10** | ModCubeBlocks Refinery x10 | [3369254538](https://steamcommunity.com/sharedfiles/filedetails/?id=3369254538) |
| **ModCubeBlocks Upgrade Module** | ModCubeBlocks Upgrade Module | [3369254384](https://steamcommunity.com/sharedfiles/filedetails/?id=3369254384) |
| **More Engineer Characters** | More Engineer Characters | [3361857363](https://steamcommunity.com/sharedfiles/filedetails/?id=3361857363) |
| **More Wind Turbines** | More Wind Turbines | [3363402742](https://steamcommunity.com/sharedfiles/filedetails/?id=3363402742) |
| **[Mafoo] More Batteries** | Mafoo's More Batteries | [3363402980](https://steamcommunity.com/sharedfiles/filedetails/?id=3363402980) |

Each subfolder is a standalone mod with its own `modinfo.sbmi` and Workshop item.

## 🎯 How adjusters work

An adjuster mod is a **thin data overlay** — it doesn't rewrite blocks or replace models. It changes stats (power, cost, output, component requirements) on blocks defined by the target mod, using SE's mod-override system. Load order: target mod first, adjuster second.

- If you **remove the adjuster**, the original mod is untouched and continues to work at its own stats.
- If you **remove the target mod** but keep the adjuster, nothing crashes — the adjuster's overrides just have no target to apply to.

## 🚀 Install

**Individual adjusters:** subscribe to the target mod first, then to the specific adjuster. Enable target before adjuster in the mod list.

**Full SG stack:** subscribe to all ten adjusters + their target mods + the [SG Core stack](https://github.com/gitpush-mod/se-sg-core-mods). This is what SG's server runs.

## ⚠️ Server operators — critical

Same as [SG Core Mods](https://github.com/gitpush-mod/se-sg-core-mods): **never upload the repo's `Sandbox` files to a live SG server** — the live server auto-pulls dependencies; overwriting will wipe them and crash the server.

## 🎯 Compatibility

- ✅ **Space Engineers 1** — actively maintained
- ✅ **Multiplayer + dedicated servers**
- ⚠️ **Mod load order matters** — target mod first, adjuster second
- ⚠️ **Tuned for SG server balance** — may or may not fit your server's ethos; forkable if you want your own numbers

## 🐛 Found a bug?

- **[Open an issue with the bug template](https://github.com/gitpush-mod/se-mod-adjuster-mods/issues/new?template=bug_report.md&labels=bug)** — mention which adjuster + which stat feels wrong
- **Comment on the specific Workshop page** for quick feedback

## 🙌 Credits

- **Author + maintainer of adjusters:** [Chris Carpenter (Godimas101)](https://github.com/Godimas101)
- **Original mod authors:** credited on each Workshop page — this repo only adjusts stats, all block design/modeling is theirs
- **Community:** [Sturmgrenadier Hosting](https://sghq.org/) — the balance conventions come from here

## 🧡 Support

Free and always will be. **Patreon** for the ongoing project log.

[![Support on Patreon](https://raw.githubusercontent.com/Godimas101/personal-projects/main/patreon/images/buttons/patreon-medium.png)](https://patreon.com/Godimas101)

---

*Part of the [`gitpush-mod`](https://github.com/gitpush-mod) mod collection. Made with ♥ (and a lot of coffee) by Godimas + Claude.*
