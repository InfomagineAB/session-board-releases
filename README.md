# Session Board

A small Windows widget that shows every Claude desktop session and its status: **needs you**, **working**, **done**. It sits in the taskbar (or floats as a small pill), alerts you when a session asks you something, and opens that session with one click.

This repository holds only the installer and update packages. The source code is private.

## Install

1. Open [Releases](../../releases/latest) and download `SessionBoard-stable-Setup.exe`.
2. Run it. No administrator rights are needed; it installs for your Windows user only.
3. Windows may show "Windows protected your PC" the first time, because the app is not code-signed yet. Choose **More info → Run anyway**. Updates after that install without the warning.

Claude's desktop app must be running with its window open (minimised is fine).

## Updates

Session Board checks this page for new versions at start and every 4 hours. When one is out, the board shows it with what's new and an **Update now** button. In the tray menu you can turn on **Install updates automatically**; it then updates only when no session needs you or is working.

## What Session Board does on your PC

Session Board only watches Claude. It needs no administrator rights and sends nothing anywhere.

**It reads** (never changes):
- Claude's window, through Windows' accessibility interface (what screen readers use): the session list and its labels, and what the open session is doing.
- Claude's own notifications from the Windows notification store. Notifications from other apps are ignored.
- Claude Code's session files (title, id, whether a turn is running).

**It writes** only its own files:
- Settings and the remembered session list: `%APPDATA%\SessionBoard`.
- A log for troubleshooting: `%USERPROFILE%\SessionBoard-logs` (stays on your PC).
- Its own "Start with Windows" entry, and only if you turn that on.

**It does**, only when you click:
- Opens a session in Claude: clicks that session in Claude's list, or opens a `claude://` link. It never opens web links or other apps' links.

**It connects** only to this repository, to check for and download updates.

**It never**:
- sends your data, session titles or logs anywhere, or collects usage statistics;
- runs commands, scripts or other programs (other than restarting itself to update);
- reads or changes other apps' windows, files or settings, or Claude's settings;
- gives anyone remote access to your computer.

## Uninstall

Windows Settings → Apps → Installed apps → Session Board → Uninstall.
