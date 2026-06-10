# Quick Start Guide - OrganEyes

## Launching the Application

Double-click `OrganEyes.exe`.

To run the source code directly:

```powershell
python .\OrganEyes.py
```

---

## Manual Mode

1. Open the application.
2. Select `Manual with Folder Picker`.
3. Click `Choose Folder`.
4. Select the folder you want to organize.
5. Click `Organize Now`.

This mode performs a single organization run and does not leave any background processes running.

---

## Automatic Mode

1. Open the application.
2. Select `Automatic at Windows Startup`.
3. Click `Add Automatic Folder`.
4. Choose one or more folders to organize automatically.
5. Click `Save and Enable`.

From that point on, OrganEyes will process the configured folders every time Windows starts and will close automatically after completion.

---

## Disabling Automatic Mode

1. Open the application.
2. Go to `Automatic at Windows Startup`.
3. Click `Disable Automatic Startup`.

The application will no longer run when Windows starts.

---

## Emergency Bypass

If something goes wrong during automatic startup:

1. Turn on the computer.
2. While Windows is loading the desktop, hold the `Shift` key.
3. Keep it pressed for a few seconds.

If OrganEyes detects the `Shift` key, it will skip that automatic execution and perform no file operations during that session.

This does not permanently disable the feature; it only skips a single startup.

---

## Manual Removal

If the application cannot be opened, remove the following file:

```text
%APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup\OrganEyes.bat
```

Typical location:

```text
C:\Users\YOUR_USERNAME\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup\OrganEyes.bat
```

---

## Configuration Location

Configured automatic folders are stored in:

```text
%APPDATA%\OrganEyes\config.json
```

Typical location:

```text
C:\Users\YOUR_USERNAME\AppData\Roaming\OrganEyes\config.json
```

To completely reset the application:

1. Delete `OrganEyes.bat`.
2. Delete `config.json`.

---

## Configurable Parameters

The following values can be adjusted in `OrganEyes.py`:

```python
MINIMO_PARA_CARPETA_PROPIA = 2
MAXIMO_CARPETAS_PRINCIPALES = 8
NOMBRE_CARPETA_VARIOS = "Varios"
NOMBRE_CARPETA_SIN_EXTENSION = "Sin extension"
VENTANA_CANCELACION_SEGUNDOS = 5
```

### Description

**MINIMO_PARA_CARPETA_PROPIA**

Minimum number of files required before creating a dedicated folder for an extension.

**MAXIMO_CARPETAS_PRINCIPALES**

Maximum number of extension-specific folders that may be created.

**NOMBRE_CARPETA_VARIOS**

Folder name used to group uncommon file extensions.

**NOMBRE_CARPETA_SIN_EXTENSION**

Folder name used for files without extensions.

**VENTANA_CANCELACION_SEGUNDOS**

Number of seconds available to cancel automatic execution by holding the `Shift` key.
