---
layout: home
title: Text Message Console
parent: X-Plane Plugin
nav_order: 4
---

# Text Message Console
In addition to using the xPilot Client interface to send or receive text radio messages or private messages, you can use the Text Message Console in X-Plane. You can open the Text Message Console through the X-Plane menu via `Plugins > xPilot > Text Message Console` or by binding a keyboard key or joystick button or switch to quickly toggle the visibility of the window. See the [Command Bindings](/docs/xplane/command-bindings.html) section for details. 

**<span style="color:red;">Keyboard Key Binding: If you bind a keyboard key to open and close the Text Message Console window, you will not be able to toggle the window closed because the text input box has priority to capture any text that is typed. Instead, you will have to manually close the window. If you bind a joystick button to toggle the window, it should work as expected.</span>**

![Text Message Console](/assets/images/TextMessageConsole.png)

To send a message, type it in the message composition area at the bottom of the window and press enter on your keyboard. Radio text messages sent in the "Messages" tab are sent out on whichever COM frequency you have selected for transmit. Received radio messages directed towards you appear in white text. All other received messages will be gray. Radio messages sent by you will be cyan colored.

The following dot commands are supported in the Text Message Console in X-Plane:

| Command | Description |
| ---------- |-------------|
| `.chat <Callsign>` | Opens a new chat tab for the specified callsign. You can also use `.msg`
| `.close` | Closes the current private message tab.
| `.closeall` | Closes all private message tabs.
| `.clear`| Clears the contents of the active message tab.
| `.atis <Callsign>` | Requests the controller text information/ATIS for the specified callsign.
| `.wx <Station>` | Requests the weather (METAR) for the specified station ID. You can also use `.metar`
| `.x <Squawk-Code>` | Sets your transponder to the specified squawk code. You can also use `.xpdr`, `.xpndr` or `.squawk`
| `.com1 <Frequency>`| Sets the COM1 radio to the specified frequency.
| `.com2 <Frequency>`| Sets the COM2 radio to the specified frequency.
| `.rx com# On|Off`| Toggles receiving on the specified com radio. For example: `.rx com1 on`
| `.tx com#`| Enables the COM1 or COM2 radio for transmit. For example: `.tx com2`|

Private messages will appear in a separate tab in the Text Message Console window. To close a tab, click the blue "X". To initiate a new private message, type the command `.chat CALLSIGN` (where CALLSIGN is the callsign of the user you want to send a message to) and press enter. A new tab will open titled with the callsign you specified. Type your message in the message composition area at the bottom of the tab and press enter on your keyboard to send the message.

![Private Message](/assets/images/TextMessageConsole_PrivateMessage.png)