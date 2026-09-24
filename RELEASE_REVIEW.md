# Release Review: Music Clip & SRT Cutter for Short Movie v1.0.5

## v1.0.5 review note

This release is a small workflow update based on v1.0.4. It expands drag-and-drop input and slightly increases the safety margin below the three-minute limit. Audio/SRT cutting logic is otherwise unchanged.

## Scope

The release target remains a local browser app that creates short-movie WAV/SRT assets from:

- one full-length MP3 or WAV music file
- one finished full-length SRT subtitle file

## v1.0.5 changes

- Updated the browser title, visible application title, and `app-version` meta tag to `v1.0.5`.
- The loading-status message area below the visible drop zone now accepts MP3/WAV/SRT drag-and-drop input using the same handler as the main drop zone. No additional UI text was added.
- Changed the default safe duration limit from `179.800` seconds to `179.700` seconds in the UI, internal default/fallback values, tooltips, and documentation.
- Updated README, user guide, changelog, and release review version labels to `v1.0.5`.
- Rebuilt the MIT GitHub release ZIP as `music_clip_srt_cutter_for_short_movie_v1_0_5_mit.zip`.

## File structure

Release package contains:

- `index.html`
- `README.md`
- `USER_GUIDE.md`
- `CHANGELOG.md`
- `RELEASE_REVIEW.md`
- `LICENSE`

## Reviewed areas

- Confirmed the secondary drop target calls the same `loadDroppedFiles()` routine as the visible drop zone.
- Confirmed document-level drag/drop default suppression remains active.
- Confirmed the safe-limit input default and internal fallback/default values use `179.700` / `179.7`.
- Confirmed JavaScript syntax with `node --check` on the extracted script.
- Confirmed release package file structure and version labels.

## Known limitations

- Runtime audio playback and browser UI behavior should still be verified manually in Chrome or Edge with real MP3/WAV and SRT files.
- MP3 decoding depends on browser support.
- Output remains WAV only.

## Release judgment

v1.0.5 is suitable as a small maintenance release after normal manual browser verification of both drop surfaces and the 179.700-second safe-limit behavior.
