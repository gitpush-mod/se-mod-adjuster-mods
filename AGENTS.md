# AGENTS.md — Mod Adjuster mods (bundle for SG)

Space Engineers 1 mod. Part of Chris's mod collection under
[`gitpush-mod`](https://github.com/gitpush-mod).

## What this is

Bundle repo for 10 balance/tuning mods that adjust other people's SE mods for use on the Sturmgrenadier community server. Each in its own subfolder.

## Where work lives (RULE — non-negotiable)

**Every task on this mod is a ticket on its project board.** YOU (the agent) create the ticket BEFORE touching anything. No exceptions for "small" work.

**Board:** [Mod Adjuster Mods board](https://github.com/orgs/gitpush-mod/projects/10)

Concrete rules — same as TCS ticket-first:

- **Starting work?** Open a ticket in this repo, add to the board, set Status = **In Progress**, then start.
- **Have an idea for later?** Ticket in **Backlog**. Not in memory, not in a README, not in NOTES.md.
- **Need Chris to check something before closing?** Move the ticket to **In QA** and comment with exactly what he needs to look at. Do NOT set to Done — that's Chris's call after review.
- **Finished?** Close the ticket with a closing summary comment (what you did / problems + solutions / anything NOT done).
- **Same-session micro-work?** Open + close in the same session — but the ticket exists.
- **Older than 30 days in Done?** The weekly cron in this repo moves it to Archived. The closed ticket + CHANGELOG entry persist.

Automation: closing a Done ticket auto-appends an entry to this repo's `CHANGELOG.md` (via the workflow in `gitpush-mod/.github`). Requires `MOD_PROJECT_TOKEN` org secret — already installed.

**Do NOT** work on this mod without a ticket. If Chris asks for something small, create + immediately-close the ticket. It's still faster than the paper-trail debt of un-ticketed work.

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

## How to verify (before flagging In QA or closing)

- **Load in-game.** Enable this mod in a real world (creative or survival). Place the affected block(s). Watch what happens on the LCD / block / behavior for at least 30 seconds.
- **Client-only check.** Verify no SessionComponent / server-side code was added. If the mod is meant to be client-side (InfoLCD variants), test in a dedicated-server context too — the mod should still work for the client without any server-side install.
- **Save-safety.** Load an existing world, add or remove the mod, verify no CustomData strings broke and no blocks vanished.
- **Look for LINQ or per-tick allocations** in scripts before pushing — SE MP performance is brutal on hot paths.
- **Watch `%AppData%\SpaceEngineers\SpaceEngineers_*.log`** — any red or yellow lines mention the mod? If yes, quote them in the ticket.

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
