# Changelog

All notable public Shrapnel release changes will be documented here.

## 1.0.0-rc.1 - 2026-08-30

### Added

- AAX (Pro Tools) plugin format — code-signed and validated on Windows and macOS.
- Installer now shows the EULA and requires acceptance before installing, and
  bundles third-party license notices.
- Init (blank slate) and a bundled factory default preset, loaded on first launch.
- Window Size preference to set the default editor size.

### Changed

- Factory default preset is now "Plink" (was "Glass Tink").

### Fixed

- Spawner no longer treats Ctrl+click as a right-click; right-drag now aims the
  spawner while Ctrl-spawning; the spawner glyph scales with window size; and on
  macOS the Cmd key no longer sticks the spawner.
- MIDI-spawn Note readout shows the learned note instead of always C4.
- Pro Tools Dynamic Plug-In Processing no longer freezes the sandbox.
- Window-sizing/clipping fixes on Bitwig (CLAP) and Pro Tools (AAX).

## 1.0.0-beta.5 - 2026-08-13

### Changed

- Unlicensed demo mode now drops out silently — removed the noise swell and tone.

### Fixed

- MIDI-spawn Note readout no longer shows NaN.

## 1.0.0-beta.4 - 2026-08-12

### Fixed

- Activation now persists after first attempt.

## 1.0.0-beta.3 - 2026-08-11

### Added

- Windows installer is now code-signed (Azure Artifact Signing + RFC3161
  timestamp).
- Master-output WAV recording — bounce the standalone's output to disk.
- About window showing the version and a link to the online manual (all formats).

### Changed

- License window: clearer demo-mode indicator and a direct purchase link.

### Fixed

- Global physics param sliders now accept manual text entry.
- Removed a redundant hover tooltip on the empty sandbox.

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
