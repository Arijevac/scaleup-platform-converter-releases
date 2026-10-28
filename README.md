# ScaleUP Platform Converter

Official Windows x64 and Apple Silicon Mac **downloads and updates**. Current release:
[1.6.0](https://github.com/Arijevac/scaleup-platform-converter-releases/releases/tag/v1.6.0).
Windows is the established portable edition; the Mac edition remains a preview.

Version 1.6.0 adds Automatic / End fit / Speed fit duration correction, reliable
AI evidence mapping through OTSM ad/master exports, amber Mixed leading-1
warnings, clearer tab indicators and a separate Measurements view. Universal
project output now requires stereo; new OTSM slates are black and accept
hyphens in ISCI/Ad-ID values. Phone recognition and GPT classification remain
unchanged. See the release notes for details.
Windows and Mac use the same shared implementation with separate native adapters.

This repository contains release artifacts and download documentation. Application
source is maintained separately in a **private repository**; the application is
not publicly open source. Client videos, sign-in records and review evidence are
not stored in either repository.

## Download and use

**Windows:** download the versioned windows-x64-portable ZIP from [Releases](https://github.com/Arijevac/scaleup-platform-converter-releases/releases),
extract the complete folder, and run **ScaleUP Platform Converter.exe**. Keep its
EXE and accompanying files together. No installer, Python or Java installation
is required. Keep videos and personal files outside the application folder.

**Apple Silicon Mac (M1/M2/M3 and later):** download the macos-arm64 DMG, open it,
drag **ScaleUP Platform Converter.app** into Applications and launch the installed
copy. The ZIP is an alternative app archive. No Python, Homebrew or emulator is
needed. Minimum macOS 14.4; automated native tests use macOS 15. Editor acceptance
on M3/macOS 26, native folder permissions and real ChatGPT login remain pending.
Intel Macs are not supported by this build.

The Mac edition has an ad-hoc signature without Apple Developer ID or
notarization. Gatekeeper/company policy may block first launch; have the official
test artifact approved through normal macOS/company processes. Keep system
protections enabled. Connect ChatGPT separately on Mac; Keychain protects its
sign-in. The app includes a Mac installation and editor checklist.

Open videos in separate tabs, choose a platform and click Convert. Original backups are
enabled by default in Videos / ScaleUP Backups on Windows and Movies / ScaleUP Backups on Mac. Header Backup settings changes the location or disables future backups. Technical conversion
is local. Confirmed optional AI checks send sampled video frames to OpenAI when connected; see DATA_HANDLING.md inside the portable folder.

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
shared queue: one local processing phase and three GPT requests by default.
AI settings offers a saved 2-5 request slider; 3 is recommended, while 5 is
experimental. Other editors/apps using the same account add to its total load. Use
`+` / **Ctrl+T** to add a tab and **X / Ctrl+W** to close it, up to eight tabs. Closing the
last tab opens a fresh empty tab. Reopening a video resets its tab after cleanup
and runs new analysis and selected checks. Output names, evidence and settings
belong to their video; shared output reservations prevent collisions.

Header AI settings contains the shared account/model, parallel-request limit and
Appearance settings. Each new video offers separate Content and Phone panels:
confirm the checks you want or Skip. Logo/website and ADVERTISEMENT checks work
on every platform and appear in the table only after confirmation. Each video's
AI checks contains manual Run now actions and evidence, including after Skip.
Phone checking asks to confirm/edit a complete filename number, enter one, or
skip that video. Completed phone audio findings can appear while visual review
continues. Positive results also wait for active conversion validation.

## Optional phone checks

**AI checks > Phone number** is available for every platform. Confirm the
expected number once; results separately check visible digits, graphic leading 1,
spoken digits and consistent use of a spoken leading 1. Graphics and speech may
use different forms. Content and phone reviews can run in parallel after technical
analysis, without waiting for each other or blocking technical Convert.

English speech recognition runs locally on the CPU. First use automatically
downloads pinned, SHA-256-verified speech support (about 497 MB on Windows or
488 MB on Mac), outside the app and reused across updates. Windows uses
LocalAppData; Mac uses the application data folder in Library/Application Support. Audio is not uploaded;
sampled frames and transcript text are sent to OpenAI using the connected ChatGPT
plan. Recognition and frame sampling can miss content. Results include evidence,
require review when uncertain, and never edit the creative. See the included
docs/PHONE_CHECKS.md and DATA_HANDLING.md.

## Software status — 1.6.0

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

## OTSM output and Evidence

OTSM supports nominal 90- and 120-second ads. Choose Complete master or Ad only
output; Ad only skips slate details and leader/tail packaging. Complete master
retains the specified slate/black layout. Kayzen nominal 120 follows its existing
119-second delivery rule and bounded duration fit.

Evidence uses red Mismatch and amber Review labels, issue counts, first-issue
focus and Previous/Next issue navigation. Saved explanations appear below the
image. These display improvements do not change detection or verdict rules.

## Updates and integrity

The app checks at startup and every four hours. An inline notice waits until
technical processing, AI work and dialogs finish; it does not interrupt editing
or take focus. About > **Check for updates** runs a manual check without
installing. Choose **Update now** or **Later** in the main notice. Installation
waits for work across all tabs to finish. After restart a fresh empty tab opens;
reopen videos as needed.

On Windows, updates validate SHA-256 and the complete file inventory, replace managed files
inside the same program folder, and keep previous program files under
`%LOCALAPPDATA%/ScaleUP Platform Converter/updates/<id>/previous-version`.
Startup failure attempts recovery. Settings and protected ChatGPT sign-in stay
in LocalAppData. The old folder-swap transition applies only to updates started
by versions 0.1.15 and earlier.

Mac updates use their own manifest, safe bundle inventory and native code-signature
checks. Replacement/restart and failed-startup rollback preserve settings,
Keychain sign-in and separately stored model/evidence data. Windows and Mac
packages are built from the same version; their native adapters remain separate.

Release 1.5.0 contains the Windows ZIP and Mac ZIP/DMG, matching `.sha256` files,
Windows `scaleup-update.json` and Mac `scaleup-update-macos-arm64.json`. Never rename/replace published assets; new builds use new
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
