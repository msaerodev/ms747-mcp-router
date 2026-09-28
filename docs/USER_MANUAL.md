# MS747 MCP Router User Manual

Version 1.2.13 | Windows | English | 29 September 2026

This manual explains how to set up the MS747 MCP panel, use the router while flying, and troubleshoot connection, knob, display, and indicator problems. Use the steps for your simulator. A working hardware test does not, by itself, confirm an aircraft connection.

## 1 Getting Started

### Before you connect

- Use the panel's supplied or approved equivalent power adapter and a reliable USB cable. This product is for PC flight simulation, not real-aircraft use.
- The router runs on Windows. There is no native Mac router in this release. PSX can run on a Mac while a separate Windows PC runs the router and connects to the panel.
- Download from the official MS Router page or GitHub releases. Extract the entire ZIP into a normal folder; do not run the app inside the ZIP or move the EXE away from its accompanying files.

### First setup

1. Connect panel power and USB. Close other programs that may be using the panel.
2. Open the router. If Windows warns about an unsigned download, check that it came from the official release page; do not disable Windows protection as a troubleshooting step.
3. Install the CH340 driver if the router requests it. Wait for **MCP Status** to show connected.
4. Upload firmware only when requested, or when support instructs you to do so. Keep power and USB connected until upload completes.
5. Select **Aerowinx PSX**, **P3D**, or **MSFS**, then the matching **Aircraft** profile. Asobo and PMDG are different profiles, even when both are Boeing aircraft.
6. Complete the simulator-specific setup on the next page. For Asobo 747, install the support package while MSFS is closed before starting the simulator.
7. Load the aircraft, wait for the cockpit to finish loading, then use **Manual Sync** if the physical panel does not match.

### Starting a normal flight

Connect the panel, start the simulator, load the aircraft, and open the router. Confirm both **MCP Status** and **Simulator Status**. Use **Manual Sync** after loading a flight, changing aircraft, reconnecting the panel, or changing simulator mode. Leave the router running throughout the flight.

### Window and display controls

- **Hide to Background:** keeps the router running in the system tray. Use the tray icon to bring it back. The Windows minimize button only minimizes the window.
- **Digit Brightness / LED Brightness:** adjust displays and indicators. The main/sub white and orange controls set backlight limits. Click **Save Display Settings** to keep your choices.
- **GREEN / ORANGE:** selects the annunciator color style. A brightness setting does not override an aircraft's unpowered or intentionally blank display.
- **Export Settings:** save a settings backup before reinstalling, moving PCs, or making extensive changes. **Import Settings** restores a previously exported backup.

## 2 Connecting Your Simulator

### Aerowinx PSX

1. Start PSX and enable its main network server.
2. Select **Aerowinx PSX** in the router. In **Host**, enter the address of the PSX computer. Use 127.0.0.1 only when PSX and the router run on the same Windows computer.
3. Set **Port** to the PSX server port; the usual default is 10747. Click **Apply**.
4. Wait for **Simulator Status** to connect, then click **Manual Sync**.

For PSX on a Mac, connect the MCP to the Windows router PC and enter the Mac's network address as Host. Keep both computers on a network that permits communication. Do not enter the Windows PC's address when PSX runs elsewhere.

### MSFS Asobo 747

The Asobo 747 requires the router support package. A message saying the files were installed is not the same as confirmation that the loaded aircraft is connected.

1. Completely close MSFS, not just the current flight.
2. Open **Debug & Options > MSFS WASM Bridge** in the updated router.
3. Confirm the detected MSFS location corresponds to the installation you actually use. Use **Browse** if detection selected the wrong installation.
4. Click **Install / Update WASM Bridge**. If prompted for a folder, select the Community folder used by that installation.
5. Start MSFS again, load the default Asobo 747, and wait for the cockpit.
6. Select the Asobo 747 profile. Use **Refresh** to check support-package status, then **Manual Sync**. Check live status, not only installation status.

After a router update, the package may update automatically when the router starts with MSFS closed. For troubleshooting or the v1.2.13 update, use Install / Update explicitly, then fully restart MSFS. Reinstalling while MSFS remains open is not sufficient.

### PMDG 747 or 777

1. Load the PMDG aircraft into the cockpit and power the aircraft systems sufficiently for MCP operation.
2. Select the correct platform and aircraft profile. MSFS PMDG 777 and P3D PMDG 747/777 are separate choices. Do not select Asobo for a PMDG aircraft.
3. Follow any router setup prompts, wait for **Simulator Status**, and use **Manual Sync**.
4. If the aircraft still does not respond, restart the router after the cockpit is loaded. If setup requested a simulator restart, complete it before testing again.

