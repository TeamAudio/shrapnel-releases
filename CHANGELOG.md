# Changelog

All notable public Shrapnel release changes will be documented here.

## 1.0.0 - Unreleased

Initial release.

### Added

- Physics-based sandbox: particles fall and collide with user-placed colliders
  to generate sound.
- Per-collider routing to MIDI (channels 1-16) or to sample groups.
- Up to 8 independent sound slots per collider for layering and
  particle-selective triggering.
- Per-slot collision filtering by particle radius, hit speed, and colour.
- Built-in sampler with per-group filters (LP/HP/BP), pitch and volume
  randomization, velocity mapping, and constant-power pan.
- Granular and live audio-input sound sources.
- MSEG breakpoint modulation editor.
- Persistent spawner with aim/power control, burst and continuous fire, and an
  Auto-Spawn mode.
- Direct-manipulation collider editing (move and resize in the sandbox).
- Preset import and export via `.spn` files.
- Windows support for Standalone, VST3, and CLAP.
- macOS support for Standalone, VST3, AU, and CLAP.
