# Swordburst 2 Controller

**By 1kakeden · v1.1.2 · Windows 10/11 x64**

I built Swordburst 2 Controller to bring multi-window monitoring, configurable combat actions, and account controls into one desktop panel. The v1.1.2 release adds private-channel Discord integration and clearer error reporting.

## Download and start

Download **Swordburst_2_Controller_v1.1.2_win-x64.zip** from the [latest release](https://github.com/kakedent/swordburst-2-controller-releases/releases/latest). Extract the ZIP and run **Swordburst2Controller.exe**. The download includes its .NET runtime.

Open the Roblox clients, select **Scan / Arrange**, and check HP, stamina, and boss recognition in **Diagnostics** before enabling automatic actions. Test **F6** to pause, **F7** to exit, and **Ctrl+Shift+F7** as the fixed backup exit. **F12** hides or shows the panel by default.

## Features

- Multi-window discovery, layouts, account priorities, and Combat or AFK-only modes.
- Configurable blocking, healing, skill rotations, and repeat cooldowns.
- Boss detection using HUD pixels, saved templates, and optional Tesseract OCR.
- Optional auto-revive with per-account limits; this can spend resurrection crystals and starts off.
- Theme controls, portable configuration exports, and boss-template sharing.
- An optional Discord bridge with a private server channel, live dashboard, and independent permissions for status, screenshots, configs, and logs.

Local controller features are free. Remote Discord services require a license issued by 1kakeden and a separately hosted bridge. The app never needs a Discord bot token. Sharing starts disabled. Private integration channels are visible to the linked user, 1kakeden, and the bot; Discord administrators retain their platform-level access.

## Settings and privacy

Existing settings remain in **%LOCALAPPDATA%\RobloxController** so installations made under the earlier name keep their preferences and templates. Discord pairing credentials are protected for the current Windows user. Portable config exports exclude those credentials and machine-specific paths. Diagnostic logs can include gameplay images and account labels; review them before sharing.

## Compatibility

One to four accounts are the recommended starting point; five to twelve remain experimental. Detection and simulated input depend on the game layout, Windows scaling, and foreground focus. Verify behavior while present before extended use. Tesseract is an optional separate installation.

This is an unofficial tool, not affiliated with Roblox or the Swordburst 2 developers. The executable is unsigned. Game and server rules apply.

## Updates

**Updates** checks the public release feed. When a newer version is available, the app can open its release page; installation is manual. Existing settings are retained.

## Building from source

The source repository is private. Contributors with access can install the .NET 8 SDK or newer and run **build-windows.cmd** from the project root. The script publishes **publish\Swordburst2Controller.exe** and packages the Windows download in **dist**. Public release repositories contain documentation and compiled downloads only.

## Version 1.1.0

- Stop preserves the button action even when focusing the panel pauses automation, and releases controller-held inputs immediately.
- Discord Start macro / Stop macro controls require permission in Details → Discord. Remote Start also enforces foreground and account checks.
- Ordinary automation never presses left-click. A confirmed revive can click its verified button; after two positive HP samples, recovery holds left, opens inventory with E, releases left, then closes inventory with E. Stop or lost focus cancels the sequence.
- HP uses multiple rows and a continuous fill check. Unreadable HP is shown as unknown rather than 0%; the revive prompt independently confirms death.
- OCR Setup can enable an experimental right-side rare-drop reader using separately installed Tesseract. It looks for skill/rare/epic/legendary/mythic/unique text, masks green/blue text, and ignores crystals and vel. Crops are processed locally and deleted. Results appear in Details and, when status sharing is enabled, the private Discord dashboard. Accuracy depends on text scale and effects; it is not a guaranteed drop log.
- Discord screenshots/configs/logs use temporary memory-only transfer; attachment messages expire after ten minutes.

### Memory usage

Use fewer simultaneous Roblox clients, lower the in-game graphics setting, close Account Utils sign-in windows after launching, and restart a client that grows continuously. Account Utils shows each client’s RAM use. There is no forced memory trim or Roblox file modification. Lower graphics mainly helps graphics load and may not reduce every game’s RAM use.

## Version 1.1.1

Overview shows account summaries; Details contains diagnostics; Settings groups all editable controls and opens the existing account, skill, input, revive, theme, OCR, config, and Discord editors. Settings scroll independently. Clicking the panel or switching apps no longer stops the automation session. Inputs are released once when focus leaves the assigned Roblox windows; the session waits without stealing focus and resumes when an assigned Roblox window is selected. Stop and emergency shortcuts still stop explicitly. Some input/account changes require stopping first.

The Overview tab keeps the compact 390-pixel-wide panel with four quick automation toggles. Details and Settings expand only when selected. Shortcut modifiers have dedicated space for full Ctrl, Alt and Shift labels, and the footer wraps long shortcuts instead of hiding them.

## Version 1.1.2 appearance update

Overview opens at the compact size immediately. Rounded theme-matched section buttons replace the native tab frame. Status and diagnostics use borderless dark text areas; Settings uses rounded cards and a slim dark scrollbar. The main screen keeps the compact four-toggle layout, with larger Details and Settings sections available separately.

### v1.1.2 control styling refresh

Rounded controls blend with their parent cards. All controller number fields use custom themed steppers with direct typing and keyboard increments; dropdowns use a custom themed picker with mouse, wheel, keyboard, and type-to-select support. This refresh replaces the existing v1.1.2 package without changing the version number.

## Saved window assignments

Select an account, click **Assign window…**, and choose its Roblox game window by PID and window handle. Verify the signed-in Roblox account before saving: window titles alone cannot identify it. A window can belong to only one account. The assignment appears in the account list and is saved locally for both apps in **%LOCALAPPDATA%\RobloxController\account-window-assignments.json**. No browser session data or credentials are sent.

Use Roblox Account Utils v1.1.1 on the same Windows user account. Stop automation, then select **Scan / Arrange** or **Start** to load assignments. Linked live windows are ordered by the Account Utils account list, ahead of unassigned windows. Controller account cards show the saved account nickname. Changes made during a run take effect after stopping and scanning or starting again.

Assignments survive restarting the apps while the same Roblox windows remain open. When Roblox closes or restarts, select its new window again; old process/window identities are never automatically reused. Removing an account also removes its saved assignment. Controller combat settings remain session-specific.
