# MS747 MCP Router - How to Use

This guide is for pilots and builders using the MS747 MCP hardware panel with the MS747 MCP Router app. It focuses on normal setup and day-to-day use, without internal wiring or developer details.

You can find the full guide in `docs/HOW_TO_USE.md` in each release package.

## Quick Start

1. Extract the MS747 MCP Router release ZIP.
2. Connect the MCP panel by USB.
3. Start your simulator and load the aircraft.
4. Open `MS747 MCP Router.exe`.
5. Select the simulator mode if it is not selected automatically.
6. Upload firmware if the router asks for it.
7. Use Manual Sync if the panel does not immediately match the aircraft.

## Hardware Test

Open `HARDWARE TEST` after setup, after transport, or whenever a switch or knob feels unreliable.

Encoder rotation now requires your confirmation. Turn each knob both directions, watch the counts rise, then click Confirm. Encoder push switches must be detected three times and then advance automatically.

## Adjusting Knob Response

Open **Encoder Mapper**, select a knob, adjust its acceleration setting, and click
**Save Encoder**. Settings are saved separately for each knob and restored next time.
Version 1.2.13 labels the shared control **Maximum Acceleration (PMDG / Asobo, x)**:
1 gives fine adjustment only; higher settings increase the response when you turn
quickly, up to the selected maximum of 8. PMDG and Asobo use the same speed bands;
PSX keeps its separate sensitivity setting.

## Asobo Indicator Checks

For Asobo indicator checks, use the aircraft's own lamp test
with the cockpit powered. All indicators lighting during that test confirms the
indicator path, not that every flight mode can engage in the current flight conditions.
Normal flight-mode checks are still incomplete; see [Changelog](CHANGELOG.md).
After updating, close MSFS, use **MSFS WASM Bridge > Install / Update**, and fully
restart MSFS before **Manual Sync**.

## Background Mode

The normal Windows minimize button only minimizes the window. It does not hide the router to the background.

Use `Hide to Background` when you want the router to keep running in the tray.

## Report a Problem

Open `Debug & Options` and click `Report a Problem`. Enter a short title, describe the problem, and add the steps that reproduce it. Click `Create Report & Open GitHub` to create a privacy-sanitized diagnostic ZIP and open a pre-filled GitHub support request.

Drag the selected ZIP into the GitHub issue, review the report, and click `Submit new issue`. A GitHub account is required. The report automatically removes known credentials, email addresses, personal Windows paths, and your Windows account and PC names before the ZIP is created.

If you do not have a GitHub account, click `Email Instead (No GitHub Account)` instead. It creates the same sanitized ZIP, opens your email app addressed to the developer with the details filled in, and selects the ZIP in File Explorer for you to attach by hand (email links cannot attach files automatically).

## Full Guide

Read the full consumer guide here:

[docs/HOW_TO_USE.md](docs/HOW_TO_USE.md)
