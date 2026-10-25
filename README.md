# ScaleUP Platform Converter

Official Windows x64 **portable downloads and updates**. Current stable release:
[1.1.0](https://github.com/Arijevac/scaleup-platform-converter-releases/releases/tag/v1.1.0).

This repository contains release artifacts and download documentation. Application
source is maintained separately in a **private repository**; the application is
not publicly open source. Client videos, sign-in records and review evidence are
not stored in either repository.

## Download and use

Download the versioned portable ZIP from [Releases](https://github.com/Arijevac/scaleup-platform-converter-releases/releases),
extract the complete folder, and run **ScaleUP Platform Converter.exe**. Keep its
EXE and accompanying files together. No installer, Python or Java installation
is required. Keep videos and personal files outside the application folder.

Open videos in separate tabs, choose a platform and click Convert. Original backups are
enabled by default in Windows Videos / ScaleUP Backups. Header Backup settings changes the location or disables future backups. Technical conversion
is local. Selected Roku AI checks send sampled video frames to OpenAI when connected; see DATA_HANDLING.md inside the portable folder.

## Multiple videos and optional AI checks

Version 1.1.0 adds a refreshed light interface, independent video tabs and a
shared queue: one local processing phase and two GPT requests at a time. Use
`+` / **Ctrl+T** to add a tab and **X / Ctrl+W** to close it, up to eight tabs. Closing the
last tab opens a fresh empty tab. Reopening a video resets its tab after cleanup
and runs new analysis and selected checks. Output names, evidence and settings
belong to their video; shared output reservations prevent collisions.

Header AI settings contains the shared account/model and saved automatic choices
for new videos. All AI checks are optional, initially enabled. Each video's AI
checks contains its selections, manual runs and evidence. Roku checks apply to
Roku; phone checks are available on all platforms. Automatic phone checking asks
to confirm/edit a complete filename number, enter a number, or skip that video.
Findings stay in progress until final review and conversion validation settle.

## Optional phone checks

**AI checks > Phone number** is available for every platform. Confirm the
expected number once; results separately check visible digits, written format,
spoken digits and consistent use of a spoken leading 1. Graphics and speech may
use different forms. Roku and phone reviews can run in parallel after technical
analysis, without waiting for each other or blocking technical Convert.

English speech recognition runs locally on the CPU. First use automatically
downloads about 497 MB of pinned, SHA-256-verified speech support into LocalAppData,
outside the program folder and reused across updates. Audio is not uploaded;
sampled frames and transcript text are sent to OpenAI using the connected ChatGPT
plan. Recognition and frame sampling can miss content. Results include evidence,
require review when uncertain, and never edit the creative. See the included
docs/PHONE_CHECKS.md and DATA_HANDLING.md.

## Updates and integrity

The app checks at startup and every four hours. An inline notice waits until
technical processing, AI work and dialogs finish; it does not interrupt editing
or take focus. Choose Update now or Later.

Updates validate SHA-256 and the complete file inventory, replace managed files
inside the same program folder, and keep previous program files under
`%LOCALAPPDATA%/ScaleUP Platform Converter/updates/<id>/previous-version`.
Startup failure attempts recovery. Settings and protected ChatGPT sign-in stay
in LocalAppData. The old folder-swap transition applies only to updates started
by versions 0.1.15 and earlier.

Each release contains a versioned ZIP, its `.sha256` file and
`scaleup-update.json`. Never rename/replace published assets; new builds use new
versions. **The EXE is unsigned.** Hashes verify agreement with published
metadata, not independent publisher identity or freedom from vulnerabilities.
Do not disable Windows protection to run the app; company IT can review the
official artifact under its normal policy.

## Notices and support

SECURITY.md, DATA_HANDLING.md, THIRD_PARTY_NOTICES.md, dependency inventory and
license texts are included in the portable folder. Complete matching native
dependency source/build-material provision remains a tracked task in the
notices; a completed license/security audit is not claimed.

Report suspected security issues to the maintainer through an existing private
company channel. Do not post credentials, client material or unredacted logs in
public issues.
