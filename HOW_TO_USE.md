# MS747 MCP Router - How to Use

This guide is for pilots and builders using the MS747 MCP hardware panel with the MS747 MCP Router app. It focuses on normal setup and day-to-day use, without internal wiring or developer details.

## What the Router Does

The router is the small Windows app that sits between your physical MCP panel and your flight simulator. It reads your panel buttons, switches, knobs, displays, lights, and backlighting, then keeps them in sync with the selected simulator.

You normally keep the router running whenever you fly with the MCP panel.

## Before You Start

You need:

- The MS747 MCP hardware panel connected by USB.
- The latest MS747 MCP Router release extracted to a normal folder.
- A supported simulator installed and working.
- For Microsoft Flight Simulator, start the simulator normally before expecting aircraft data to appear.

Do not run the router directly from inside the ZIP file. Extract the release first.

## First Launch

1. Open `MS747 MCP Router.exe`.
2. Allow Windows to run it if SmartScreen appears and you trust that it came from the official MS747 MCP release page.
3. Connect the MCP panel by USB.
4. Wait a few seconds for the status area to show that the MCP board is connected.
5. If the app asks you to install or update the firmware, follow the prompt.

The firmware version on the panel must match the router version closely. If the router says firmware upload is needed, do that before troubleshooting anything else.

## Firmware Upload

Use the firmware upload button in the router when the app asks for it, or after installing a new router release.

Recommended process:

1. Close other apps that may be using the MCP panel.
2. Connect the panel directly to the PC, not through an unreliable hub.
3. In the router, use the firmware upload option.
4. Wait until the upload finishes.
5. Do not unplug the panel during upload.
6. After upload, the panel should reconnect and show ready/standby behavior.

If upload fails, unplug the panel, plug it in again, select the correct COM port if needed, and retry.

## Choosing a Simulator

The router can work with different simulator modes. Use the simulator selection area in the app to choose what you are flying.

Typical choices:

- PSX for Aerowinx PSX.
- PMDG 747 for the PMDG 747.
- PMDG 777 for the PMDG 777.
- MSFS Asobo 747 for the default Microsoft Flight Simulator 747-8i.

If automatic simulator detection is enabled, the router may switch modes based on what is running. If you are testing or troubleshooting, manual selection is often clearer.

## Microsoft Flight Simulator Asobo 747 Setup

The MSFS Asobo 747 needs the router's MSFS support package for the best MCP behavior, especially fast knob movement and some cockpit-specific controls.

Use the router's MSFS WASM Bridge section:

1. Open the router.
2. Go to the MSFS WASM Bridge area.
3. Check that the Community folder shown is the one used by your MSFS installation.
4. Click Install / Update WASM Bridge.
5. Fully restart Microsoft Flight Simulator.
6. Load the Asobo 747.
7. Start or restart the router if needed.

Important: Microsoft Flight Simulator usually loads these support packages only during simulator startup. Installing the package while the simulator is already running is not enough; restart MSFS.

## PMDG Aircraft Setup

For PMDG aircraft, make sure the aircraft is loaded and powered enough for the MCP to be active. Then choose the matching PMDG mode in the router.

If the displays or annunciators do not follow the aircraft:

1. Confirm the correct aircraft mode is selected.
2. Confirm the aircraft is fully loaded in the cockpit, not still on a loading screen.
3. Use Manual Sync in the router.
4. Restart the router after the simulator is already in the cockpit.
5. If needed, restart the simulator and router.

## Hardware Test

Use Hardware Test after building the panel, after transport, or whenever a button or knob feels unreliable.

Open the router and click `HARDWARE TEST`.

The test walks through the panel in a fixed order. Follow the instruction shown at the top of the test window.

### Buttons and Switches

Most pushbuttons pass automatically when the router detects the correct press.

The DSP panel is tested in this order:

1. ENG
2. STAT
3. ELEC
4. FUEL
5. ECS
6. HYD
7. DRS
8. GEAR
9. CANC
10. RCL

