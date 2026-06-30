# Release Review: Music Clip & SRT Cutter for Short Movie v1.0.0

This document summarizes the review performed before packaging Music Clip & SRT Cutter for Short Movie v1.0.0.

## Scope

v1.0.0 is the initial public release. It packages the completed HTML5 prototype as a GitHub-ready MIT release.

The release target is a local browser app that creates short-movie WAV/SRT assets from:

- one full-length MP3 or WAV music file
- one finished full-length SRT subtitle file

## Reviewed areas

### Application versioning

- Added `v1.0.0` to the browser title.
- Added `v1.0.0` to the visible application title through the Japanese and English UI dictionary.
- Added an `app-version` meta tag with `1.0.0`.

### File structure

Confirmed release package contains:

- `index.html`
- `README.md`
- `USER_GUIDE.md`
- `CHANGELOG.md`
- `RELEASE_REVIEW.md`
- `LICENSE`

### UI workflow

Reviewed the main workflow:

- audio/SRT selection buttons
- drag-and-drop loading area
- SRT row navigation
- waveform click navigation
- selected-position playback model
- start-position setting
- output-time waveform display
- safe limit line
- fade-out start and end markers
- terminal subtitle editing
- separate WAV and SRT export buttons
- Undo button and `Ctrl+Z`
- Japanese / English UI switching
- tooltip coverage for major controls

### Subtitle conversion behavior

Reviewed the intended SRT behavior:

- Original SRT is treated as the trusted timing master.
- Timestamps are converted using actual cut position.
- Negative start times are rounded to `00:00.000`.
- Subtitles after the end point are omitted.
- The subtitle overlapping the end point can be kept, edited, or omitted by editing/clearing the terminal text field.
- Subtitle numbers are regenerated from 1.

### Audio behavior

Reviewed the intended audio behavior:

- MP3/WAV input is decoded in the browser.
- Playback preview reflects the current fade-in and fade-out settings.
- The actual output range starts at the calculated cut position.
- The output end point cannot exceed the safe limit.
- WAV export writes 16-bit PCM WAV.

### Documentation

Created or updated:

- `README.md`
- `USER_GUIDE.md`
- `CHANGELOG.md`
- `RELEASE_REVIEW.md`
- `LICENSE`

The user guide includes detailed workflow, technical assumptions, limitations, troubleshooting, and GitHub Pages notes.

## Technical checks

- Extracted embedded JavaScript from `index.html` and ran `node --check` successfully.
- Confirmed release-facing files are UTF-8 text files.
- Confirmed ZIP package generation completed successfully.

## Known limitations

- MP3 decoding depends on browser support.
- Output audio is WAV only; MP3 export is not included.
- The app is intended for a single full-length song, not album-length or long-form audio.
- The original SRT must already be complete and reliable.
- The app does not perform automatic subtitle generation or full retiming.
- Browsers cannot automatically search the source file's folder for a same-name SRT unless the user explicitly provides the SRT file.
- Drag-and-drop can load only the files the user drops into the app.
- Browser download behavior may require separate confirmation for WAV and SRT saves.

## Release assessment

The package is suitable for the v1.0.0 public release and GitHub Pages publication.
