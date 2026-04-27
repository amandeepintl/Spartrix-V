# SPARTRIX-V

## The Absolute Enforcement Nexus

SPARTRIX-V is a Minecraft Paper anticheat focused on server-side enforcement, behavioral correlation, compact staff alerts, and moderation workflows.

This GitHub repository is **release-only**. It distributes compiled plugin jars and release notes. Source code is not published here.

## Current Snapshot

Latest snapshot line:

- `v0.1.1-SNAPSHOT`

Target platform:

- Paper `1.21.11`
- Java `21`

## What SPARTRIX-V Does Today

This is an early snapshot build, not a final production anticheat. The current plugin provides a practical Paper-event foundation:

- Movement drift checks for obvious speed, flight, glide, step, high-jump, bunny-hop, and boat-fly style behavior.
- Combat reach validation with hit distance checks.
- Basic aura heuristics for bad attack angle and extremely fast target switching.
- Auto-clicker entropy checks using CPS and click interval consistency.
- Inventory-walk detection while player inventories are open.
- Far-place and ghost-hand interaction checks.
- Nuker, fast-break, and auto-drop burst checks.
- Leaked hack-client command detection for commands such as `.bind`, `.setcheckbox`, `.enabledhax`, `.xray`, and similar client control commands.
- Unified flag pipeline so movement, combat, inventory, world, voting, probation, and alerts all use the same evidence path.
- Staff alert compression so operators see compact messages like `HorizontalDrift x6` instead of chat spam.
- Sustained-cheat kick policy using a safer default: `5 seconds` + `6 detections` + `180 correlation score`.
- Community oversight with `/hackflags`, voting, probation tracking, and staff case-file support.

## Commands

- `/sv gui` opens the admin dashboard.
- `/sv status` shows plugin status.
- `/sv reload` reloads configuration.
- `/hackflags` opens the public suspect interface.
- `/hackflags vote <player>` records a community vote.

## Important Detection Limits

Some hacked-client modules are not directly provable from the server alone. Visual or local-only modules such as ESP overlays, Fullbright, NoFog, NoOverlay, keybind menus, GUI themes, and client settings do not send reliable evidence to Paper by themselves.

SPARTRIX-V focuses on what a server can actually observe: movement, combat, clicking, inventory actions, block interactions, command leaks, packet-like behavior exposed through events, and repeated suspicious patterns.

## Installation

1. Download the latest `.jar` from the Releases page.
2. Put the jar into your Paper server's `plugins/` folder.
3. Restart the server.
4. Use `/sv status` or `/sv gui` to confirm the plugin is loaded.

## Release Policy

All current builds are snapshots. Snapshot builds are expected to change quickly while detection logic, thresholds, and admin tooling improve.

No source code is pushed to this public release repository.
