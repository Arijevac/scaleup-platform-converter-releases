# ScaleUP Platform Converter

Official Windows x64 **portable downloads and updates**. Current stable release:
[1.3.0](https://github.com/Arijevac/scaleup-platform-converter-releases/releases/tag/v1.3.0).

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

## Appearance and About

Version 1.2.0 adds saved Light and Dark themes under **AI settings > Appearance > Theme**.
Switch immediately without restarting or changing video jobs, AI findings or
exported media. The agency logo is blue in Light and white in Dark.

Click the header version badge for **About**, release notes, component licenses,
data/AI documentation and team/company contacts. **Copy technical info** copies
runtime versions and display settings without video paths or account details.
The About window stays available while processing continues.

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
Completed phone audio findings can appear while visual review continues. Positive
results also wait for active conversion validation.

## Optional phone checks

**AI checks > Phone number** is available for every platform. Confirm the
expected number once; results separately check visible digits, graphic leading 1,
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

## Software status — 1.3.0

Based on internal regression tests and the team's manual advertising-video collection:

- **Technical file preparation is very reliable** in the supported, tested platform
  workflows: FPS, dimensions, format/codecs, video/audio bitrates, specified audio
  targets and bounded duration alignment. Actual output is validated before source
  replacement, with original backups enabled by default.
- **AI content review has reliably identified clear real errors** in the tested
  collection. Occasional **false-positive findings** flag correct content for
  review, especially around animations or recognition uncertainty. Editors retain
  the final visual/listening decision; AI findings do not block technical Convert.
- AI review is sampled and recognition-based. A PASS does not certify the absence
  of every error; false negatives are possible and formal error rates have not
  been established. Rerun after external edits and review important phone/caption
  endings after trimming. The package includes docs/SOFTWARE_STATUS.md.

Version 1.3.0 adds chronological animation/sequential-caption checks, local
confirmation of suspect speech, punctuation-independent leading-1 consistency,
less TTY 711 clutter and bounded recovery of invalid replies/server overloads.

## Updates and integrity

The app checks at startup and every four hours. An inline notice waits until
technical processing, AI work and dialogs finish; it does not interrupt editing
or take focus. About > **Check for updates** runs a manual check without
installing. Choose **Update now** or **Later** in the main notice. Installation
waits for work across all tabs to finish. After restart a fresh empty tab opens;
reopen videos as needed.

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
