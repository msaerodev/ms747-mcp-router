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

## Background Mode

The normal Windows minimize button only minimizes the window. It does not hide the router to the background.

Use `Hide to Background` when you want the router to keep running in the tray.

## Report a Problem

Open `Debug & Options` and click `Report a Problem`. Enter a short title, describe the problem, and add the steps that reproduce it. Click `Create Report & Open GitHub` to create a privacy-sanitized diagnostic ZIP and open a pre-filled GitHub support request.

Drag the selected ZIP into the GitHub issue, review the report, and click `Submit new issue`. A GitHub account is required. The report automatically removes known credentials, email addresses, and personal Windows paths before the ZIP is created.

## Full Guide

Read the full consumer guide here:

[docs/HOW_TO_USE.md](docs/HOW_TO_USE.md)
