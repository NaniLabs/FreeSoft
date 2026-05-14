# Quick Manual - OrganEyes

## How to open the application

Double-click `OrganEyes.exe`.

If you want to run the source code directly:

```powershell
python .\OrganEyes.py
```

---

## Manual mode

1. Open the application.
2. Keep `Manual with folder picker` selected.
3. Click `Choose folder`.
4. Select the folder you want to organize.
5. Click `Organize now`.

This mode runs only once and does not stay active in the background.

---

## Automatic mode

1. Open the application.
2. Select `Automatic at Windows startup`.
3. Click `Add automatic folder`.
4. Choose one or more folders you want to organize automatically.
5. Click `Save and enable`.

From that moment, every time Windows starts, OrganEyes checks those folders, organizes the files and closes automatically.

---

## How to disable automatic mode normally

1. Open the application.
2. Go to `Automatic at Windows startup`.
3. Click `Disable automatic startup`.

After that, OrganEyes will no longer run when the PC starts.

---

## Emergency startup skip

If something goes wrong during Windows startup:

1. Turn on the PC.
2. While Windows is loading the desktop, hold the `Shift` key.
3. Keep holding it for a few seconds.

If OrganEyes starts in automatic mode while `Shift` is being held, it cancels that automatic session and does not organize anything.

This does not disable automatic mode permanently.
It only skips it once so you can enter Windows safely and fix the configuration.

---

## How to disable it manually if the app cannot be opened

If you need to disable it manually, delete this file:

```txt
%APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup\OrganEyes.bat
```

Typical path:

```txt
C:\Users\YOUR_USER\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup\OrganEyes.bat
```

---

## Where configuration is stored

The automatic folder list is stored in:

```txt
%APPDATA%\OrganEyes\config.json
```

Typical path:

```txt
C:\Users\YOUR_USER\AppData\Roaming\OrganEyes\config.json
```

If you want to reset everything, you can delete:

1. The automatic startup `.bat`
2. The `config.json` file

---

## Easy-to-modify parameters in the source code

Inside `OrganEyes.py` you can adjust:

- `MINIMUM_FOR_OWN_FOLDER = 2`
- `MAX_MAIN_FOLDERS = 8`
- `MISC_FOLDER_NAME = "Varios"`
- `NO_EXTENSION_FOLDER_NAME = "Sin extension"`
- `CANCELLATION_WINDOW_SECONDS = 5`

---

## What each parameter does

### `MINIMUM_FOR_OWN_FOLDER`

Minimum number of files required for an extension to deserve its own folder.

### `MAX_MAIN_FOLDERS`

Limits how many extension folders can be created at most.

### `MISC_FOLDER_NAME`

Name of the folder used for uncommon file types.

### `NO_EXTENSION_FOLDER_NAME`

Name of the folder used for files without extension.

### `CANCELLATION_WINDOW_SECONDS`

Available time window to cancel automatic mode by holding `Shift`.
