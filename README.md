# MS747 MCP Router - How to Use

MS747 MCP Router is the Windows control app for the MS747 MCP hardware panel. It connects the physical MCP panel to supported flight simulators, keeps displays and annunciators synchronized, and provides setup, testing, update, and troubleshooting tools.

This guide is written for users. It avoids internal wiring, SDK, and developer details unless the name appears directly in the app.

## Download

Latest release page:

[Download the latest MS747 MCP Router release](https://github.com/msaerodev/ms747-mcp-router/releases/latest)

Stable direct download link for website buttons:

[MS747_MCP_Router_latest.zip](https://github.com/msaerodev/ms747-mcp-router/releases/latest/download/MS747_MCP_Router_latest.zip)

Current direct ZIP download:

[MS747_MCP_Router_v1.2.13.zip](https://github.com/msaerodev/ms747-mcp-router/releases/download/v1.2.13/MS747_MCP_Router_v1.2.13.zip)

[Changelog and known limitations](CHANGELOG.md)

Detailed usage and troubleshooting: [User Manual](docs/USER_MANUAL.md).
Word copies: [Full manual](docs/MS747_MCP_Router_User_Manual.docx) and
[One-page quick guide](docs/MS747_MCP_Router_Quick_User_Guide_v1.2.13.docx).

Do not run the router from inside the ZIP file. Extract the ZIP first, then run `MS747 MCP Router.exe`.

## Supported Simulator Modes

- **Aerowinx PSX**: For Aerowinx PSX.
- **P3D / PMDG**: For supported PMDG aircraft in Prepar3D.
- **MSFS / PMDG 777**: For the supported PMDG 777 bridge in Microsoft Flight Simulator.
- **MSFS / Asobo 747-8i**: For the default Microsoft Flight Simulator 747-8i with the router support package installed.

## First-Time Setup

1. Extract the latest release ZIP to a normal folder.
2. Connect the MCP panel to the PC by USB.
3. Start the simulator and load the aircraft.
4. Run `MS747 MCP Router.exe`.
5. Select the simulator and aircraft mode.
6. If firmware upload is requested, follow the router prompt.
7. If using MSFS Asobo 747, install the MSFS WASM Bridge from the router, then fully restart Microsoft Flight Simulator.
8. Press **Manual Sync** after the aircraft is loaded.

## Normal Flying Workflow

1. Connect the MCP panel by USB.
2. Start the simulator.
3. Load the aircraft and wait until the cockpit is ready.
4. Start MS747 MCP Router.
5. Confirm that the selected simulator mode is correct.
6. Press **Manual Sync** if the hardware panel does not immediately match the aircraft.
7. Leave the router running while flying.

## Main Settings Tab

The **Main Settings** tab is for normal flying, simulator selection, display brightness, backlighting, and switch status monitoring.

### Window Action

- **Hide to Background**: Hides the router to the background while keeping it running. Use the tray icon to restore it. The normal Windows minimize button only minimizes the window.

### Simulator Mode

- **Aerowinx PSX**: Selects PSX mode.
- **P3D**: Selects Prepar3D mode.
- **MSFS**: Selects Microsoft Flight Simulator mode.
- **Aircraft**: Selects the aircraft profile used by the selected simulator platform.
- **Auto-detect running simulator**: Lets the router detect a running simulator and switch mode automatically.
- **Detect Now**: Runs simulator detection immediately.

Use manual selection when troubleshooting. Automatic detection is convenient for normal use, but manual mode makes testing clearer.

### Connection Status

- **Simulator Status**: Shows whether the router is connected to the selected simulator.
- **MCP Status**: Shows whether the physical MCP panel is connected.
- **COM Port**: Shows the detected USB serial port for the panel.
- **Manual Sync**: Refreshes the panel displays, switch state, annunciators, and mode lights from the current aircraft state.

Use **Manual Sync** after loading an aircraft, reconnecting the panel, changing simulator modes, or whenever the panel looks out of step with the cockpit.

### PSX Network Settings

- **Host**: The PSX computer address.
- **Port**: The PSX network port.
- **Apply**: Saves and applies the PSX connection settings.

These settings are only needed when using Aerowinx PSX.

### Display & Backlight Settings

- **Annunciator LED color - GREEN / ORANGE**: Chooses which LED color style the annunciators use.
- **Main Backlight - White Max**: Sets the maximum white backlight level for the main MCP panel.
- **Main Backlight - Orange Max**: Sets the maximum orange backlight level for the main MCP panel.
- **Sub Backlight - White Max**: Sets the maximum white backlight level for the sub panel.
- **Sub Backlight - Orange Max**: Sets the maximum orange backlight level for the sub panel.
- **Segment Display - Digit Brightness**: Adjusts the brightness of the 7-segment displays.
- **Annunciator - LED Brightness**: Adjusts annunciator LED brightness.
- **Save Display Settings**: Saves display, backlight, color, and brightness settings.

Set these once for your cockpit lighting preference, then save them.

### Switch Mismatch Monitor

- **Switch Mismatch Monitor**: Shows whether key physical switch positions match the simulator state.

If a switch mismatch appears, move the physical switch to match the aircraft or press **Manual Sync** after confirming the aircraft is fully loaded.

## Debug & Options Tab

The **Debug & Options** tab is for maintenance, firmware, updates, MSFS support package management, backups, and deeper troubleshooting.

### Debug Options

- **Enable Switch Mismatch Monitor**: Enables mismatch warnings when physical switch positions and simulator states disagree.
- **Show Simulator <-> Router traffic**: Shows simulator communication messages in the system log.
- **Show Router <-> Arduino traffic**: Shows MCP hardware communication messages in the system log.
- **Trace PMDG end-to-end I/O**: Shows PMDG input, command, output, and panel update flow.
- **Show Initial Sync details**: Shows detailed startup and Manual Sync messages.

Leave these off for normal flying. Turn them on only when diagnosing a problem or when support asks for detailed logs.

### Settings Backup

- **Export Settings**: Saves display settings, backlight settings, annunciator settings, PSX network settings (host/port), and user mapping overrides to a backup file.
- **Import Settings**: Restores a previously exported router settings backup.

Use this before moving to another PC, reinstalling the router, or changing many mappings.

### Update

- **Update now**: Downloads and installs the latest available router release when an update is available.

After an update, upload firmware if the router asks for it. The router keeps the MSFS Asobo 747 WASM Bridge up to date on its own once it has been installed once (see below), so a manual WASM update is normally not needed after a router update — just make sure MSFS is closed when the router starts, then restart MSFS.

### Firmware

- **Upload Port**: Selects the COM port used for firmware upload.
- **Refresh**: Refreshes the list of available COM ports.
- **Upload Firmware**: Uploads the matching firmware to the MCP panel.
- **Install / Reinstall CH340 Driver**: Installs the USB serial driver used by many MCP boards.
- **Allow Through Windows Firewall**: Adds Windows firewall permission for router network communication.

Do not unplug the panel during firmware upload. If upload fails, reconnect the panel, refresh the port list, select the correct port if needed, and retry.

### MSFS WASM Bridge

- **MSFS location**: Shows the detected or selected Microsoft Flight Simulator location.
- **Browse**: Manually selects the MSFS installation location.
- **Open**: Opens the selected MSFS folder.
- **Install / Update WASM Bridge**: Installs the router support package for the MSFS Asobo 747.
- **Uninstall WASM Bridge**: Removes the installed router support package.
- **Refresh**: Re-checks bridge installation and live status.

The MSFS Asobo 747 needs this support package for the best MCP behavior, especially fast encoder movement and cockpit-specific controls. After installing or updating it, fully restart Microsoft Flight Simulator.

Version 1.2.13 includes Asobo speed-display, encoder delivery and support-package corrections. Parked-aircraft encoder and Mach tests have passed; full button/indicator verification is still incomplete. Close MSFS before **Install / Update**, then fully restart it; an installed-package message alone does not confirm that the MCP controls work. See [Changelog](CHANGELOG.md) for the tested scope and remaining limitations.

The development indicator update follows the loaded aircraft's panel power and lamp-test switch. All 13 indicator output paths passed a simulator lamp test; normal mode engagement is a separate check and is not fully qualified. See [development validation](docs/ASOBO_WASM_LIVE_VALIDATION.md).

After the first manual install, the router checks the bundled WASM version against the installed one on every startup and updates it automatically in the background when MSFS is not running, so the button above is mainly needed for the very first install.

### Monitoring Tools

- **PSX Monitoring**: Opens a live monitor for PSX state.
- **PMDG Monitoring**: Opens a live monitor for PMDG state.
- **Asobo 747 Monitoring**: Opens a live monitor for MSFS Asobo 747 state.
- **PMDG Interaction Probe**: Records PMDG interaction data for troubleshooting.

Use these tools when checking whether the simulator is sending live data to the router.

### Report a Problem

- **Report a Problem**: Opens the guided support report window.
- **Short title**: Enter a brief description, such as `IAS display does not update`.
- **What happened?**: Describe the visible problem and when it occurred.
- **Steps to reproduce**: List the actions that make the problem happen again.
- **What did you expect?**: Describe the correct behavior you expected.
- **Additional information**: Add anything else that may help identify the problem.
- **Include recent router and simulator logs**: Adds recent router, bridge, trace, crash, and interaction logs to the diagnostic package.
- **Include router settings and mapping overrides**: Adds the current router settings and customized mappings.
- **Create Report & Open GitHub**: Creates a privacy-sanitized ZIP and opens a new GitHub issue with the problem and system details already filled in.
- **Email Instead (No GitHub Account)**: Creates the same privacy-sanitized ZIP and opens your default email app instead, addressed to the developer, with the problem details already filled in.

After the GitHub page opens, drag the selected diagnostic ZIP into the issue, review the information, and click **Submit new issue**. A GitHub account is required for the final submission.

If you do not have (or do not want to create) a GitHub account, use **Email Instead** instead. A `mailto:` link cannot attach a file, so the diagnostic ZIP is selected in File Explorer for you to attach to the email by hand before sending.

The report removes known GitHub tokens, passwords, email addresses, personal Windows paths, and your Windows account and PC names automatically. The ZIP remains on your computer until you attach it, so you can review it before sending it.

## Mapping & Test Tab

The **Mapping & Test** tab is for hardware verification, direction correction, mapping review, output tests, and advanced customization.

### Top Controls

- **Activate Input Scan Mode**: Shows detected hardware inputs as you press buttons, move switches, or rotate encoders.
- **HARDWARE TEST**: Starts the guided hardware test.
- **Direction Reverse**: Opens a window to reverse switches or encoders that work backward.
- **See All Mappings**: Opens a table view of current switch, encoder, and annunciator mappings.

Use **Hardware Test** before changing mappings. It helps separate a physical hardware issue from a configuration issue.

### Hardware Test

The Hardware Test walks through the panel in a controlled order and asks you to confirm what the physical hardware does.

- **Buttons**: Press the requested button. Most buttons pass automatically when detected.
- **Toggle switches**: Move the requested switch clearly through its expected position.
- **Encoder push switches**: Press the knob switch three times. The test shows the count and automatically advances at 3/3.
- **Encoder rotation**: Rotate the knob clockwise and counterclockwise. Watch the CW, CCW, and total counts, then click **Confirm** when the count is reliable.
- **Lights and displays**: Visually confirm backlights, annunciators, and segment displays.
- **Confirm**: Marks the current visual or encoder step as passed.
- **Previous**: Returns to the previous step.
- **Skip**: Skips the current step.
- **Close**: Exits Hardware Test.

Encoder rotation requires manual confirmation on purpose. This catches intermittent encoder or soldering faults that may pass a one-click automatic test.

### Direction Reverse

Use **Direction Reverse** when a correctly wired-looking switch or encoder works opposite to the panel marking.

- **F/D L switch**: Reverses the left flight director switch.
- **F/D R switch**: Reverses the right flight director switch.
- **A/T ARM switch**: Reverses the autothrottle arm switch.
- **DISENGAGE bar**: Reverses the autopilot disengage bar.
- **IAS encoder**: Reverses IAS knob rotation.
- **HDG encoder**: Reverses heading knob rotation.
- **ALT encoder**: Reverses altitude knob rotation.
- **V/S encoder**: Reverses vertical speed knob rotation.
- **Save**: Saves the selected reverse settings permanently.
- **Reset All**: Clears all reverse settings.
- **Close**: Closes the window.

These settings are saved as user settings and remain after restarting the router or updating the app.

### Input Mapper

The Input Mapper is for advanced input review and customization.

- **Last**: Shows the last detected input while Input Scan Mode is active.
- **Description**: Human-readable name for the selected input.
- **Aerowinx PSX - Press**: Command used when the input is pressed in PSX mode.
- **Aerowinx PSX - Rel**: Command used when the input is released in PSX mode.
- **PMDG 747 - Press Event ID / Param**: Event and parameter sent when pressed in PMDG 747 mode.
- **PMDG 747 - Rel Event ID / Param**: Event and parameter sent when released in PMDG 747 mode.
- **PMDG 777 - Press Event ID / Param**: Event and parameter sent when pressed in PMDG 777 mode.
- **PMDG 777 - Rel Event ID / Param**: Event and parameter sent when released in PMDG 777 mode.
- **Func**: Special handling mode for inputs that need custom behavior.
- **Quick Preset**: Loads a predefined mapping for common MCP controls.
- **Save Input**: Saves the selected input mapping.

Most users should not need to edit these fields. Use presets or Direction Reverse first.

### Encoder Mapper

The Encoder Mapper controls encoder commands and acceleration.

- **Last**: Shows the last detected encoder while Input Scan Mode is active.
- **CW Cmd**: Command used for clockwise rotation.
- **CCW Cmd**: Command used for counterclockwise rotation.
- **Acceleration (PSX)**: Sets encoder acceleration for PSX mode.
- **Maximum Acceleration (PMDG / Asobo, x)**: Choose a maximum from 1 to 8 for the selected knob. Slow turns make fine adjustments; faster turns increase the response up to this maximum for both PMDG and Asobo. Choose 1 to disable speed acceleration. PSX keeps its separate setting. Click **Save Encoder** to retain the setting.
- **Save Encoder**: Saves the selected encoder settings, including its acceleration setting, for the next launch. Repeat for each knob you want to adjust.

If the direction is wrong, use **Direction Reverse** instead of swapping commands manually.

### Output Mapper

The Output Mapper configures annunciator LED output assignments and provides direct LED tests.

- **Annunciator Name**: Selects the annunciator to configure.
- **G Bit**: Hardware output assigned to the green LED.
- **O Bit**: Hardware output assigned to the orange LED.
- **GREEN ON**: Tests the selected green LED output.
- **ORANGE ON**: Tests the selected orange LED output.
- **Save Output**: Saves the selected annunciator output mapping.

Use this only when checking annunciator wiring or correcting an output assignment.

### Backlight Test

- **Main WH ON**: Tests main panel white backlight.
- **Main OR ON**: Tests main panel orange backlight.
- **Sub WH ON**: Tests sub panel white backlight.
- **Sub OR ON**: Tests sub panel orange backlight.

Only one color channel per panel is normally tested at a time.

### 7-Segment Logic Test

- **IAS field**: Test value for the IAS display.
- **HDG field**: Test value for the heading display.
- **ALT field**: Test value for the altitude display.
- **VS field**: Test value for the vertical speed display.
- **TEST SEND**: Sends the test values to the physical segment displays.
- **RESET ALL HW**: Clears hardware outputs and returns the panel to a clean state.

Use this when verifying that the physical display digits are connected and responding correctly.

## System Log

The **System Log** area shows important warnings, errors, firmware messages, update messages, and selected debug output.

- **Filter**: Shows only log lines containing the typed keyword.
- **Clear**: Clears the visible log window.

Startup diagnostic noise is kept out of the visible console when it is not useful to users, but detailed logs are still written to log files for support.

## Simulator-Specific Notes

### Aerowinx PSX

1. Start PSX.
2. Confirm the PSX host and port.
3. Select **Aerowinx PSX** in the router.
4. Press **Manual Sync** after the aircraft is ready.

### PMDG Aircraft

1. Load the PMDG aircraft fully into the cockpit.
2. Confirm the aircraft has enough power for the MCP to be active.
3. Select the matching PMDG mode in the router.
4. Press **Manual Sync**.
5. If displays or annunciators do not respond, restart the router after the aircraft is already loaded.

### MSFS Asobo 747

1. Install or update the **MSFS WASM Bridge** from the router.
2. Fully restart Microsoft Flight Simulator.
3. Load the default Asobo 747-8i.
4. Select **MSFS / Asobo 747-8i** in the router.
5. Press **Manual Sync**.

If encoder acceleration or cockpit-specific controls do not work, check the WASM Bridge status first and restart MSFS after installing it.

## Troubleshooting

### The MCP panel is not detected

- Check the USB cable.
- Try a different USB port.
- Avoid unreliable or unpowered USB hubs.
- Close other programs that may be using the panel.
- Restart the router.
- Reconnect the panel and wait a few seconds.
- Install or reinstall the CH340 driver if the router recommends it.

### Buttons work but displays do not

- Confirm the correct simulator mode is selected.
- Wait until the aircraft cockpit is fully loaded.
- Press **Manual Sync**.
- Restart the router after the aircraft is loaded.
- For MSFS Asobo 747, confirm the WASM Bridge is installed and MSFS was restarted.

### A switch or encoder works backward

- Open **Mapping & Test**.
- Click **Direction Reverse**.
- Enable the checkbox for the switch or encoder that works backward.
- Click **Save**.
- Test the control again.

Do not edit presets manually for this problem.

### Encoder turns are missed or unreliable

- Run **Hardware Test**.
- Rotate the encoder slowly and quickly in both directions.
- Watch the CW, CCW, and total counts.
- If counts only appear at certain angles, inspect the physical knob, connector, and soldering.

### MSFS Asobo 747 knobs feel slow or incomplete

- Install or update the **MSFS WASM Bridge**.
- Fully restart Microsoft Flight Simulator.
- Load the Asobo 747 again.
- Confirm the bridge status is active/live in the router.

### PMDG aircraft does not respond

- Confirm the correct PMDG aircraft mode is selected.
- Load the aircraft fully into the cockpit.
- Make sure the aircraft systems are powered enough for MCP operation.
- Press **Manual Sync**.
- Restart the router after the aircraft is loaded.

### Firmware upload fails

- Reconnect the panel.
- Click **Refresh** in the firmware port area.
- Select the correct upload port.
- Close other apps that may use the panel.
- Try the firmware upload again.

## Files Included in the Release

- `MS747 MCP Router.exe`: Main router application.
- `MS747 MCP Updater.exe`: Update helper.
- `docs/HOW_TO_USE.md`: Full user guide.
- `docs/MS747_MCP_Router_One_Page_User_Guide.docx`: Two-page printable quick guide (file name kept for compatibility with existing links).
- `packages/msfs/ms747-mcp-wasm-bridge/`: MSFS support package for the Asobo 747.
- `bridges/`: Simulator bridge components used by the router.
- `tools/firmware/`: Firmware upload tools.

## Support Information

When asking for support, include:

- Router version.
- Simulator and aircraft.
- Whether the MCP panel is detected.
- What was expected and what happened.
- Screenshots of the relevant tab.
- Recent log files from the router `logs` folder.

For most setup problems, run **Hardware Test** first and note which step fails.
