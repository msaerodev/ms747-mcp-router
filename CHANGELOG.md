# Changelog

## v1.2.21 - 2026-11-04

### Fixes

- **MSFS Asobo 747 support package**: installing or updating it can no longer leave a broken package (missing its `.wasm`) in the Community folder. The router now refuses to touch the package while MSFS is using it, prepares and checks the new package first, and puts the previous one back if anything fails. The automatic update at startup only runs when the router can confirm MSFS is closed. Uninstall keeps a backup instead of deleting.
- **PSX**: knob turns and button presses made while PSX was disconnected or restarting were sent all at once when it came back. They are now discarded, and the panel is re-synchronised on reconnect as before. Loading a situation no longer starts overlapping re-syncs.
- **PMDG / MSFS**: when the simulator is closed the router no longer restarts its PMDG connection helper every few seconds; if the simulator crashes or quits without notice, the router restarts the connection by itself instead of waiting for a mode change. Asobo 747 knobs no longer stop working after the simulator connection drops during a knob turn.
- Simulator connection logs no longer grow without limit (a PMDG log could reach hundreds of MB).
- macOS: the panel is no longer probed twice on connect.

### Update Instructions

- Use **Update now** as usual. No firmware upload is needed for this version.
- This PC's MSFS support package: if MSFS Asobo 747 knobs did not respond, close MSFS and click **Install / Update WASM Bridge** once.

## v1.2.20 - 2026-11-04

### New

- **macOS version** (Apple Silicon and Intel, macOS 11+) for **Aerowinx PSX**. Panel connection, mapping, Direction Reverse, acceleration, brightness, Hardware Test, firmware upload, updates and Report a Problem work the same as on Windows. PMDG and the MSFS Asobo 747 need Windows simulators and are not offered on the Mac. The app is not signed by Apple: the first time, right-click it and choose **Open**.
- Your settings are now kept in your user profile (`%LOCALAPPDATA%\MS747 MCP Router` on Windows, `~/Library/Application Support/MS747 MCP Router` on macOS). Updates, re-extracting the ZIP and new installs in any other folder keep your mapping, Direction Reverse, acceleration, brightness and PSX address. The first start of v1.2.20 copies your existing settings automatically (the old copy stays in the router folder). Put an empty `portable.flag` file next to the router to keep everything in one folder instead.

### Update Instructions

- Windows: use **Update now** as usual. Your settings are copied to your user profile on the first start.
- macOS: download `MS747_MCP_Router_mac_latest.zip`, open it and drag the app into **Applications**.

## v1.2.19 - 2026-11-04

### Fixes

- MCP indicator (annunciator) brightness now always follows your **LED Brightness** setting. Before, releasing the PSX **IND LTS TEST** switch, or connecting to PSX or a PMDG aircraft, could leave the indicators at the simulator's own level -- sometimes too dim to see the orange lights -- until you moved the slider. The simulator's indicator dimming (IND LTS DIM/BRT/TEST) is now applied on top of your setting instead of replacing it.
- In-app updates are much more robust against Windows permission problems:
  - The update is downloaded to your temp folder, so a router folder that needs admin rights no longer stops the download.
  - Files briefly locked by antivirus or by a router copy that is still closing are retried, and read-only files are handled.
  - If a file or folder needs administrator rights, the updater asks for permission by itself.
  - If the update still cannot finish, your previous version is restored instead of being left half-updated.
- Extracting a release ZIP over your router folder no longer resets your display settings (brightness, colors, PSX address). Earlier ZIPs carried a settings file that replaced yours; product defaults now ship separately and are only used on a fresh install.
- New **Download latest version manually** button (Debug & Options > Update) and a **Manual download** button in the update prompt. Every update error also offers the manual download as a last resort.

### Update Instructions

- If **Update now** from v1.2.18 or earlier fails, click the manual download link in the error message (or download from the release page), close the router, and extract the ZIP over your router folder. Your settings are kept. Later updates use the new, more robust updater.
- With PSX or PMDG, the indicator lights now use your LED Brightness setting as their maximum; if they look dimmer than before, raise LED Brightness and click **Save Display Settings**.

## v1.2.18 - 2026-10-04

### Fixes

- Fixed the panel showing "MCP: NOT CONNECTED" with brightness controls doing nothing, together with `PermissionError(13, 'Access is denied')` and "Write timeout" messages. Only one program can use the panel's COM port at a time; when a second copy of the router (for example a hidden copy from before an update, or a copy in another folder) was running, the first copy kept answering the panel's buttons while the second could not connect or change anything.
- The router now refuses to start a second copy and tells you to use the one already running.
- When the panel's COM port is held by another program, the status line now says so ("NOT CONNECTED (COM9 in use by another program)") and the console explains what to close, instead of a bare error.

### Update Instructions

- Close every running copy of the router first (check the system tray and Task Manager for `MS747_MCP_Router.exe`), then start the new version.

## v1.2.17 - 2026-10-01

### Fixes

