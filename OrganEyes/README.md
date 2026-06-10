# OrganEyes

OrganEyes is a lightweight Windows application that automatically organizes files based on their most common extensions and file types.

It is designed to help users keep folders such as Downloads, Documents, Music, and custom directories organized without requiring additional dependencies.

## Screenshot

![Main Interface](Screenshots/app-main.png)

---

## Example

### Before Organization

![Before](Screenshots/before.png)

### Organization Process

![Organizing](Screenshots/organizing.png)

### After Organization

![After](Screenshots/after.png)

---

## Automatic Mode

OrganEyes can also run automatically when Windows starts.

Users manually select which folders should be organized automatically.

![Automatic Mode](Screenshots/auto-mode.png)

---

## Features

* Manual organization through a folder picker
* Automatic startup mode
* Intelligent grouping based on common file extensions
* Rare extensions grouped into `Misc`
* Files without extensions grouped into `No Extension`
* Emergency bypass by holding `Shift` during startup
* Windows notifications after automatic runs
* Safe duplicate file handling
* Built entirely with Python's standard library

---

## How It Works

1. Analyzes only the top level of the selected folder.
2. Identifies the most common file extensions.
3. Creates dedicated folders for the most frequent file types.
4. Groups less common extensions into `Misc`.
5. Groups files without extensions into `No Extension`.
6. Resolves filename conflicts safely using incremental suffixes.

Examples:

* `file (1).ext`
* `file (2).ext`

---

## Running from Source

### Requirements

* Windows
* Python 3.12 or newer recommended

### Run

```powershell
python .\OrganEyes.py
```

---

## Building the Executable

OrganEyes relies exclusively on Python's standard library.

To rebuild the executable:

```powershell
python -m pip install pyinstaller
python -m PyInstaller --onefile --windowed --name OrganEyes .\OrganEyes.py
```

The generated executable will be available in:

```text
dist\
```

---

## Automatic Mode Behavior

Automatic mode does not select folders on its own.

Users must explicitly configure which locations should be organized automatically.

If no folders are configured, the application exits safely without making changes and displays a notification.

---

## Security Notes

* Does not scan subfolders
* Does not overwrite existing files
* Automatic execution can be skipped by holding `Shift` during Windows startup

---

## Downloads

The latest executable release is available in the Releases section.

---

## Notes

This repository contains only the distributable version of the application.

Personal development scripts and internal tooling used during development are not included.

---

## Credits

Developed by NaniLabs.