Use manual profile selection while troubleshooting. **Auto-detect running simulator** and **Detect Now** are convenient, but confirm the resulting Aircraft choice, especially when more than one simulator is running.

## 3 Knobs Switches and Hardware Test

### Adjust knob response

1. Open **Mapping & Test > Encoder Mapper** and select IAS, HDG, ALT, or V/S.
2. Set **Maximum Acceleration (PMDG / Asobo, x)** between 1 and 8.
3. Click **Save Encoder**, then try a slow turn and several short faster turns in the aircraft.

Slow turns make fine adjustments. Faster turns increase the response up to the chosen maximum; the setting is not a constant multiplier applied to every turn. Choose 1 for no speed acceleration. Lower the maximum if small corrections overshoot; raise it if large changes require too much turning. Each knob keeps its own saved setting. PSX uses its separate sensitivity setting.

Some aircraft limit the allowed range or hide a display until its mode is active. Turning farther cannot override those aircraft limits. V/S adjustment may require the V/S window to be open.

### Fix a reversed switch or knob

Open **Mapping & Test > Direction Reverse**. Check only the item that works backward, click **Save**, and retest normal simulator operation. You can independently reverse F/D L, F/D R, A/T ARM, DISENGAGE, IAS, HDG, ALT, and V/S. Settings remain after restarting and are preserved by the updater. You do not need to edit presets.

Direction Reverse changes normal operation, not the raw counts shown in Hardware Test. A consistently reversed response can be corrected here; missed or intermittent inputs require hardware diagnosis.

### Run Hardware Test

1. Click **HARDWARE TEST** while not actively flying. Normal simulator input routing is suppressed during the test; do not use it to control a flight.
2. Follow the displayed button/switch prompts. Press and fully release each encoder push switch three times. The count reaches 3/3 before automatic advance.
3. Turn every encoder repeatedly in both directions. Check that the counts rise reliably during slow turns and short faster bursts. Click **Confirm** only when you are satisfied; a single detected click is not enough.
4. Inspect each backlight, indicator, and numeric display when prompted. Confirm only if the physical panel looks correct. **Skip** is not a pass.
5. Close the test and use **Manual Sync** before returning to normal operation.

The main pushbutton sequence begins LNAV then VNAV. Knob push checks follow IAS, HDG, ALT, immediately before their corresponding rotation steps. DSP buttons follow ENG, STAT, ELEC, FUEL, ECS, HYD, DRS, GEAR, CANC, RCL. Toggle switches follow F/D L, A/T ARM, DISENGAGE, F/D R.

## 4 Updates and Support Reports

### Update safely

1. Finish flying and export settings if you want an additional backup.
2. Close MSFS before updating its Asobo support package. Use **Update now** when offered, or download the official latest ZIP for a manual installation.
3. Follow the updater prompts. Let it close the old router before replacing files; do not run two router copies together.
4. The built-in updater preserves user settings. For a manual move to a fresh folder or PC, export settings first and import them into the new router rather than assuming a fresh extraction contains your custom settings.
5. Open the updated router. Upload firmware only if prompted. For Asobo 747, use **Install / Update WASM Bridge**, fully restart MSFS, load the aircraft, and use **Manual Sync**.
6. Recheck your simulator profile, brightness, saved acceleration, and Direction Reverse settings.

If an update fails, use the official release download, extract all files into a separate normal folder, and import your settings backup. Do not delete the old installation or its user settings until the new copy works. An update download is not complete until the new router runs successfully.

### Report a problem

1. Open **Debug & Options > Report a Problem**.
2. Enter a short title, what you expected, what actually happened, and the steps to reproduce it. Include the simulator, aircraft, router version, and whether the issue occurs in Hardware Test, normal flight, or both.
3. For a knob problem, identify the knob, direction, approximate turn speed, and acceleration setting. For a light problem, name the light and whether the cockpit light changed too.
4. Leave the log/settings options enabled unless you intentionally want to exclude them. Click **Create Report & Open GitHub**, or **Email Instead (No GitHub Account)**.
5. Review the generated report and attach the ZIP selected in File Explorer. GitHub submission needs your sign-in; email needs you to attach the ZIP manually. The router does not submit the issue or send email automatically.

Known sensitive values are removed from the diagnostic bundle, but review the report before sending. Attach the generated support ZIP, not your entire router folder. For email, send to msaerodev@gmail.com.

### Diagnostic switches

