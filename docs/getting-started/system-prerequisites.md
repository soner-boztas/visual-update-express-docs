# System Prerequisites

This section lists the system prerequisites for operating Visual Update. A distinction is made here between the
[build environment], [target environment] and the [server environment].

Before using Visual Update, please make sure that the requirements listed are met by the different environments.

=== "Build Environment Prerequisites"

    | Category           | Prerequisite                                                               |
    |--------------------|----------------------------------------------------------------------------|
    | Operating System   | :material-microsoft-windows: Windows 7 or later                            |
    | CPU                | :simple-intel: :simple-amd: Any Intel or AMD CPU based on x86 architecture |
    | RAM                | 1 GB                                                                       |
    | Disk Space         | 10 MB                                                                      |
    | Monitor Resolution | 1024 x 768 px²                                                             |

=== "Target Environment Prerequisites"

    | Category           | Prerequisite                                                               |
    |--------------------|----------------------------------------------------------------------------|
    | Operating System   | :material-microsoft-windows: Windows 7 or later                            |
    | CPU                | :simple-intel: :simple-amd: Any Intel or AMD CPU based on x86 architecture |
    | RAM                | 128 MB                                                                     |
    | Disk Space         | N/A (depends on the size of distributable update packages)                 |
    | Monitor Resolution | 1024 x 768 px²                                                             |

=== "Server Environment Prerequisites"

    | Category           | Prerequisite                                                               |
    |--------------------|----------------------------------------------------------------------------|
    | Operating System   | Any operating system with an operating HTTP server (such as Apache)        |
    | CPU                | Any                                                                        |
    | RAM                | N/A                                                                        |
    | Disk Space         | N/A                                                                        |

!!! note

    Please note that despite "Windows 7 or later" being stated in the target environment prerequisites,
    distributable update packages can technically target Windows 2000, Windows XP, Windows Server 2003,
    Windows Vista and Windows Server 2008 as well. However, these operating system are not officially supported.
