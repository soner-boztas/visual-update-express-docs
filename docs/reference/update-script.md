# Update Script

The update script serves for Visual Update to determine whether an update is available for your software
product and which operations need to be performed in order to update it. It is a text file named `updatescript.ini`
exposing a simple declarative syntax that must be located in the [server environment]. When creating a DUP (through
InstallForge), the web URI provided for `Main update address` (`1. Alternative update address`
and `2. Alternative update address` respectively) must point to a folder hosted on your web server, where the update
script file and a folder (named `Updates`) reside. For more information about this, refer to
[Quick Start Guide](../getting-started/quick-start-guide.md#configuring-the-dup).

## Structure of the Update Script

The general structure of the update script looks as follows:

```
releases{
<InitalVersion>
[<Version1>]
[<Version2>]
[...]
}

release:<InitalVersion>{

}

release:<Version1>{
<Command>: <Parameters>
...
}

release:<Version2>{
<Command>: <Parameters>
...
}

...
```

### `releases` Section

The update script consists of two main sections, which are enclosed in curly braces (`{}`):

- `releases`
- `release:<Version>`

The `releases` section contains a list of all versions identifiers of your software product that are considered for
updates. Each version identifier is specified in a separate line and can be any arbitrary string value
(e.g. `1.0.0`, `v2.5`, `2025.1`). Visual Update does not impose any restrictions on the scheme of version
identifiers.

!!! tip

    However, it is recommended to use [Semantic Versioning](https://semver.org/) for version identifiers in order to
    ensure a clear and consistent versioning scheme.

!!! danger "Important"

    It is important that the version identifiers are listed in the `releases` section in **ascending order**,
    i.e. from the oldest version to the newest version. This is crucial for the correct functioning of the update process.

The first version listed is the initial version of your software product (i.e. the version that is installed on the
[target environment] before any updates are applied). All other versions listed are versions that can be updated to.

### `release:<Version>` Section

For each version identifier `<Version>` listed in the `releases` section, there must be a corresponding
`release:<Version>` section in the update script, which specifies a list of commands that will be executed in order to
update your software product from the previous version to the specified version.

!!! info

    One exception is the `release:<InitalVersion>` section, which does not contain any commands, since previous to the
    initial version there is no version to update from. Yet, this section must still be present in the update script.

The commands are specified in the following format:

```
<Command>: <Parameters>
```

where `<Command>` is the name of the command and `<Parameters>` specifies comma-separated parameters required for
executing the command.

!!! info

    The commands are executed in the order they are listed in the `release:<Version>` section.

!!! danger "Important"

    It is crucial to understand that Visual Update works incrementally when applying updates. This means that when
    updating from version `A` to version `C`, first the commands listed in the `release:A` section are executed, followed
    by the commands listed in the `release:B` section, and finally the commands listed in the
    `release:C` section.

## Command Reference

The following commands are supported in the update script:

---

### `DownloadFile: <FilePath>, <DestinationPath>`

**Description:**

Downloads a file from the [server environment] to the [target environment].

**Parameters:**

- `<SourceFilePath>` (string): Relative path of the file to download . The path is relative to the `Updates` folder on
  the web server (see [Quick Start Guide](../getting-started/quick-start-guide.md#configuring-the-dup) for more
  information)
- `<DestinationPath>` (string): Folder path (relative or absolute) on the [target environment] where the file will be
  downloaded to. Alternatively, you can also specify target file path to rename the file during download.

**Example:**

```
DownloadFile: myapp.exe,
DownloadFile: someLib.dll, lib\
DownloadFile: someOtherLib.dll, lib\oherLib.dll
DownloadFile: myFont.ttf, <Fonts>
```

**Notes:**

* `<DestinationPath>` can be either relative or absolute. If a relative path is specified (e.g. `lib\`), it is resolved
  relative to the location of the DUP executable on the [target environment].
* If the folder specified in `<DestinationPath>` does not exist, it will **NOT** be created automatically.
* If the file already exists at the destination path, it will be overwritten.
* If `<DestinationPath>` points to a folder, the file will be downloaded with its original name as specified in
  `<FilePath>`.
* `<DestinationPath>` can also contain [path constants](path-constants.md). These constants will be resolved to
  the corresponding system folders on the [target environment].
* If the download fails, the update process will be aborted with an error message.

---

### `RenameFile: <SourceFilePath>, <DestinationFilePath>`

**Description:**

Renames or moves a file on the [target environment].

**Parameters:**

- `<SourceFilePath>` (string): Path of the file to rename or move. Can be either relative or absolute.
- `<DestinationFilePath>` (string): New path of the file after renaming or moving. Can be either relative or absolute.

**Example:**

```
RenameFile: myapp.exe, myappRenamed.exe
RenameFile: fonts\myFont.ttf, <Fonts>\myMovedFont.ttf
```

**Notes:**

* If `<SourceFilePath>` is a relative path, it is resolved relative to the location of the DUP executable on the
  [target environment].
* If `<DestinationFilePath>` is a relative path, it is resolved relative to the location of the DUP executable on the
  [target environment].
* `<SourceFilePath>` can also contain [path constants](path-constants.md). These constants will be resolved to
  the corresponding system folders on the [target environment].
* `<DestinationFilePath>` can also contain special Windows folder constants. These constants will be resolved to
  the corresponding system folders on the [target environment].
* If the source file does not exist or cannot be renamed/moved, the update process will be aborted with an error
  message.

---

### `CopyFile: <SourceFilePath>, <DestinationFilePath>`

**Description:**

Copies a file on the [target environment].

**Parameters:**

- `<SourceFilePath>` (string): Path of the file to copy. Can be either relative or absolute.
- `<DestinationFilePath>` (string): Path where the file will be copied to. Can be either relative or absolute.

**Example:**

```
CopyFile: myapp.exe, myappCopy.exe
CopyFile: fonts\myFont.ttf, <Fonts>\myCopiedFont.ttf
```

**Notes:**

* If `<SourceFilePath>` is a relative path, it is resolved relative to the location of the DUP executable on the
  [target environment].
* If `<DestinationFilePath>` is a relative path, it is resolved relative to the location of the DUP executable on
  the [target environment].
* `<SourceFilePath>` and `<DestinationFilePath>`can also contain [path constants](path-constants.md). These constants
  will be resolved to the corresponding system folders on the [target environment].
* If the source file does not exist or cannot be copied, the update process will be aborted with an error message.

---

### `DeleteFile: <FilePath>`

**Description:**

Deletes a file on the [target environment].

**Parameters:**

- `<FilePath>` (string): Path of the file to delete. Can be either relative or absolute.

**Example:**

```
DeleteFile: myappOld.exe
DeleteFile: <AppData>\OldConfig.cfg
```

**Notes:**

* If `<FilePath>` is a relative path, it is resolved relative to the location of the DUP executable on the
  [target environment].
* `<FilePath>` can also contain [path constants](path-constants.md). These constants will be resolved to
  the corresponding system folders on the [target environment].
* If the file does not exist, the command will be skipped **WITHOUT** error.

---

### `DeleteDirectory: <DirectoryPath>`

**Description:**

Deletes a directory on the [target environment] along with all its contents (recursively).

**Parameters:**

- `<DirectoryPath>` (string): Path of the directory to delete. Can be either relative or absolute.

**Example:**

```
DeleteDirectory: oldLibs
DeleteDirectory: <AppData>\OldData
```

**Notes:**

* If `<DirectoryPath>` is a relative path, it is resolved relative to the location of the DUP executable on the
  [target environment].
* `<DirectoryPath>` can also contain [path constants](path-constants.md). These constants will be resolved to
  the corresponding system folders on the [target environment].
* If the directory does not exist, the command will be skipped **WITHOUT** error.

---

### `ShellExecute: <FilePath>, <CommandLineArguments>, <WorkingDirectory>, <Flags>`

**Description:**

Executes a file (program) on the [target environment].

**Parameters:**

- `<FilePath>` (string): Path of the file (program) to execute. Can be either relative or absolute.
- `<CommandLineArguments>` (string): Command line arguments to pass to the program.
- `<WorkingDirectory>` (string): Working directory for the program. Can be either relative or absolute.
- `<Flags>` (string): Flags controlling the execution behavior. Can contain the following options:
    - `-wait`: The update process will wait for the program to finish before proceeding to the next command.
    - `-hidden`: The program will be executed in invisible mode.

**Example:**

```
ShellExecute: post_update_script.bat, --someArgument, ., -wait
```

**Notes:**

* If `<FilePath>` is a relative path, it is resolved relative to the location of the DUP executable on the
  [target environment].
* If `<WorkingDirectory>` is a relative path, it is resolved relative to the location of the DUP executable on the
  [target environment].
* `<FilePath>`, `<CommandLineArguments>` and `<WorkingDirectory>` can also contain [path constants](path-constants.md).
  These constants will be resolved to the corresponding system folders on the [target environment].
* If the file does not exist or cannot be executed, the update process will be aborted with an error message.

