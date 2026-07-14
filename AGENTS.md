# AGENTS.md — Mod Adjuster mods (bundle for SG)

Space Engineers 1 mod. Part of Chris's mod collection under
[`gitpush-mod`](https://github.com/gitpush-mod).

## What this is

Bundle repo for 10 balance/tuning mods that adjust other people's SE mods for use on the Sturmgrenadier community server. Each in its own subfolder.

## For agents

- **Game:** Space Engineers 1
- **SE modding skill:** Chris has an SE modding Claude skill (source:
  [`Godimas101/se-claude-skill`](https://github.com/Godimas101/se-claude-skill)) —
  use it when working on this mod
- **SDK:** `D:\SteamLibrary\steamapps\common\SpaceEngineersModSDK\`
- **Vanilla SBCs (authoritative for TypeId/SubtypeId + schema baselines):**
  `D:\SteamLibrary\steamapps\common\SpaceEngineers\Content\Data\`
- **Workshop mods (reference / dependencies):**
  `D:\SteamLibrary\steamapps\workshop\content\244850\`

## Development principles (shared across all Chris's SE mods)

1. **Backward compatibility.** Never break existing CustomData or save games.
   Add new config keys, don't remove or rename.
2. **Performance first.** Cache subgrid scans, minimize LINQ, defensive parsing.
3. **Null safety.** Always check block/component existence before use.
4. **Match existing style.** Follow the patterns already in this codebase.

## MUST NOT

- Modify vanilla SE game files (`steamapps/common/SpaceEngineers/`)
- Rename or delete workshop content
- Upload repo `Sandbox` files to a live SG server (wipes auto-pulled dependencies)
- Break save-game compatibility without explicit version bump

## Related

- Parent (when checked out under Chris's tree): `mods/space-engineers-mods/` /
  `mods/AGENTS.md`
- Universal Golden Rules: top-level `AGENTS.md` in `VS Code Projects/`

## About this bundle

10 balance-adjustment mods bundled together — each modifies another modder's
work for the SG server context. Each lives in its own subfolder (folder names
preserve the "[Mod Adjuster For SG]" suffix for easy matching to the SE Mod
Manager listing on Chris's game).

When one of the upstream mods updates, the corresponding adjuster subfolder
here needs a matching update. Kept in one repo because they share a common
"tune upstream mods for SG" purpose.
