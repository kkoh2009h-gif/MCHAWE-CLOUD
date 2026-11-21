# PS4 native build scaffold

This folder is a **starter native PS4 homebrew build**, not yet a complete launcher.

## Build
The GitHub Actions workflow attempts to build the native ELF/eboot with OpenOrbis. The current source is a minimal console prototype.

## Important
The web launcher in the repository is not automatically embedded into this native app. Porting the visual interface and implementing networking, authentication, controller input, and cloud-stream playback are separate development tasks. No PKG is produced by this initial scaffold yet; packaging/icon/param.sfo steps still need to be added and validated.
