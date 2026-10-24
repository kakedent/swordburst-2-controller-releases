# Swordburst 2 Controller

**By 1kakeden · Windows 10/11 x64**

I publish compiled downloads for Swordburst 2 Controller here. Application source is maintained privately.

## Download

Open **Releases**, select **v1.1.2** or a newer release, and download **Swordburst_2_Controller_v1.1.2_win-x64.zip** from its assets. Extract the entire ZIP and run **Swordburst2Controller.exe**. Keep the included files and folders together. **SHA256SUMS.txt** contains the download checksum.

GitHub's automatic **Source code** archives contain this public repository's documentation, not the application source or the runnable download.

Check Diagnostics and test F6 (pause), F7 (exit), and Ctrl+Shift+F7 (backup exit) before enabling automation. Existing settings remain in %LOCALAPPDATA%\RobloxController.

This is an unofficial, unsigned utility, not affiliated with Roblox or the Swordburst 2 developers. Game and server rules apply.

## Version 1.1.2

- Stop preserves the button action even when focusing the panel pauses automation, and releases controller-held inputs immediately.
- Discord Start macro / Stop macro controls require permission in Details → Discord. Remote Start also enforces foreground and account checks.
- Ordinary automation never presses left-click. A confirmed revive can click its verified button; after two positive HP samples, recovery holds left, opens inventory with E, releases left, then closes inventory with E. Stop or lost focus cancels the sequence.
- HP uses multiple rows and a continuous fill check. Unreadable HP is shown as unknown rather than 0%; the revive prompt independently confirms death.
- OCR Setup can enable an experimental right-side rare-drop reader using separately installed Tesseract. It looks for skill/rare/epic/legendary/mythic/unique text, masks green/blue text, and ignores crystals and vel. Crops are processed locally and deleted. Results appear in Details and, when status sharing is enabled, the private Discord dashboard. Accuracy depends on text scale and effects; it is not a guaranteed drop log.
- Discord screenshots/configs/logs use temporary memory-only transfer; attachment messages expire after ten minutes.

### Memory usage

Use fewer simultaneous Roblox clients, lower the in-game graphics setting, close Account Utils sign-in windows after launching, and restart a client that grows continuously. Account Utils shows each client’s RAM use. There is no forced memory trim or Roblox file modification. Lower graphics mainly helps graphics load and may not reduce every game’s RAM use.

## Compact layout and Settings

Version 1.1.2 restores the compact Overview with four quick automation toggles. Settings and Details expand only when selected. All editable controls and the existing account, skill, input, revive, theme, OCR, config, and Discord editors are accessible from Settings. Shortcut modifiers display their full Ctrl, Alt, and Shift labels, and long shortcut text wraps.

Changing focus keeps the automation session active: inputs wait while the controller or another app has focus, then resume when an assigned Roblox window is selected. Stop and emergency shortcuts still stop explicitly.

Version 1.1.2 replaces the native tab border with rounded section buttons, forces compact Overview sizing at startup, and uses borderless text areas and a slim themed Settings scrollbar.
