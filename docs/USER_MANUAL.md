# MS747 MCP Router User Manual

Version 1.2.18 | Windows | English | 29 September 2026

This manual explains how to set up the MS747 MCP panel, use the router while flying, and troubleshoot connection, knob, display, and indicator problems.

## 1 Getting Started

### Supported Simulators and Aircraft

- **Aerowinx PSX** (PSX itself can run on a Mac; the router still needs a separate Windows PC connected to the panel).
- **Prepar3D (P3D)** with supported PMDG aircraft.
- **Microsoft Flight Simulator (MSFS)** with the supported PMDG 777.
- **Microsoft Flight Simulator (MSFS)** with the default Asobo 747-8i, using the router's support package.

The router itself runs on Windows only; there is no native Mac version. Asobo and PMDG are separate aircraft profiles in the router, even when both are Boeing 747s -- always pick the one that matches what you are actually flying.

### Before you connect

- Use the panel's supplied or approved equivalent power adapter and a reliable USB cable. This product is for PC flight simulation, not real-aircraft use.
- Download from the official MS Router page or GitHub releases. Extract the entire ZIP into a normal folder such as Documents or Desktop; do not run the app from inside the ZIP or move the EXE away from its accompanying files. Avoid `Program Files` and other admin-protected folders -- installing there can make future updates ask for an administrator prompt.

### First setup

1. Connect panel power and USB. Close other programs that may be using the panel.
2. Open the router. If Windows warns about an unsigned download, check that it came from the official release page; do not disable Windows protection as a troubleshooting step.
3. Install the CH340 driver if the router requests it. Wait for **MCP Status** to show connected.
4. Upload firmware only when requested, or when support instructs you to do so. Keep power and USB connected until upload completes.
5. Select **Aerowinx PSX**, **P3D**, or **MSFS**, then the matching **Aircraft** profile.
6. Complete the simulator-specific setup on the next page. For Asobo 747, install the support package while MSFS is closed before starting the simulator.
7. Load the aircraft, wait for the cockpit to finish loading, then use **Manual Sync** if the physical panel does not match.

### Starting a normal flight

Connect the panel, start the simulator, load the aircraft, and open the router. Confirm both **MCP Status** and **Simulator Status** show connected. Use **Manual Sync** after loading a flight, changing aircraft, reconnecting the panel, or changing simulator mode. Leave the router running throughout the flight.

### Window and display controls

- **Hide to Background:** keeps the router running in the system tray. Use the tray icon to bring it back. The Windows minimize button only minimizes the window.
- **Digit Brightness / LED Brightness:** adjust displays and indicators. The main/sub white and orange controls set backlight limits. Click **Save Display Settings** to keep your choices.
- **GREEN / ORANGE:** selects the annunciator color style. Note that a dark cockpit or an aircraft that is powered off will still show a blank/dark panel regardless of your brightness setting.
- **Export Settings:** save a settings backup before reinstalling, moving PCs, or making extensive changes. **Import Settings** restores a previously exported backup.

## 2 Connecting Your Simulator

### Aerowinx PSX

1. Start PSX and enable its main network server.
2. Select **Aerowinx PSX** in the router. In **Host**, enter the address of the PSX computer. Use 127.0.0.1 only when PSX and the router run on the same Windows computer.
3. Set **Port** to the PSX server port; the usual default is 10747. Click **Apply**.
4. Wait for **Simulator Status** to connect, then click **Manual Sync**.

For PSX on a Mac, connect the MCP to the Windows router PC and enter the Mac's network address as Host. Keep both computers on a network that permits communication.

### MSFS Asobo 747

The Asobo 747 needs the router's support package installed to work fully.

1. Completely close MSFS, not just the current flight.
2. Open **Debug & Options > MSFS WASM Bridge** in the router.
3. Confirm the detected MSFS location matches the installation you actually use. Use **Browse** if detection picked the wrong one.
4. Click **Install / Update WASM Bridge**. If prompted for a folder, select the Community folder used by that installation.
5. Start MSFS again, load the default Asobo 747, and wait for the cockpit to finish loading.
6. Select the Asobo 747 profile. Use **Refresh** to check the support-package status is live, then click **Manual Sync**.

After a router update, the package usually updates itself automatically the next time the router starts with MSFS closed. If a control feels slow or incomplete after updating, use **Install / Update WASM Bridge** explicitly and fully restart MSFS.

### PMDG 747 or 777

