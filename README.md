# Music Clip & SRT Cutter for Short Movie v1.0.0

Music Clip & SRT Cutter for Short Movie は、フルコーラスの音源ファイル（MP3 / WAV）と、その曲に対応する完成済みSRT字幕から、ショート動画用のWAV音源とSRT字幕を作成するためのローカルHTMLアプリです。

This is a local browser-based HTML5 app for creating short-movie WAV/SRT assets from one full-length music file and a finished SRT subtitle file.

## Main features

- Single-file local HTML app
- MP3 / WAV input
- SRT input
- Drag-and-drop loading for audio and SRT files
- Waveform display with click-to-select positioning
- SRT row click navigation
- Start-point selection with short fade-in
- Safe duration limit, default `179.800` seconds
- Free end-point selection within the safe limit
- Two-marker fade-out editing: fade start and end point
- Playback preview reflecting fade-in and fade-out
- Terminal subtitle handling by edited text field
  - keep unchanged
  - edit and keep
  - clear the field to omit the overlapping subtitle
- 16-bit PCM WAV output
- Short SRT output with renumbering
- Japanese / English UI switching
- Tooltip help for major UI elements
- Undo support for editing operations

## Recommended environment

Recommended:

- Windows 11
- Google Chrome or Microsoft Edge

The app uses browser APIs such as File API, Drag and Drop API, Web Audio API, Canvas, and Blob download. MP3 decoding depends on the browser's audio decoding support.

## Important workflow concept

This app assumes that the original full-length SRT is already complete and reliable. It does not try to retime the whole subtitle file. Instead, it treats the original SRT as the timing master and converts timestamps using the actual audio cut position.

```text
short subtitle time = original SRT time - actual cut position
```

If the first remaining subtitle would start before `00:00.000`, the start time is rounded to `00:00.000` because SRT cannot represent negative time.

## Files in this repository

- `index.html` — application body
- `README.md` — project overview
- `USER_GUIDE.md` — detailed user guide
- `CHANGELOG.md` — version history
- `RELEASE_REVIEW.md` — release review notes
- `LICENSE` — MIT License

## Basic use

1. Open `index.html` in Chrome or Edge.
2. Load or drop one MP3/WAV file and the matching SRT file.
3. Click an SRT row near the desired start point.
4. Use the waveform and playback to select the start position.
5. Click `現在位置を開始位置にする` / `Set selected position as start`.
6. Select an end point and a fade-out start point.
7. Adjust the terminal subtitle text if needed.
8. Save the WAV and SRT separately.

See `USER_GUIDE.md` for detailed operation and technical notes.

## Privacy

The selected audio and SRT files are processed locally in the browser. This app does not upload audio or subtitle files to a server.

## License

MIT License. See `LICENSE`.
