# ScaleUP Platform Converter

Public download and update repository for the Windows x64 portable application.
Application source code and user data are not stored in this repository.

## Download

Published packages appear on the [Releases page](https://github.com/Arijevac/scaleup-platform-converter-releases/releases).
Extract the complete ZIP and open `ScaleUP Platform Converter/ScaleUP Platform Converter.exe`.
No Python or Java installation is required. There is no Windows installer.

## Updates

The portable application checks for a newer stable release once at startup.
Choose **Update now** or **Later**. Updates verify the archive SHA-256 and complete file inventory,
wait for active technical processing, retain the previous application folder, and attempt recovery
if the new version does not confirm startup. Settings and protected ChatGPT sign-in records
remain in the current Windows user's LocalAppData folder.

Each published version includes a portable ZIP, matching `.sha256` file and `scaleup-update.json`.
Do not rename or replace these release assets. A new version must use a new release tag.
Keep your videos and other personal files outside the application folder.