1. Load the PMDG aircraft into the cockpit and power the aircraft systems sufficiently for MCP operation.
2. Select the correct platform and aircraft profile. MSFS PMDG 777 and P3D PMDG 747/777 are separate choices.
3. Follow any router setup prompts, wait for **Simulator Status** to connect, and use **Manual Sync**.
4. If the aircraft still does not respond, restart the router after the cockpit is loaded. If setup asked you to restart the simulator, do that before testing again.

**Auto-detect running simulator** and **Detect Now** are convenient shortcuts, but always confirm the Aircraft choice it selected -- especially if more than one simulator is running at once.

## 3 Knobs, Switches, and Hardware Test

### Adjust knob response

1. Open **Mapping & Test > Encoder Mapper** and select IAS, HDG, ALT, or V/S.
2. Set **Maximum Acceleration (PMDG / Asobo, x)** between 1 and 8.
3. Click **Save Encoder**, then try a slow turn and a few short faster turns in the aircraft.

Slow turns make fine adjustments; faster turns speed up the response, up to the maximum you chose. Choose 1 if you don't want any speed acceleration. Lower the maximum if small corrections overshoot; raise it if large changes take too much turning. Each knob remembers its own setting. PSX has its own separate sensitivity setting.

Some aircraft limit the allowed range for a value, or hide a display until that mode is active -- turning farther will not go past those aircraft limits. The V/S display may need the V/S window open on the aircraft's own panel.

### Fix a reversed switch or knob

Open **Mapping & Test > Direction Reverse**. Check only the item that works backward, click **Save**, and try it again in the simulator. You can independently reverse F/D L, F/D R, A/T ARM, DISENGAGE, IAS, HDG, ALT, and V/S. This setting is saved and survives updates -- you never need to edit configuration files by hand.

Direction Reverse only affects normal simulator operation, not the raw counts shown in Hardware Test -- that's expected, not a bug.

### Run Hardware Test

1. Click **HARDWARE TEST** while you are not actively flying -- normal simulator control is paused while the test runs.
2. Follow the on-screen button and switch prompts. Press and fully release each encoder push switch three times.
3. Turn every encoder in both directions. Watch that the counts rise reliably during both slow turns and quick bursts, then click **Confirm**.
4. Check each backlight, indicator, and digit display when prompted, and only confirm if the physical panel looks correct. Clicking **Skip** does not mean it passed.
5. Close the test and click **Manual Sync** before going back to normal flying.

## 4 Updates and Support Reports

### Update safely

1. Finish flying, and export your settings first if you'd like an extra backup.
2. Close MSFS before updating the Asobo support package. Click **Update now** when a new version is available.
3. Follow the on-screen updater steps -- it closes the old router for you before replacing files.
4. Your saved settings are kept automatically by the updater. If you're moving to a new PC or a fresh folder yourself, export your settings first and import them into the new copy.
5. Open the updated router. Upload firmware only if it asks. For Asobo 747, use **Install / Update WASM Bridge**, fully restart MSFS, load the aircraft, and use **Manual Sync**.
6. Double-check your simulator profile, brightness, saved acceleration, and Direction Reverse settings still look right.

If an update fails with a Windows permission message, see **Update fails with "Access is denied"** below.

If **Update now** cannot finish, your previous version is kept. Click **Download latest version manually** in **Debug & Options > Update** (it is also offered in the error message), close the router, and extract the ZIP over your router folder. Your settings are kept.

### Report a problem

1. Open **Debug & Options > Report a Problem**.
2. Enter a short title, what you expected, what actually happened, and the steps to reproduce it. Include the simulator, aircraft, and whether the issue happens in Hardware Test, normal flight, or both.
3. For a knob problem, note which knob, which direction, roughly how fast you turned it, and your acceleration setting. For a light problem, note which light, and whether the cockpit's own light changed too.
4. Leave the log/settings options enabled unless you want to exclude them on purpose, then click **Create Report & Open GitHub** or **Email Instead (No GitHub Account)**.
5. Attach the generated ZIP file when you submit on GitHub, or attach it manually to your email. The router prepares the report but does not send it for you.

The diagnostic bundle has known sensitive values removed automatically, but it's still a good idea to glance over the report before sending. For email, send to msaerodev@gmail.com.

## 5 Troubleshooting

### Update fails with "Access is denied"

- If Windows shows an administrator permission prompt, approve it and the update will continue.
- If it still fails, or fails without showing a prompt at all, open **Windows Security > Virus & threat protection > Manage ransomware protection > Allow an app through Controlled folder access**, and add both `MS747_MCP_Router.exe` and `MS747_MCP_Updater.exe` to the list.
- Installing the router in Documents or Desktop instead of `Program Files` avoids the administrator-prompt case entirely.

