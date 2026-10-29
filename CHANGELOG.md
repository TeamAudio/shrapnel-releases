# Changelog

All notable public Shrapnel release changes will be documented here.

## 1.1.0 - 2026-10-27

### Added

- Factory presets. The preset menu now has a Factory section, with presets
  organized into folders, above your own User presets. Hovering a preset shows
  its author and description. The full Shrapnel Factory Pack (100 presets) is a
  separate free download. Factory presets load in licensed copies of Shrapnel;
  in demo mode only Plink_01 loads.
- Preset info panel: shows the current preset's title, author and description,
  and lets you edit them. Changing the title renames your preset file.
- Startup Preset in Preferences: choose what new instances load: the default
  (Plink_01), Init, or any factory or user preset.
- Granular: a play button next to Browse previews the source file. Hovering the
  file name shows its full name.
- Pitch snapping has a Key setting: a key for MIDI slots, and a semitone offset
  for sampler, granular and audio-input slots.
- Preferences → Audio Cache shows how much space extracted preset audio uses,
  and can clear it.

### Changed

- Spawn Rate now goes down to 0.1 Hz (one spawn every 10 seconds), and its
  slider is log-scaled so slow rates are easy to set.
- Max Voices now also applies with OVPP on, and stolen voices fade out over the
  collider's Fade time instead of cutting off.
- Vel Scale can now go all the way to 0, so every hit plays at full volume
  regardless of speed.
- Sample group files can be up to 120 seconds long (was 30). Longer files are
  cut off at 120 seconds and shown in red in the Sample Groups window.
- Loading a preset no longer changes your own settings, such as tooltips, glow
  or stats.
- Audio extracted from presets is now stored in the system cache folder and
  shared between presets that use the same file. Projects and presets from 1.0.x
  still find their audio, and any missing audio is restored automatically from
  its preset.
- Preset names must use plain (ASCII) characters that are valid on both Windows
  and macOS.

### Fixed

- With pitch snapping on, colliders with different pitch ranges played in
  different keys, and some ranges were detuned by half a semitone.
- Deleting or replacing a soloed collider or sound slot left everything else
  silent, with nothing left to un-solo.
- Loading a preset while sounds were playing let the old preset's notes and
  voices ring on into the new one.
- A collider over its Max Voices limit stayed over it under steady hits.
- Bypassing a filter MSEG left the filter running at its default cutoff.
- The preset menu came up empty once a library grew large enough.

## 1.0.2 - 2026-10-05

### Added

- Shrapnel now tells you when a newer version is available: a small notice
  appears in the top-right corner of the editor and links to the product page.
  It checks once per session and stays quiet when you're offline.
- Range sliders: double-click either number in the readout to type a value.
  Units are understood (e.g. `250ms`, `1.2s`, `2kHz`, `6dB`, `7st`).
- Hold Shift while dragging a slider or range handle for fine adjustment.
- AIFF and AIFC files can now be loaded as samples and granular sources.
- Pro Tools: Shrapnel can now be inserted on mono tracks (mono in, stereo out).

### Changed

- Granular Transient mode now works inside the position selection. Transient is
  an on/off toggle; each hit picks from the markers inside the selection, and
  markers outside it are drawn dimmed. Presets saved in Transient mode behave
  as they did before.
- Spawner motion Freq, and granular Attack, Hold and Decay, now give more of
  their travel to the low end, so short and slow settings are easier to dial
  in. Saved values are unchanged.

### Fixed

- Granular Transient mode placed dozens of markers on low or rumbly hits (kicks,
  explosions) and only one on bright ones, so grains favored bass-heavy
  material. Each hit now gets one marker. Markers are re-detected when a
  preset or project loads, so existing Transient-mode patches may trigger a
  little differently.
- At high gravity with large audio buffer sizes, resting particles kept
  bouncing and never settled. Physics now runs at a fixed rate whatever the
  buffer size.
- In hosts that stop processing while transport is stopped or the plugin is
  bypassed (e.g. Soundminer VST Rack, or REAPER with "Run FX when stopped"
  off), presets loaded only partway and "+ Collider" did nothing until
  playback started.
- With a few hundred samples loaded, the Sample Groups list went blank, new
  groups didn't appear, and groups couldn't be assigned.
- Saving a preset with audio deleted any sample group not yet assigned to a
  collider, both from the file and from the current session.
- Long sample file names pushed the sample list and its buttons past the
  edge of the Sample Groups window.

## 1.0.1 - 2026-09-21

### Added

- Advanced-mode readouts that are being reshaped by the Basic-mode knobs are
  now highlighted, with a hover receipt naming the knob responsible and its
  net effect (e.g. "Basic Mode Pitch Knob: +7.0 st"). Covers Pitch/Volume on
  sampler, granular and audio-input slots, and the spawn rate/amount, damping
  and velocity sliders driven by Amount/Spread.
- "BASIC MODS" chip at the top of the collider panel, visible in both Basic and
  Advanced modes, lists the engaged knobs and resets them all in one click
  (undoable).
- Basic-mode knobs glow with a halo while they're off their default.

### Changed

- Links to techaud.io opened from the plugin (manual, product page, purchase)
  now carry UTM tags so in-app visits can be told apart from organic traffic.

### Fixed

- Windows: the editor opened clipped to the top-left with blank space to the
  right and below in Ableton Live on 125%/150% display scaling, and only
  recovered after a maximize/restore.
- Windows: VST3/CLAP editor size is now correct in DPI-aware hosts (e.g.
  REAPER) at 125%/150% display scaling.
- Windows: opening Shrapnel in a second host while another host already had it
  open (e.g. REAPER after Live) showed a blank editor for the life of that
  process. Also affected Shrapnel alongside other WebView-based plugins.
- The "+ Add MSEG" and "+ Add Spawner Motion" buttons appeared to do nothing
  when the window was maximized or fullscreen on a large display (e.g. 4K).
  Their menus were opening off-screen; they now drop directly under the button
  at any window size.
- Sound slots appeared to vanish and the properties panel went blank after
  undoing a collider add, redoing a delete, or loading a project saved with a
  stale collider selection.
- Granular transient mode only ever fired from the first 128 detected markers,
  so on a file with many transients grains clustered near the start while
  markers were drawn across the whole waveform. The limit is now 1024, and a
  file with more than that uses an evenly spaced subset spanning the whole
  file. The markers drawn are now exactly the ones that can fire.

## 1.0.0 - 2026-09-03

- Initial release of Shrapnel.
- Collision based sound design tool.
- Supports VST3, AU, AAX, CLAP, Standalone.

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
