---
hide:
  - navigation
---

# Release Notes

## Version 1.3.0 (2025-10-25)

`Available with InstallForge version 1.5.0`

!!! danger "Important"

    As of version 1.3.0, Visual Update Express (now Visual Update Community) is no longer allowed to be used in a
    commercial context. If you want to use Visual Update in a commercial context, please purchase a Pro license.
    More information can be found in the [License section](../license/index.md).

* `Feature` Building DUP's in the context of a Continuous Deployment (CD) pipeline is now supported through the
  InstallForge CLI builder (available with InstallForge version 1.5.0+). More information can be found in
  the [InstallForge documentation](https://docs.installforge.net/).
* `Feature` DUP's can now be digitally signed during the build process using a code signing certificate
  (available with InstallForge version 1.5.0+). More information can be found in the
  [InstallForge documentation](https://docs.installforge.net/).
* `Feature` Support for several new Windows [special folder path constants](../reference/path-constants.md)
* `Enhancement` The update configuration is now stored in an XML file (`updateConfig.xml`) instead of in the DUP executable
* `Enhancement` Improved performance of the native update engine
* `Enhancement` Updated GUI fonts of the title text in the [DUP Wizard] for better readability

## Version 1.2.2 (2025-10-19)

* `Feature` Support for French language in the DUP Wizard (translation provided by Melchior V.)
* `Enhancement` Updated external libraries to the latest versions for improved security and stability

## Version 1.2.1 (2020-06-17)

`Available with InstallForge version 1.4.2`

* `Fix` Fixed false positive issues with different anti-malware applications

## Version 1.2.0 (2020-05-10)

`Available with InstallForge version 1.4.1`

* `Feature` Support for a new command: `ShellExecute`
* `Enhancement` Several improvements for the update engine with better error handling and increased robustness
* `Enhancement` The update engine now detects the [BOM] of the updatescript.ini file automatically (either no [BOM]
  or [UTF-8] [BOM] is valid)
* `Enhancement` The dialog can now be minimized
* `Enhancement` Improved `DownloadFile` command: The second parameter can now contain an optional file name which will
  be used for the downloaded file
* `Enhancement` Improved `DeleteFiles` command: read-only files are also deleted
* `Enhancement` Improved `DeleteDirectory` command: read-only files are also deleted
* `Fix` Fixed several UI issues due to DPI Awareness

## Version 1.1.0 (2020-04-24)

`Available with InstallForge version 1.4`

* `Feature` Support for secure connections (HTTPS)
*
`Enhancement` [DPI aware](https://docs.microsoft.com/en-us/windows/win32/hidpi/high-dpi-desktop-application-development-on-windows)
GUI
* `Enhancement` Full [Unicode] support (also for [Unicode] characters within the update script file)
* `Enhancement` Improved icon (16×16 px icon now has a higher quality; also added a 24×24 px icon)

## Version 1.0.0 (2012-11-03)

`Available with InstallForge version 1.2.7`

* Initial release