The main toggle switches are tested in this order:

1. F/D L
2. A/T ARM
3. DISENGAGE
4. F/D R

Move each switch clearly through its expected position when prompted.

### Encoder Push Switches

The encoder push switches are checked more strictly. Each one must be detected three times.

The test shows the count on screen. When the count reaches 3/3, it moves to the next step automatically.

The knob push order is:

1. IAS
2. HDG
3. ALT

Press each knob firmly and release it fully between presses.

### Encoder Rotation

Each encoder rotation step stays on screen until you confirm it.

When prompted:

1. Turn the knob clockwise several clicks.
2. Turn the knob counterclockwise several clicks.
3. Watch the CW, CCW, and total counts rise.
4. If the count misses turns, jumps, or only works at certain angles, inspect the knob or soldering.
5. Click Confirm only when the count looks reliable.

This manual confirmation is intentional. It helps catch intermittent contact problems that may pass a one-click automatic test.

### Lights and Displays

Backlights, annunciators, and segment displays require visual confirmation.

When the test lights something, look at the actual panel and click Confirm if it looks correct. Use Skip only if you intentionally want to move past that item.

## Normal Flying Workflow

Recommended startup order:

1. Connect the MCP panel by USB.
2. Start the simulator.
3. Load the aircraft and wait until you are in the cockpit.
4. Start the MS747 MCP Router.
5. Select the correct simulator mode if it did not auto-select.
6. Use Manual Sync if the panel does not immediately match the aircraft.

During flight, leave the router running. The panel displays, mode lights, switches, and knobs should follow the aircraft.

## Running in the Background

Use `Hide to Background` when you want the router out of the way but still running.

The normal Windows minimize button only minimizes the window. It does not hide the router to the background.

To bring the router back after using Hide to Background, use the tray icon.

## Updating the Router

When an update is available:

1. Close the simulator if you are done flying.
2. Install or extract the new router release.
3. Run the new router.
4. Upload firmware if prompted.
5. For MSFS Asobo 747, install/update the MSFS support package again if the router recommends it.
6. Restart MSFS before testing the Asobo 747.

## Basic Troubleshooting

### The MCP panel is not detected

- Check the USB cable.
- Try a different USB port.
- Avoid unpowered hubs.
- Close other programs that may be using the panel.
- Restart the router.
- Reconnect the panel and wait a few seconds.

### Buttons work but displays do not

- Confirm the correct simulator mode is selected.
- Wait until the aircraft cockpit is fully loaded.
- Use Manual Sync.
- Restart the router after the aircraft is loaded.

### MSFS Asobo 747 knobs feel slow or incomplete

- Install/update the MSFS support package from the router.
- Fully restart Microsoft Flight Simulator.
- Load the Asobo 747 again.
- Confirm the router shows the MSFS support package as active/live.

### PMDG aircraft does not respond

- Confirm the correct PMDG aircraft mode is selected.
- Load the aircraft fully into the cockpit.
- Make sure the aircraft systems are powered enough for MCP operation.
- Restart the router after the aircraft is loaded.

### Hardware Test misses clicks

- Repeat the Hardware Test.
- Turn the encoder slowly and quickly in both directions.
- If counts only appear at certain angles or miss regularly, check the physical knob, connector, and soldering.

## When to Use Manual Sync

Use Manual Sync when the panel and aircraft look out of step, especially after:

- Changing aircraft.
- Loading into a flight.
- Reconnecting the panel.
- Switching simulator modes.
- Recovering from a simulator pause or reload.

Manual Sync asks the router to refresh the panel from the current aircraft state.

## Closing the Router

Use the normal window close button when you are finished. If the router is hidden in the background, restore it from the tray icon first or use the tray menu to exit.

Do not unplug the panel during firmware upload. During normal use, unplugging the panel is safe, but the router may need a restart or reconnect to detect it again.
