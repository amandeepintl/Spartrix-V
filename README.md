# SPARTRIX-V

## The Absolute Enforcement Nexus

SPARTRIX-V is a Minecraft Paper anticheat focused on server-side enforcement, readable staff alerts, behavioral correlation, moderation workflows, and low-overhead event-level detection.

This GitHub repository is **release-only**. It distributes compiled plugin jars and release notes. Source code is not published here.

## Current Snapshot

Latest snapshot line:

- `v0.1.4-SNAPSHOT`

Target platform:

- Paper `1.21.11`
- Java `21`

## What This Snapshot Detects

This is still a snapshot, but the current jar has a broader and cleaner event-level detection layer:

- `Flying` detection for fly/hover/air-strafe movement with setback locking.
- `Speed Hack` detection for sustained illegal horizontal movement.
- `No Fall` validation with delayed landing checks and suppression after fly/setback events.
- `Jesus` checks for water-walk/liquid-walk behavior.
- `Air Place`, `Far Place`, and `Ghost Hand` checks for invalid block placement and through-wall interaction.
- `Fast Break`, `Nuker`, and `Auto Drop` world-abuse checks.
- `Anti Cactus` damage-integrity enforcement with server-side damage forcing.
- `Anti Knockback` checks for missing knockback after velocity.
- `Anti Hunger` checks for cancelled or missing hunger loss during sprinting.
- `Entity Push` checks for players resisting normal entity push behavior.
- `Reach`, `Kill Aura`, `Multi Aura`, and `Auto Clicker` combat/click checks.
- `Inventory Move`, `No Slow`, `Fast Eat`, `Fast Bow`, `Hotbar Macro`, `Boat Fly`, and `Vehicle Speed` checks.
- Leaked hack-client command detection for commands such as `.bind`, `.setcheckbox`, `.enabledhax`, `.xray`, and similar client control commands.
- Unified flag pipeline for movement, combat, inventory, world, voting, probation, setbacks, and alerts.
- Compact staff alerts using readable names instead of internal engine names.
- Sustained-cheat kick policy capped at `3 seconds`.
- Community oversight with `/hackflags`, voting, probation tracking, and staff case-file support.

## Commands

- `/sv gui` opens the admin dashboard.
- `/sv status` shows plugin status.
- `/sv reload` reloads configuration.
- `/hackflags` opens the public suspect interface.
- `/hackflags playtime` shows the playtime used for voting eligibility.
- `/hackflags vote <player>` records a community vote.

## Configuration Note

If you already installed an older snapshot, your generated `plugins/SpartrixV/config.yml` will not be overwritten automatically. Compare the new default config or regenerate it on a test server if new checks are not firing.

Important defaults in this snapshot include:

```yaml
thresholds:
  alerts:
    kick-after-seconds: 3

checks:
  anti-cactus:
    enabled: true
  anti-knockback:
    enabled: true
  anti-hunger:
    enabled: true
  entity-push:
    enabled: true
```

## Performance Notes

SPARTRIX-V `0.1.4-SNAPSHOT` keeps low-end servers in mind:

- Anti Cactus tracks only active cactus-contact suspects instead of scanning every online player globally.
- Auto Clicker no longer performs target-block lookup on every arm swing.
- Most checks are event-driven and avoid packet-level hooks for now.
- Heavy packet simulation is not included in this snapshot.

## Detection Limits

This build is event-level, not packet-level yet. It can detect many visible cheat behaviors, but serious anticheat accuracy still requires a packet layer for pre-Bukkit movement, block placement faces, ground spoofing, transaction timing, and rotation analysis.

Client-only visuals such as ESP overlays, Fullbright, NoFog, NoOverlay, keybind menus, GUI themes, and client settings are not directly provable from the server alone.

## Installation

1. Download the latest `.jar` from the Releases page.
2. Put the jar into your Paper server's `plugins/` folder.
3. Restart the server.
4. Use `/sv status` or `/sv gui` to confirm the plugin is loaded.

## Release Policy

All current builds are snapshots. Snapshot builds are expected to change quickly while detection logic, thresholds, and admin tooling improve.

No source code is pushed to this public release repository.
