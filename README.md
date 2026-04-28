# SPARTRIX-V.

## The Absolute Enforcement Nexus

SPARTRIX-V is a Minecraft Paper anticheat focused on server-side enforcement, behavioral correlation, compact staff alerts, and moderation workflows.

This GitHub repository is **release-only**. It distributes compiled plugin jars and release notes. Source code is not published here.

## Current Snapshot

Latest snapshot line:

- `v0.1.3-SNAPSHOT`

Target platform:

- Paper `1.21.11`
- Java `21`

## What This Snapshot Detects

This is still an early snapshot, but the current jar includes a stronger Paper-event detection layer:

- `SustainedSpeed` and `HorizontalDrift` checks for speed and horizontal movement abuse.
- `FlyAscend` checks for sustained upward fly hacks.
- `LiquidWalk` checks for Jesus/water-walk behavior.
- `AirPlace` checks for suspended fly/scaffold-style block placement.
- `NoFall` checks using fall-distance tracking and landing validation.
- `FastBreak`, `InstantBreak`, Nuker-style burst, and AutoDrop burst checks.
- Combat reach validation.
- Basic aura heuristics for bad attack angle and fast target switching.
- Auto-clicker entropy checks using CPS and click interval consistency.
- Inventory-walk detection while player inventories are open.
- Far-place and ghost-hand interaction checks.
- Fast-consume and fast-bow timing checks.
- Hotbar macro detection for extreme slot-switch bursts.
- Leaked hack-client command detection for commands such as `.bind`, `.setcheckbox`, `.enabledhax`, `.xray`, and similar client control commands.
- Unified flag pipeline for movement, combat, inventory, world, voting, probation, setbacks, and alerts.
- Staff alert compression so operators see compact messages like `FlyAscend x6` instead of chat spam.
- Sustained-cheat kick policy using `5 seconds` + `6 detections` + `180 correlation score`.
- Community oversight with `/hackflags`, voting, probation tracking, and staff case-file support.

## Commands

- `/sv gui` opens the admin dashboard.
- `/sv status` shows plugin status.
- `/sv reload` reloads configuration.
- `/hackflags` opens the public suspect interface.
- `/hackflags vote <player>` records a community vote.

## Configuration Note

If you already installed an older snapshot, your generated `plugins/SpartrixV/config.yml` will not be overwritten automatically. Compare the new default config or regenerate it on a test server if new checks are not firing.

Important defaults in this snapshot include:

```yaml
checks:
  liquid-walk:
    enabled: true
  air-place:
    enabled: true
  no-fall:
    enabled: true
  world-abuse:
    enabled: true
```

## Detection Limits

This build is event-level, not packet-level yet. It can detect many visible cheat behaviors, but serious anticheat accuracy requires a packet layer for pre-Bukkit movement, block placement faces, ground spoofing, transaction timing, and rotation analysis.

Client-only visuals such as ESP overlays, Fullbright, NoFog, NoOverlay, keybind menus, GUI themes, and client settings are not directly provable from the server alone.

## Installation

1. Download the latest `.jar` from the Releases page.
2. Put the jar into your Paper server's `plugins/` folder.
3. Restart the server.
4. Use `/sv status` or `/sv gui` to confirm the plugin is loaded.

## Release Policy

All current builds are snapshots. Snapshot builds are expected to change quickly while detection logic, thresholds, and admin tooling improve.

No source code is pushed to this public release repository.