Leave detailed traffic and trace options off for ordinary flying. Turn them on when support asks, reproduce the problem once, and create a report. Screenshots of the physical panel and aircraft cockpit are useful when display values or indicator behavior differ.

## 5 Troubleshooting Connections and Numbers

### Panel is not detected

1. Check panel power and USB connections; try a known-good cable and another PC USB port.
2. Avoid an unreliable or unpowered hub. Close other router copies and apps using the panel.
3. Install or reinstall the CH340 driver if requested. Reconnect the panel and wait a few seconds.
4. Restart the router and check **MCP Status**. Do not troubleshoot aircraft settings until the panel connection works.

### Firmware upload fails

Close other apps using the panel, reconnect directly to the PC, refresh the upload-port list, select the panel's port, and retry **Upload Firmware**. Keep power and USB connected during upload. If it fails repeatedly, create a support report rather than repeatedly changing mappings.

### Panel connects but the simulator does not

Select the correct platform and Aircraft manually. Wait for the cockpit to load, then restart the router. For PSX, check the server, Host and Port. For Asobo, check the selected installation and support package, then fully restart MSFS. For PMDG, follow setup prompts and confirm the correct PMDG profile. **Manual Sync** cannot establish a missing connection by itself.

### Displays do not match the cockpit

Check both connection statuses, the Aircraft profile, aircraft power, and digit brightness. Use **Manual Sync** after loading or switching aircraft. A cockpit display that is blank because of the aircraft's current mode may legitimately be blank on the panel. If Hardware Test displays digits correctly but normal operation does not, report a simulator/display issue rather than changing hardware output assignments.

### Knob is too slow or overshoots

Try slow turns first, then short faster bursts. Adjust the selected knob's maximum acceleration and click **Save Encoder**. For Asobo, check the support package is live after a full MSFS restart. If the value continues changing long after you stop, or oscillates, report the knob, turn pattern, and setting; do not keep increasing acceleration to compensate.

### Knob or switch works backward

Use **Direction Reverse**, save only the affected item, then retest outside Hardware Test. If direction is correct but counts are missed or erratic, the reverse setting will not fix it.

### Inputs are intermittent

Run Hardware Test and repeat slow turns, short bursts, and full button releases. If counts appear only at certain angles or miss repeatedly, check the external cable/connection and contact support for panel service. Do not open or modify a consumer panel merely to follow this guide.

## 6 Troubleshooting Lights and Remaining Issues

### Backlights or indicators appear dark

Check panel power, brightness settings, selected annunciator color, and aircraft cockpit power. Run the visual Hardware Test to establish whether the physical light can illuminate. If the hardware test passes but a simulator indicator does not, compare it with the corresponding cockpit indicator before changing mappings.

### Check Asobo indicators with the aircraft lamp test

1. Load and power the Asobo 747 cockpit. Confirm the router is connected to the Asobo profile.
2. Operate the aircraft's own lamp-test control and compare cockpit and physical MCP indicators.
3. Return the aircraft control to normal. The panel should return to the aircraft's normal indications.
4. Then test the flight mode in conditions where the aircraft permits it. A lamp test confirms illumination/output, not normal mode engagement.

If the cockpit indicator stays off too, do not assume the panel light is faulty. If the cockpit light is on but the physical indicator is off, confirm brightness and color, use Manual Sync, then send a support report with both views.

### What is and is not verified in version 1.2.13

All 13 Asobo MCP indicators passed the simulator lamp-test output/restoration check. Normal VNAV, FLCH, HDG HOLD, V/S, and ALT HOLD illumination was observed. Normal LNAV, LOC, APP, SPD, THR, and CMD L/C/R activation remains unverified; the lamp-test result is not a claim that these eight modes work in normal flight.

PMDG 777 and Asobo numeric tests used virtual knob input while parked. This update has not been live-tested in P3D or with the physical MCP, and PMDG Mach, active V/S, normal PMDG annunciators, and eligible in-flight Asobo conditions remain unverified. Report behavior that differs rather than assuming a hardware failure or a fully qualified aircraft feature.

### Before you contact support

Record whether MCP Status and Simulator Status are connected, whether Hardware Test passes, the selected Aircraft profile, and what the cockpit shows at the same time. Include reproducible steps and the generated support ZIP. This separates a panel connection problem from an aircraft mode or synchronization problem.

### Official downloads and full online guide

- Software and user information: https://www.mikesierraaero.com/general-1
- Latest release: https://github.com/msaerodev/ms747-mcp-router/releases/latest
- Online guide: https://github.com/msaerodev/ms747-mcp-router/blob/main/README.md
- Support: msaerodev@gmail.com
