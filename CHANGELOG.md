# 📋 Changelog

All notable changes, architectural updates, and release notes for **NevPlay** are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Calendar Versioning](https://calver.org/) (`YYYY.MM.PATCH`).

---

## [2026.10.22] — October Feature Release 🚀
*Release Date: 2026-10-22*

> **Summary:** The October update brings major architectural enhancements to NevPlay, completely redesigning the queue workflow, introducing a full multi-selection system across all library views, refining acoustic processing (bass boost & virtualizer), adding seamless ringtone configuration, and optimizing overall app performance.

### 🌟 Key Highlights & Major Additions

* **Multi-Selection Architecture**:
  * Added long-press gesture and multi-selection mode across **Albums**, **Artists**, **Playlists**, **Library**, and **Universal Search**.
  * **Batch Actions**: Bulk tag editing (*Genre, Artist, Album, Album Artist, Year*), bulk addition to playlists, bulk queue insertion (*Play Next / Add to Queue*), bulk favorites toggling, bulk blacklisting, and SAF-compliant bulk deletion from device storage.
  * Interactive floating bottom selection bar displaying real-time selected counts, **Select All / Deselect All**, and direct batch action shortcuts.

* **Rebuilt Queue Screen**:
  * Completely rebuilt the queue screen from the ground up for faster navigation and effortless queue organization.
  * Drag-and-drop reordering, swipe-to-dismiss, and one-tap track jumping with tactile haptic feedback.
  * Rebalanced control ergonomics and button spacing for instant accessibility.

* **Set Song as Ringtone**:
  * Users can now set any local song directly as their device ringtone from inside NevPlay.
  * Streamlined Android system permissions flow (`WRITE_SETTINGS` & MediaStore `IS_RINGTONE`), bypassing vendor-specific greyed-out settings on modern Android versions.

* **In-App Issue & Feature Request Portal**:
  * Added a dedicated **Report Issue / Request Feature** entry in Settings.
  * Users can quickly submit bug reports, feature suggestions, or feedback with optional device context (*OS version, device model, build ID*) for rapid triage.

---

### 🎵 Audio Engine & Acoustic Tuning

* **Bass Boost Distortion Fix**:
  * Completely re-engineered the bass boost DSP algorithm (`NevPlayBassBoostProcessor`) to prevent audio clipping and harmonic distortion.
  * Applied an optimized 120 Hz shelf filter with a calibrated 0.92 limiter ceiling, delivering deep, punchy low-end without muddy resonance or crackle.
* **Virtualizer & Spatial Sound Polish**:
  * Fixed phase cancellation and stereo collapse in `NevPlaySpatializationProcessor`.
  * Smooth 1.0×–2.0× stereo widening with balanced dry/wet blend for expansive, natural soundstage imaging.
* **Stutter-Free Playback**:
  * Resolved playback stuttering and micro-dropouts on specific low-latency and performance-constrained devices by optimizing ExoPlayer buffer allocations and audio thread scheduling.

---

### 🎤 Lyrics & Visual Dynamics

* **Circular Instrumental Break Visuals & Dynamics**:
  * Introduced an animated circular countdown ring for extended instrumental interludes during synchronized lyrics playback.
  * Dynamically visualizes the lead-in duration with a pulsing progress arc, letting listeners anticipate vocal entrance moments.
* **Auto-Synced & Word-by-Word Lyrics Polish**:
  * Enhanced word-by-word timing precision and smooth auto-scrolling behavior.
  * Improved glowing typography, active line emphasis, and fluid entrance animations.
* **Player Layout & Button Spacing Fixes**:
  * Fixed button crowding and player alignment across various aspect ratios, ensuring every playback control has distinct spacing and clear touch targets.

---

### 🛡️ Storage, Blacklist & Privacy

* **Default System Folder Blacklist**:
  * NevPlay now automatically blacklists standard non-music system audio directories by default for both new users and existing users upon upgrading.
  * Protected folders include:
    * `Android/` (system cache, app data)
    * `Ringtones/`
    * `Alarms/`
    * `Recordings/`
    * `Notifications/`
  * Applied automatically to both **internal storage** and **external SD cards**, keeping your music collection clean and clutter-free.

---

### ⚡ Performance, Search & Updater

* **Enhanced Search Functionality**:
  * Upgraded Universal Search with instant indexing, debounced query processing, and fluid keyboard dismissal on scroll.
* **120 FPS Fluid Animations**:
  * Fixed animation frame drops throughout the app, achieving smooth 120 Hz transitions across bottom sheets, mini-player expansions, and list scrolling.
* **Improved In-App Updates**:
  * Streamlined update checking, background package downloads, and silent hash verification for both Stable and Nightly release channels.

---

### ℹ️ Known Issues & Ongoing Work

* Some edge-case layout behaviors on ultra-wide foldable displays are under active investigation and will be resolved in upcoming maintenance releases.

---

## [2026.08.10] - 2026-08-10

### Added
* Enhanced Home screen with dynamic theme adaptation
* Added long-press context menus for songs across Home, Library, and Explorer
* Added Sleep Timer shortcut to Now Playing capsule
* Enhanced "Made for you" section with Artist Mix collages and "Made for You" albums
* Set Ubuntu font family as the primary app font
* Added Cocogoose and Geom as selectable font options in settings
* Improved Universal Search with keyboard dismissal on scroll
* Fixed card visibility issues in Home screen mixes

---

## [2026.07.0] - 2026-07-04

### Added
* Add Weblate integration and translation updates
* Implement play next and improve broadcast safety
* Fix player action wiring and song selection
* Improved Updater & New Nightly channel
* Added exact artwork color setting
* Bump Compose and UI dependency versions
* Added Motion Canvas support
* Refresh artwork on settings changes
* Improved Mini Player and Player transitions
* Refactor lyrics fetching with multi-source support
* Handle missing picker and suggest folders (#455)
* Fixed: cannot import playlists from JSON backup (#449)
* Fixed Lyrics Embedding & Sleep Timer
* Fixed: Sleep timer remaining time not counted down (#450)
* Fixed: Connection failed: `java.security.cert.CertPathValidatorException` (#451)

---

## [5.2.422.1104 Beta] - 2026-07-04

### Added
* Restrict nightly update check to nightly builds
* Implement play next and improve broadcast safety
* Fix player action wiring and song selection
* Added exact artwork color setting
* Bump Compose and UI dependency versions
* Added Canvas support

---

## [5.2.422.1103 Beta] - 2026-07-03

### Added
* Implement play next and improve broadcast safety
* Fix player action wiring and song selection
* Improved Updater
* Add nightly builds & exact artwork color setting
* Bump Compose and UI dependency versions
* Added Canvas support

---

## [5.1.414.1086] - 2026-06-22

### Added
* Added Song-Specific Lyrics Preferences and Custom LRC File Management
* Fixed: Premature signaling of Instrumental lyrics (#442)
* Added ability to share tracks from all song overflow menus
* Fixed: all playlists missing in latest beta build (#437)
* Fixed: Backup button not showing (#435)
* Major optimizations made
* Fixed Stats and Equalizer opening lag
* Fix artist splitting, sorting, and chooser flow across player screens
* Fixed Library Scrollbar
* Refactor: replace magic strings with typed enums for media scanning
* Feat: Extend format/codec/tag support
* Fixed Carousel Scrolling
* Fixed: Update fails every time (#429)
* Added: Sort the Album tab by Year (#432)
* Fixed: Cannot save word by word lyrics and save button squished (#433)
* Added: long press lyrics chip on player to launch immersive view (#406)
* Library improvements & addressed color issues
* Attempt fixes: Whitelist mode doesn't work (#405)
* Added MKV/MKA format support
* Fix(`ArtistDetailScreen`): Update album filtering to use more appropriate matching function
