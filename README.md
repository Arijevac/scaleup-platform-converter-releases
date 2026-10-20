# ScaleUP Platform Converter

Public download and update repository for the Windows x64 portable application.
Application source code and user data are not stored in this repository.

## Download

Published packages appear on the [Releases page](https://github.com/Arijevac/scaleup-platform-converter-releases/releases).
Extract the complete ZIP and open `ScaleUP Platform Converter/ScaleUP Platform Converter.exe`.
No Python or Java installation is required. There is no Windows installer.

## Updates

The portable application checks at startup and then every four hours, without overlapping requests.
An inline notice waits until technical processing, AI work and dialogs have finished.
It does not pop up or take focus. Choose **Update now** or **Later**; Later hides that release version
for the rest of the session. Updates verify the archive SHA-256 and complete file inventory,
wait for active technical processing, update individual files inside the original folder without renaming it,
and keep a verified backup in `%LOCALAPPDATA%/ScaleUP Platform Converter/updates/<id>/previous-version`.
They attempt recovery in the same original folder if the new version does not confirm startup.
The in-place method is bundled in 0.1.16: an update started by 0.1.15 or earlier still uses its old
folder-swap helper once; subsequent updates started by 0.1.16 use the new method.
Settings and protected ChatGPT sign-in records
remain in the current Windows user's LocalAppData folder.

Each published version includes a portable ZIP, matching `.sha256` file and `scaleup-update.json`.
Do not rename or replace these release assets. A new version must use a new release tag.
Keep your videos and other personal files outside the application folder.