- Fixed automatic updates failing with a certificate error (`CERTIFICATE_VERIFY_FAILED: unable to get local issuer certificate`) on some Windows machines. This had nothing to do with admin rights or file permissions -- it was a missing certificate trust list in the packaged app. The router now verifies its update downloads against the same certificate trust store Windows itself already uses.

### Update Instructions

- If a previous update attempt failed with a certificate error, download and install this version manually once from the link below; future updates should then work normally through **Update now**.

## v1.2.16 - 2026-09-29

### Improvements

- Rewrote the full user manual and one-page quick guide from a plain end-user perspective, with a clear "Supported Simulators and Aircraft" section up front.
- Fixed a rare case where Hardware Test's annunciator light readings could still be affected by a connected PSX session.
- Fixed a rare case where the router settings screen could read a value from the wrong internal thread when applying saved settings.

### Fixes

- Hardened the internal sequence tracking used to confirm Asobo 747 encoder commands were received, with no change to how those commands are actually sent.

## v1.2.15 - 2026-09-29

### Fixes

- If an update still fails with an access-denied error after v1.2.14's automatic admin-permission prompt, the failure message now also explains Windows Security's **Controlled folder access**, which can block this app from writing to Documents, Desktop, and similar folders even with admin rights approved. The message tells you exactly where to allow the app (Windows Security > Virus & threat protection > Manage ransomware protection > Allow an app through Controlled folder access).

### Update Instructions

- Close the router before applying the update. Existing saved settings are preserved by the updater.
- If this or a prior update failed with an access-denied error, check both the folder location (avoid `Program Files`) and Windows Security's Controlled folder access allow-list before retrying.

## v1.2.14 - 2026-09-29

### Fixes

- Fixed automatic updates failing with an access-denied error when the router is installed in a folder that needs administrator permission to write to (most commonly `Program Files`). The router now shows the standard Windows administrator permission prompt automatically only when it's actually needed, instead of requiring the whole app to always run as administrator. Installing in a normal folder such as Documents or Desktop avoids this prompt entirely.

### Update Instructions

- Close the router before applying the update. Existing saved settings are preserved by the updater.
- If the router is currently installed under `Program Files`, approve the administrator permission prompt when it appears during this update.

## v1.2.13 - 2026-09-29

### Improvements

- Added a saved, per-knob **Maximum Acceleration (PMDG / Asobo, x)** setting from 1 to 8. Slow turns remain fine adjustments; faster turns increase the response up to the selected maximum. Select 1 to disable speed acceleration. PSX retains its separate setting.
- Improved PMDG speed adjustment during short bursts, pauses to regrip, and direction changes. New turns accumulate toward the requested value rather than restarting from delayed simulator feedback.
- Removed per-step waiting from the PMDG high-speed adjustment path. In parked MSFS 2024 PMDG 777 tests, the previously measured approximately 3-second trailing response was reduced to at most 125 ms in the tested upper-speed cases. This is not a zero-latency guarantee.
- Improved automatic PMDG SDK setup discovery for Microsoft Flight Simulator 2024 installations.

### Fixes

- Fixed Asobo 747 support-package startup and command acknowledgement handling, preventing lost or stale encoder adjustments.
- Fixed Asobo 747 numeric control, including altitude selection, IAS/Mach display handling, and direction changes under accelerated input.
- Fixed Asobo 747 HDG HOLD selecting HDG SEL instead of HDG HOLD; verified the cockpit HDG HOLD indication.
- Corrected Asobo 747 APP indicator detection and the SPD button command binding.
- Made all 13 Asobo MCP indicators follow the aircraft's dedicated mode indications, cockpit panel power, and lamp-test switch rather than unrelated autopilot indications.
- Restricted customer documentation packaging to user guides and this changelog. Internal engineering reports and local test exports are not included.

### Update Instructions

- Close the router before applying the update. Existing saved settings are preserved by the updater.
- For Asobo 747, close Microsoft Flight Simulator, open the updated router, and use **MSFS WASM Bridge > Install / Update**. Fully restart the simulator and load the aircraft before using **Manual Sync**.
- Adjust each knob's response in **Encoder Mapper**, then click **Save Encoder**.

### Verification and Known Limitations

- Actual parked-aircraft virtual-input tests passed 20 PMDG 777 numeric cases and 8 maximum-acceleration Asobo burst/reversal cases. Asobo Mach roundtrip and all 13 lamp-test output/restoration checks passed.
- Normal Asobo activation/illumination was observed for VNAV, FLCH, HDG HOLD, V/S, and ALT HOLD. Normal LNAV, LOC, APP, SPD, THR, and CMD L/C/R activation remains unverified. A successful lamp test does not prove these modes engage under normal flight conditions.
- The shared PMDG changes are included for P3D, but this update has not been live-tested in P3D. PMDG Mach, active V/S, normal PMDG annunciators, eligible in-flight Asobo conditions, and physical MCP hardware remain unverified.
- Windows only; this release does not add native macOS support.