### Panel shows NOT CONNECTED, brightness does nothing, or you see "Access is denied"

Only one program can use the panel's COM port at a time. If **MCP Status** says NOT CONNECTED with "in use by another program", or the console shows `PermissionError(13, 'Access is denied')`, another copy of the router -- or another program such as the Arduino IDE or a serial monitor -- already has the port open. The first copy may still answer the panel's buttons while the second one cannot change brightness, which can look like a partly working panel.

1. Open Task Manager and look for `MS747_MCP_Router.exe` in addition to the window you are using, including a copy from before an update or from another folder. Also check the system tray.
2. Close every extra copy and any other program that may be using the panel, then wait a few seconds. The router connects on its own.
3. Newer versions refuse to start a second copy and tell you so. If you see that message, use the router that is already running.

### Panel is not detected

1. Check panel power and USB connections; try a known-good cable and a different PC USB port.
2. Avoid an unreliable or unpowered USB hub. Close other router copies and any other apps using the panel.
3. Install or reinstall the CH340 driver if the router asks. Reconnect the panel and wait a few seconds.
4. Restart the router and check **MCP Status**. Sort out the panel connection before troubleshooting aircraft settings.

### Firmware upload fails

Close other apps using the panel, reconnect it directly to the PC, refresh the upload-port list, select the panel's port, and retry **Upload Firmware**. Keep power and USB connected during the upload. If it keeps failing, send a support report rather than repeatedly changing mappings.

### Panel connects but the simulator does not

Select the correct platform and Aircraft manually, and wait for the cockpit to finish loading before restarting the router. For PSX, check the server, Host, and Port. For Asobo, check the selected MSFS installation and that the support package shows live, then fully restart MSFS. For PMDG, follow the setup prompts and confirm the profile. **Manual Sync** can't create a connection that doesn't exist yet -- fix the connection first, then sync.

### Displays do not match the cockpit

Check both connection statuses, the Aircraft profile, aircraft power, and digit brightness, then use **Manual Sync**. A cockpit display that's blank because of the aircraft's current mode may legitimately show blank on the panel too. If Hardware Test shows the digits correctly but normal flying doesn't, send a support report describing the difference.

### Knob is too slow or overshoots

Try a slow turn first, then a few short faster bursts. Adjust that knob's maximum acceleration and click **Save Encoder**. For Asobo, confirm the support package shows live after a full MSFS restart. If a value keeps changing well after you've stopped turning, or oscillates, send a support report describing the knob and turn pattern rather than repeatedly raising the acceleration setting.

### Knob or switch works backward

Use **Direction Reverse**, save only the affected item, then retest in normal flying (not Hardware Test). If the direction is correct but counts are missed or erratic, Direction Reverse is not the fix -- see Inputs are intermittent below.

### Inputs are intermittent

Run Hardware Test and repeat slow turns, quick bursts, and full button releases. If counts only appear at certain angles or keep being missed, check the cable connection and contact support for panel service. Please don't open or modify the panel yourself.

### Backlights or indicators appear dark

Check panel power, brightness settings, the selected annunciator color, and whether the aircraft cockpit itself is powered. Run the visual part of Hardware Test to see whether the physical light can turn on at all. If Hardware Test passes but a simulator indicator does not light up during normal flying, compare it against the matching cockpit indicator and send a support report with both.

### Checking Asobo indicators with the aircraft's own lamp test

1. Load and power the Asobo 747 cockpit, and confirm the router is connected to the Asobo profile.
2. Use the aircraft's own lamp-test control and compare the cockpit and physical MCP indicators side by side.
3. Return the aircraft's control to normal -- the panel should go back to showing the aircraft's normal indications.

If the cockpit indicator stays off too, the panel light is probably not the problem. If the cockpit light is on but the physical indicator stays off, double-check brightness and color, use Manual Sync, then send a support report with both views.

### Before you contact support

Note whether MCP Status and Simulator Status both show connected, whether Hardware Test passes, which Aircraft profile is selected, and what the cockpit shows at the same time as the panel. Attach the generated support ZIP along with your description -- this helps tell a panel connection problem apart from an aircraft mode or sync problem.

## 6 Official Downloads and Support

- Software and product information: https://www.mikesierraaero.com/general-1
- Latest release: https://github.com/msaerodev/ms747-mcp-router/releases/latest
- Online guide: https://github.com/msaerodev/ms747-mcp-router/blob/main/README.md
- Support: msaerodev@gmail.com
