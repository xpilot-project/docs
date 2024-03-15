---
layout: home
title: Dot Commands
parent: xPilot Client
nav_order: 9
---

# Dot Commands
xPilot supports the following dot commands, which can be entered in the command line just below the message history in any tab.

| Command | Description |
| ---------- |-------------|
| `.chat <Callsign> <Message>` | Opens a new chat tab for the specified callsign. You can specify an initial message string to send. If no message string is specified, only a new chat window is opened. You can also use `.msg`
| `.clear`| Clears the contents of the active message tab.
| `.copy`| Copies the contents of the active message tab to the system clipboard.
| `.close` | Closes the current chat tab.
| `.ctaf <Station>`| Queries the VATSIM AIP for the CTAF frequency of the specified airport ID.
| `.atis <Callsign>` | Requests the controller text information/ATIS for the specified callsign.
| `.wx <Station>` | Requests the weather (METAR) for the specified station ID. You can also use `.metar`
| `.wallop <Message>` | Sends a "wallop" to all supervisors connected to the network.
| `.x <Squawk-Code>` | Sets your transponder to the specified squawk code. You can also use `.xpdr`, `.xpndr` or `.squawk`
| `.com1 <Frequency>`| Sets the COM1 radio to the specified frequency.
| `.com2 <Frequency>`| Sets the COM2 radio to the specified frequency.
| `.rx com# on|off`| Toggles receiving on the specified com radio. For example: `.rx com1 on`
| `.tx com#`| Enables the COM1 or COM2 radio for transmit. For example: `.tx com2`
| `.radios on|off`| Overrides the avionics power to be either on or off.
| `.towerview`| Connects xPilot to the network in tower view mode.
| `.ignore <Callsign>` | Adds the specified aircraft to the ignore list. xPilot will not render an aircraft model for any aircraft on the ignore list. The list is cleared when xPilot is closed.
| `.unignore <Callsign>` | Removes the specified aircraft from the ignore list.
| `.ignorelist` | Lists all the callsigns currently in the ignore list.
| `.simip` | Sets the IP address of the computer running your X-Plane instance; useful if you want to run xPilot on a separate machine from X-Plane. See [Running xPilot Over a Network](/docs/client/network.html) for details.
| `.visualip` | See [Running xPilot Over a Network](/docs/client/network.html).
| `.appdata`| Opens the client application data folder using the system file explorer