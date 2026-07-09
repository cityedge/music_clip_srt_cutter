# Release Review: Music Clip & SRT Cutter for Short Movie v1.0.4

## v1.0.4 review note

This release is a small usability update based on v1.0.3. It changes SRT row navigation to use the standard zoom level automatically and adds ±10 / ±30 second movement buttons beside Undo. Audio processing and SRT export timing logic are unchanged from v1.0.3.

## Scope

v1.0.4 targets the same local browser workflow as v1.0.3. The release target is a local browser app that creates short-movie WAV/SRT assets from:

- one full-length MP3 or WAV music file
- one finished full-length SRT subtitle file

## v1.0.4 changes

- Updated the browser title, visible application title, and `app-version` meta tag to `v1.0.4`.
- Updated README, user guide, changelog, and release review version labels to `v1.0.4`.
- Changed SRT row clicks so they move to the subtitle start and set the waveform display to standard zoom.
- Added `-30秒`, `-10秒`, `+10秒`, and `+30秒` movement buttons to the left of the Undo button.
- Preserved the existing selected-position playback model.
- Rebuilt the MIT GitHub release ZIP as `music_clip_srt_cutter_for_short_movie_v1_0_4_mit.zip`.

## File structure

Confirmed release package contains:

- `index.html`
- `README.md`
- `USER_GUIDE.md`
- `CHANGELOG.md`
- `RELEASE_REVIEW.md`
- `LICENSE`

## Reviewed areas

### UI workflow

Reviewed the main workflow inherited from v1.0.3:

- audio/SRT selection buttons
- drag-and-drop loading area
- SRT row navigation
- waveform click navigation
- selected-position playback model
- start-position setting
- output-time waveform display
- safe limit line
- end-point navigation
- whole-second navigation buttons
- ±10 / ±30 second navigation buttons
- Undo placement and enable/disable state
- Japanese / English labels and tooltips for the new controls

### Implementation checks

- Confirmed JavaScript syntax with `node --check` on the extracted script.
- Confirmed the new button IDs are present in the DOM mapping.
- Confirmed the new buttons are enabled/disabled with audio loading state.
- Confirmed the new navigation function clamps movement inside the current timeline and respects the output end point when available.
- Confirmed SRT row click navigation uses standard zoom rather than preserving the previous zoom.

## Known limitations

- Runtime audio playback and browser UI behavior should still be verified manually in Chrome or Edge with real MP3/WAV and SRT files.
- MP3 decoding depends on browser support.
- Output remains WAV only.

## Release judgment

v1.0.4 is suitable as a small usability release if manual browser testing confirms the SRT row standard zoom behavior and ±10 / ±30 second movement buttons work as expected.
