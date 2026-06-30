# Changelog

## v1.0.0

### Added

- Initial public release.
- Added local single-file HTML5 app structure.
- Added MP3 / WAV audio loading through browser decoding.
- Added SRT loading and SRT list display.
- Added drag-and-drop loading for audio and SRT files.
- Added waveform display using Canvas.
- Added click-to-select navigation on the waveform.
- Added SRT row click navigation.
- Added fixed selected-position playback behavior.
  - Playback starts from the last selected position.
  - Stopping returns the playback cursor to the selected position.
- Added start-position workflow.
  - User-selected start position.
  - Actual cut position calculated as start position minus fade-in length.
  - Short fade-in options for click-noise reduction.
- Added output-time waveform mode after the start position is set.
- Added safe limit line, default `179.800` seconds.
- Added free end-point selection within the safe limit.
- Added fade-out start and end-point markers.
- Added preview playback reflecting fade-in and fade-out.
- Added terminal subtitle handling with an edited-text field.
  - unchanged text keeps the original subtitle text.
  - edited text replaces the terminal subtitle text.
  - empty edited text omits the terminal subtitle.
- Added 16-bit PCM WAV export.
- Added short SRT export with timestamp conversion and renumbering.
- Added Japanese / English UI switching.
- Added tooltip help for major UI controls.
- Added Undo button and `Ctrl+Z` support for editing operations.
- Added MIT license package.

### Notes

- The original full-length SRT is treated as the trusted timing master.
- The app does not generate subtitles automatically.
- Output audio is WAV only. MP3 output is not included.
- MP3 decoding depends on browser support.
- The app is intended for one full-length song, typically around three to five minutes, not album-length audio.
