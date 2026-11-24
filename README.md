# turtle-test-tools-log-viewer
Log viewer for Transport Fever 3 mod testing

# Turtle's Test Tools: Log Viewer

A small Windows tool that makes the Transport Fever 3 log file easy to read while you test mods. It is an optional companion to the **Turtle's Test Tools** mod, but it works on its own and needs no mods.

## How it works

The game writes everything to a log file (`stdout.txt`) and replaces it only when the game starts, so the log grows long and mixes old sessions with new ones. The log viewer finds that file by itself and shows only the **current game or save load**. When you load another game or save, the window clears and starts over.

- Known harmless noise is hidden. Everything else stays visible, so unknown warnings and errors are never lost.
- Colours: red = error, yellow = warning, cyan = Turtle lines, green = new-game banner.
- Each session is saved in full (nothing hidden) to `Documents\turtle_logs`, because the game replaces its own log at every start.
- The viewer only reads the log. It never changes or clears it.

## Install and use

1. Download `turtle_test_tools_log_viewer.zip` from the [latest release](../../releases/latest).
2. Unzip it anywhere.
3. Double-click `view_log.bat` before or while you play. Close the window to stop.

Needs only Windows. Windows may warn that the files came from the internet. Both `view_log.bat` and `view_log.ps1` are plain text, so you can open them in Notepad and read them first.

## Options

Run `view_log.bat` from a command prompt and add a switch after the file name:

| Switch | What it does |
|---|---|
| `-Once` | Print the current session once and stop |
| `-ShowAll` | Hide nothing |
| `-Strict` | Show only Turtle lines, warnings and errors |
| `-Raw` | Keep the long `[date - MESSAGE - thread]` prefix |
| `-NoSave` | Do not write session files |
| `-SaveDir "D:\logs"` | Save sessions to another folder |
| `-Path "C:\...\stdout.txt"` | Read a log file from a specific place |

Example: `view_log.bat -Once`

## Log levels

The Test Tools mod tags its own log lines `[ERR]`, `[WARN]`, `[INFO]` and `[DBG]`. `[DBG]` lines are off by default.

## Files

- `view_log.bat`: the launcher (double-click this)
- `view_log.ps1`: the viewer script, which the launcher runs
- `README_log_viewer.txt`: short instructions

Keep the `.bat` and `.ps1` files in the same folder.
