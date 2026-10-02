# Music Assets - drive-releases

This repository provides music assets for the music streaming application.

Audio files are distributed through **GitHub Releases** rather than the normal Git repository history.

## Current Release

- **Release Tag:** `music-v1.0.0`
- **Release Title:** Music Assets v1.0.0
- **Release URL:** https://github.com/girishlade111/drive-releases/releases/tag/music-v1.0.0
- **Total Songs:** 26

## How It Works

- Local audio files are stored in the `songs/` folder (local only, **not** committed to Git).
- All audio files are uploaded as **GitHub Release Assets** under the release `music-v1.0.0`.
- The streaming application uses the direct Release Asset URLs as audio sources.

## Files

- `songs.json` — Music catalog with `id`, `title`, `genre`, and `audioUrl` for every song. Used by the streaming app.
- `music-release.json` — Release metadata including repository, tag, and per-song asset URLs and sizes.
- `songs/` — Local source directory (**ignored via `.gitignore`**, never pushed to Git).
- `SnapTube Audio/` — Original download folder (also ignored).

## GitHub Release Assets

All 26 songs are available as Release Assets:

Browse: https://github.com/girishlade111/drive-releases/releases/tag/music-v1.0.0

Example URL pattern:
```
https://github.com/girishlade111/drive-releases/releases/download/music-v1.0.0/<asset-name>.mp3
```

> **Note:** Asset filenames are sanitized by GitHub (spaces, Unicode, special characters become `.`). The manifest files map original filenames to the actual sanitized asset URLs.

## Usage

```json
// songs.json entry
{
  "id": "ram-siya-ram-full-song-sachet-tandon-...",
  "title": "Ram Siya Ram (Full Song) Sachet Tandon ...",
  "genre": "Unknown",
  "audioUrl": "https://github.com/girishlade111/drive-releases/releases/download/music-v1.0.0/Ram.Siya.Ram.Full.Song....mp3"
}
```

## Verification

- `.gitignore` contains `songs/` and `SnapTube Audio/` to prevent accidental commits.
- Run `git status` — no `.mp3` files should ever be staged.
- Verify release: `gh release view music-v1.0.0 --json assets --jq ".assets[].name"`

---
*Generated via automated GitHub Releases workflow — audio files are NOT stored in Git history.*

---
Built by [Girish Lade](https://ladestack.in) — https://ladestack.in
