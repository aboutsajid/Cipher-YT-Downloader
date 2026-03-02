# Cipher YT Downloader

<img width="1920" height="1032" alt="Screenshot 2026-03-02 113720" src="https://github.com/user-attachments/assets/67ecb9b7-f602-4e2f-a3e9-e144d21f0197" />


A powerful Windows YouTube downloader with smart format selection, subtitle support, playlist controls, and optional Chrome extension handoff.

Built with Python, yt-dlp, ffmpeg, and CustomTkinter.

✨ Overview

Cipher YT Downloader is a modern Windows desktop application designed to simplify high-quality video and audio downloads with intelligent format handling and clean UI controls.

It combines:

Smart quality selection

Subtitle extraction

Playlist range control

Seamless Windows installer support

Optional Chrome extension integration

Designed for performance, simplicity, and reliability.

🚀 Features
🎯 Smart Format Selection

Automatically selects the best compatible video/audio format

Intelligent merging via FFmpeg

Clean output naming

📝 Subtitle Support

Download available subtitles

Supports embedded or separate subtitle files

Automatic detection of available languages

📚 Playlist Controls

Download entire playlists

Download selected range (e.g., 5–15)

Skip unwanted entries

🖥 Modern Windows Desktop UI

Built using CustomTkinter

Clean layout and responsive design

Beginner-friendly workflow

🌐 Chrome Extension Handoff (Optional)

Send YouTube links directly from Chrome

One-click transfer to the desktop app

Custom protocol integration

🏗 Tech Stack

Python

yt-dlp

FFmpeg

CustomTkinter

Inno Setup (Windows Installer)

PowerShell build scripts

📦 Installation
Option 1 — Recommended (Installer)

Go to the Releases section.

Download the latest installer:

Cipher_YT_Downloader_Setup_<version>.exe

Run the installer.

Launch Cipher YT Downloader from Start Menu.

No Python required for installer users.

Option 2 — Run from Source

Requirements:

Windows 10/11

Python 3.10+

FFmpeg installed and added to PATH

Clone and run:

git clone https://github.com/<your-username>/cipher-yt-downloader.git
cd cipher-yt-downloader
python cipher_yt_downloader.py
📂 Repository Structure

Source code kept in repository:

cipher_app/
cipher_chrome_extension/
tests/
cipher_yt_downloader.py
Cipher YT Downloader.spec
Cipher_YT_Downloader_Setup.iss
build_installer.ps1
build_extension_zip.ps1
register_cipheryt_protocol.ps1
unregister_cipheryt_protocol.ps1
README.md
SETUP.md
EULA.txt

Large build artifacts are not stored in Git history and are published via GitHub Releases:

dist/
build/
upload_bundle_*/
*.exe
*.zip
🔒 Legal Notice

This software is provided as a general-purpose media downloading tool.
Users are responsible for ensuring they comply with all applicable laws and platform terms of service when using this software.

🏷 Suggested GitHub About Section

Name:
cipher-yt-downloader

Description:
Windows YouTube downloader with smart format selection, subtitles, playlist controls, and optional Chrome extension handoff.

Suggested Topics:

python
yt-dlp
ffmpeg
youtube-downloader
customtkinter
windows-app
chrome-extension
🏁 First Release Recommendation

Tag: v1.0.0
Title: Cipher YT Downloader v1.0.0

Release Notes:
Initial public release with:

Desktop Windows app

Smart format selection

Subtitle support

Playlist range controls

Chrome extension handoff support

Release Assets:

dist\installer\Cipher_YT_Downloader_Setup_v1.0.0.exe
dist\cws\Cipher_YT_Downloader_Extension_v1.0.0.zip
🛠 Build & Packaging

PyInstaller via .spec

Inno Setup installer via .iss

PowerShell automation scripts included

See SETUP.md for detailed build instructions.

📄 License & EULA

See EULA.txt for full terms.

💬 Support

Website: <your-website-or-youtube-link>
Support: <your-support-email-or-link>

If you'd like, I can now:

Write a high-converting GitHub description (short SEO optimized version)

Create a professional SETUP.md

Or upgrade this into a more “enterprise-grade” README with badges, screenshots section, and branding tone**

2

Here is a professional, structured, production-ready SETUP.md for your repository.

You can paste this directly into SETUP.md.

Cipher YT Downloader – Setup & Build Guide

This document explains how to:

Run the app from source

Build the standalone executable

Build the Windows installer

Build the Chrome extension package

Register the custom protocol handler

1️⃣ Development Setup (Run From Source)
Requirements

Windows 10 / 11

Python 3.10+

FFmpeg installed and added to PATH

Git (optional but recommended)

Install Dependencies

From project root:

python -m venv venv
venv\Scripts\activate
pip install --upgrade pip
pip install -r requirements.txt

If no requirements.txt exists, install manually:

pip install yt-dlp customtkinter pillow pyinstaller
Ensure FFmpeg Is Installed

Download FFmpeg and add it to your system PATH.

Verify:

ffmpeg -version

If installed correctly, version information will display.

Run Application
python cipher_yt_downloader.py
2️⃣ Build Standalone Executable (PyInstaller)

The project includes:

Cipher YT Downloader.spec
Build Command
pyinstaller "Cipher YT Downloader.spec"

After build completes, output will be located in:

dist/

Test the generated .exe before building the installer.

3️⃣ Build Windows Installer (Inno Setup)

The installer script:

Cipher_YT_Downloader_Setup.iss
Option A – Using Inno Setup GUI

Install Inno Setup

Open .iss file

Click Build

Option B – Command Line
"C:\Program Files (x86)\Inno Setup 6\ISCC.exe" Cipher_YT_Downloader_Setup.iss

Output installer will be located in:

dist\installer\
4️⃣ Automated Installer Build (Recommended)

Use included PowerShell script:

.\build_installer.ps1

This script:

Builds the executable

Runs Inno Setup

Outputs final installer

5️⃣ Build Chrome Extension Package

Extension source folder:

cipher_chrome_extension/

To build zip package:

.\build_extension_zip.ps1

Output:

dist\cws\

Upload the generated .zip to:

Chrome Web Store (if publishing)

GitHub Releases

6️⃣ Register Custom Protocol (Optional)

Cipher supports a custom protocol for Chrome extension handoff:

cipheryt://
Register Protocol

Run as Administrator:

.\register_cipheryt_protocol.ps1
Unregister Protocol
.\unregister_cipheryt_protocol.ps1
7️⃣ Recommended Release Workflow

For production release:

Step 1

Update version in:

App config

Installer script

Extension manifest (if needed)

Step 2

Run:

.\build_installer.ps1
.\build_extension_zip.ps1
Step 3

Create GitHub Release:

Tag: vX.X.X
Title: Cipher YT Downloader vX.X.X

Upload:

dist\installer\Cipher_YT_Downloader_Setup_vX.X.X.exe
dist\cws\Cipher_YT_Downloader_Extension_vX.X.X.zip

Do NOT commit:

dist/

build/

.exe

.zip

These should only exist in Releases.

8️⃣ Troubleshooting
FFmpeg Not Detected

Ensure it is in system PATH

Restart terminal after installation

PyInstaller Errors

Delete build/ and dist/

Re-run build

Ensure virtual environment is activated

Extension Not Connecting

Ensure protocol is registered

Confirm manifest permissions

Check Windows default app handler

9️⃣ Clean Build Reset

If you need a full clean rebuild:

rmdir /s /q build
rmdir /s /q dist
pyinstaller "Cipher YT Downloader.spec"
🔐 Security & Best Practices

Do not store API keys in repository

Use GitHub Releases for binary distribution

Sign installer for production releases (recommended)

Test installer on clean Windows VM before publishing

📦 Production Checklist

Before releasing:

 Version updated everywhere

 Fresh build completed

 Installer tested

 Extension tested

 Protocol tested

 Release notes written

 Assets uploaded to GitHub Releases

For additional technical details, see:

README.md

EULA.txt
