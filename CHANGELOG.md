# Changelog

## v1.0.5

- Added implicit drag-and-drop support to the loading-status message area below the main drop zone. It accepts files exactly like the visible drop zone without adding new UI text.
- Changed the default safe duration limit from `179.800` seconds to `179.700` seconds.
- Updated application and documentation version labels to v1.0.5.

## v1.0.4

- Changed SRT row click navigation so that the waveform automatically switches to the standard zoom level around the clicked subtitle.
- Added four navigation buttons beside Undo: `-30秒`, `-10秒`, `+10秒`, and `+30秒` / `-30s`, `-10s`, `+10s`, `+30s`.
- These buttons move the selected playback position by the specified number of seconds and move the waveform view to that position.
- Audio processing and SRT export timing logic are unchanged from v1.0.3.

## v1.0.3

- Changed the `End` / `終端へ` navigation behavior.
- Pressing `End` now moves the waveform view to the end point while placing the selected playback position near the center of the visible window, instead of selecting the exact end point.
- This makes it possible to press Play immediately after moving to the end area and hear the ending/fade-out section.
- Zoom level is still preserved.

## v1.0.2

- When a new SRT file is loaded, the SRT list selection and scroll position now reset to the top of the list.
- This makes the next song workflow easier when the previous task ended near the bottom of the SRT list.
- No audio processing or SRT export timing logic was changed.


## v1.0.1

- Released the GitHub package as v1.0.1.
- No functional changes from v1.0.0.
- The application title, HTML metadata, and documentation version labels were updated to v1.0.1.


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
- Added whole-second navigation buttons (`Sec−` / `Sec+`) for snapping the selected position to exact second boundaries.
- Added fixed selected-position playback behavior.
  - Playback starts from the last selected position.
  - Stopping returns the playback cursor to the selected position.
- Added start-position workflow.
  - User-selected start position.
  - Actual cut position calculated as start position minus fade-in length.
  - Short fade-in options for click-noise reduction.
- Added output-time waveform mode after the start position is set.
- Added safe limit line, default `179.700` seconds.
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
