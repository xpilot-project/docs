---
layout: home
title: Command Bindings
parent: X-Plane Plugin
nav_order: 3
---

# Command Bindings
There are several commands that can be binded to one or more keyboard keys, joystick buttons or switches within X-Plane. If you are not familiar with how to setup command shortcuts in X-Plane, please refer to the [X-Plane Manual](https://www.x-plane.com/manuals/desktop/index.html#configuringkeyboardshortcuts) for more information.

Available X-Plane Commands:

* **Radio Push to Talk (PTT)**<br/>Bind `xPilot: Radio Push-To-Talk (PTT)` command to transmit on a radio frequency while connected to the network.

* **Split Audio Channels**<br/>Bind `xPilot: Split Audio Channels` command to split COM1 and COM2 audio into separate audio channels (COM1 will be routed to left channel – *left ear*, and COM2 will be routed to the right channel – *right ear*). This is a shortcut for enabling Split Audio Channels in the xPilot Settings.

* **Toggle Default X-Plane ATIS**<br/>Bind `xPilot: Toggle Default X-Plane ATIS` command to enable or disable the default X-Plane ATIS. xPilot will automatically disable the default ATIS when connected to the network, but you may enable it again using this command (or via the xPilot plugin menu).

* **Toggle Nearby ATC Window**<br/>Bind `xPilot: Toggle Nearby ATC Window` command to show or hide the Nearby ATC window.

* **Toggle Aircraft Labels**<br/>Bind `xPilot: Toggle Aircraft Labels` command to show or hide aircraft labels.

* **Toggle Notification Panel**<br/>Bind `xPilot: Toggle Notification Panel` command to show or hide the notification panel.

* **Toggle Message Console**<br/>Bind `xPilot: Toggle Message Console` command to show or hide the text message console. [See the note](/docs/xplane/text-message-console.html) on Keyboard Key Bindings for limitations.

* **Toggle TCAS Control**<br/>Bind `xPilot: Toggle TCAS Control` command to request or release TCAS control. If another plugin already owns the TCAS targets and doesn't release them on request, xPilot will not have control.