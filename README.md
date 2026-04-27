# SPARTRIX-V

## The Absolute Enforcement Nexus

SPARTRIX-V is a Minecraft server anticheat plugin focused on server-authoritative enforcement, behavioral correlation, and admin-facing moderation workflows.

This repository is **release-only**.
It exists to distribute compiled plugin builds and release assets.
Source code is not published here.

## Current Release

Download the latest plugin jar from the [Releases](../../releases) page.

Current public release line:
- `v0.1.0`

## Compatibility

- Paper `1.21.11`
- Java `21`

## Current Feature Set

The current public build includes:

- movement drift enforcement
- reach envelope checks
- auto-clicker entropy detection
- inventory-move detection
- far-place detection
- ghost-hand style interaction checks
- probation tracking
- case-file generation
- public `/hackflags` voting flow
- `/sv` admin command and control GUI

## Commands

- `/sv gui`
- `/sv status`
- `/sv reload`
- `/hackflags`
- `/hackflags vote <player>`

## Installation

1. Download the latest `.jar` from [Releases](../../releases).
2. Put the jar into your server's `plugins/` folder.
3. Start or restart your Paper server.
4. Configure the plugin through its generated config files if needed.

## Notes

- This plugin is currently distributed as a compiled binary release.
- Public releases may change over time as new detection modules and enforcement systems are added.

## Support

If you use this repository, use the release assets from the Releases page rather than cloning the repository contents.
