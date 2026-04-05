# Cipher Video Downloader

Version: `2.0.0`

This repository still uses the older GitHub repo name `Cipher-YT-Downloader`, but the current desktop product is now branded as `Cipher Video Downloader`.

## Overview

Cipher Video Downloader is a Windows desktop downloader built for a faster, cleaner media workflow.

The current `Version 2.0.0` release keeps the Qt desktop UI and adds tray persistence, maximized launch behavior, and refreshed extension branding:
- redesigned `Downloads` page with preview, active transfer, queue, and recent results
- light mode and dark mode
- queue persistence and general app-state persistence
- toast feedback, About dialog, and cleaner branding
- updated Chrome companion extension for browser handoff into the desktop app
- broader real-world support through `yt-dlp`, while keeping the browser extension focused on YouTube

## Tech Stack

- Python
- PySide6
- yt-dlp
- FFmpeg
- PowerShell release scripts
- Chrome Extension (Manifest V3)

## Release Assets

Recommended GitHub release assets for `Version 2.0.0`:

- `Cipher.Video.Downloader.Setup.2.0.0.exe`
- `Cipher Video Downloader Version 2.0.0.exe`
- `Cipher-Video-Downloader-Version-2.0.0-win64.zip`
- `SHA256SUMS.txt`

## Main Features

- modern Qt desktop UI
- video and audio download profiles
- subtitle and auto-subtitle support
- playlist range controls
- save-folder selection
- queue management inside the Downloads page
- recent results history with quick actions
- Chrome handoff with saved profile support

## Run From Source

Install dependencies:

```powershell
pip install PySide6 yt-dlp
```

Run:

```powershell
python .\cipher_yt_downloader_qt.py
```

Legacy app:

```powershell
python .\cipher_yt_downloader.py
```

## Build Release

Use the included release script:

```powershell
powershell -ExecutionPolicy Bypass -File .\build_release.ps1
```

This builds the `Version 2.0.0` Windows executable with:
- installer output for easier upgrades
- bundled app assets
- bundled `yt-dlp`
- bundled `FFmpeg`
- bundled unpacked Chrome companion extension folder for manual loading in Chrome
- Windows version metadata

## Chrome Extension

The companion extension lives in:

```text
cipher_chrome_extension
```

It is now branded as `Cipher Video Downloader Companion`.

Installer users can also load the bundled unpacked extension from:

```text
%LOCALAPPDATA%\Programs\Cipher Video Downloader\Chrome Extension\Cipher Video Downloader Companion
```

## Notes

- the repo name is still old for continuity, but the current product name is `Cipher Video Downloader`
- the website project card and fallback release links should point to the installer-first `v2.0.0` GitHub release
- if browser handoff is already configured, re-running `register_cipheryt_protocol.ps1` after upgrading is recommended
