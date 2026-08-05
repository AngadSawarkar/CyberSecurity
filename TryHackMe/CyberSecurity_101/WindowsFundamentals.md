# Module 3
# Windows NTFS – Quick Notes

## File Systems

* **NTFS (New Technology File System)** – Default file system in modern Windows.
* Older file systems:

  * **FAT16/FAT32**
  * **HPFS**

## NTFS Features

* Supports **files larger than 4 GB**.
* **Journaling** (automatically repairs file system after crashes).
* File & folder **permissions**.
* File & folder **compression**.
* **Encryption (EFS)**.

## NTFS Permissions

* Full Control
* Modify
* Read & Execute
* List Folder Contents
* Read
* Write

View permissions:

```text id="j67dza"
Right-click File/Folder → Properties → Security
```

## Alternate Data Streams (ADS)

* NTFS feature that allows a file to have **multiple data streams**.
* Main data stream: **$DATA**.
* Hidden from Windows Explorer.
* Can be viewed using **PowerShell** or third-party tools.
* Used by Windows to store metadata (e.g., downloaded from the Internet).
* Can also be abused by malware to hide data.

## Important Points

* **NTFS = Default Windows file system.**
* **FAT32** is still common on USB drives and SD cards.
* **ADS** is unique to NTFS and is important in cybersecurity.


# Windows Folder – Quick Notes

## Windows Folder

* Default location:

```text
C:\Windows
```

* Contains the **Windows Operating System** files.
* Can be installed on a different drive or folder.

## Environment Variable

* **`%windir%`** → Points to the Windows installation folder.
* Environment variables store system information (paths, temp folders, processor info, etc.).

## System32 Folder

* Location:

```text
C:\Windows\System32
```

* Contains **critical system files** required for Windows to function.
* Many built-in Windows tools are stored here.

## Important Points

* ⚠️ Do **not** delete or modify files in **System32**.
* Damaging System32 can make Windows **unbootable/inoperable**.
* `%windir%` is the easiest way to access the Windows folder regardless of where Windows is installed.


