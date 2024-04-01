---
hide:
  - navigation
---

# Release Notes

## Version 1.2.1 (2020-06-17)

`Available with InstallForge version 1.4.2`

* `Fix` Fixed false positive issues with different anti-malware applications

## Version 1.2.0 (2020-05-10)

`Available with InstallForge version 1.4.1`

* `Feature` Support for a new command: `ShellExecute`
* `Enhancement` Several improvements for the update engine with better error handling and increased robustness
* `Enhancement` The update engine now detects the [BOM] of the updatescript.ini file automatically (either no [BOM] or [UTF-8] [BOM] is valid)
* `Enhancement` The dialog can now be minimized
* `Enhancement` Improved `DownloadFile` command: The second parameter can now contain an optional file name which will be used for the downloaded file
* `Enhancement` Improved `DeleteFiles` command: read-only files are also deleted
* `Enhancement` Improved `DeleteDirectory` command: read-only files are also deleted
* `Fix` Fixed several UI issues due to DPI Awareness

## Version 1.1.0 (2020-04-24)

`Available with InstallForge version 1.4`

* `Feature` Support for secure connections (HTTPS)
* `Enhancement` [DPI aware](https://docs.microsoft.com/en-us/windows/win32/hidpi/high-dpi-desktop-application-development-on-windows) GUI
* `Enhancement` Full [Unicode] support (also for [Unicode] characters within the update script file)
* `Enhancement` Improved icon (16×16 px icon now has a higher quality; also added a 24×24 px icon)

## Version 1.0.0 (2012-11-03)

`Available with InstallForge version 1.2.7`

* Initial release
