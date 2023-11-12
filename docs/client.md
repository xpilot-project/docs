# xPilot Client

The xPilot client serves as the primary user interface for connecting to the VATSIM network.

![xPilot](media/Client.png ':size=273')

?>
<span style="font-weight:bold;font-size:16px;">macOS Users</span><br/>
Upon launching xPilot for the first time on macOS, a prompt will request permission to access the microphone. Granting access is necessary to utilize the voice communication features of the client.<br/>
![Microphone Access](media/MacOSMicrophoneAccess.png ':size=186')

## Settings

To access the configuration settings of the xPilot client, click on the <span class="toolbar-btn">SETTINGS</span> button. The window displayed below will appear. Before establishing a network connection, it is necessary to configure your VATSIM credentials. If you plan to utilize voice communications, configuring your microphone and listen device is also essential.

![Settings](media/Settings.png ':size=507')

The VATSIM ID, VATSIM Password, and Name fields should be self-explanatory. The Home Airport field is optional; if completed, it will be displayed next to your name while connected to the network.

The Network Server dropdown menu provides only one option, "AUTOMATIC," which helps to connect your xPilot session automatically to the best network server, taking into account your geographic location and server availability.

### Notifications

![Settings](media/Settings_Notifications.png ':size=507')

The options listed in the "Notifications" tab allows you to personalize which events will trigger aural sound notifications and cause the application icon in the system taskbar to flash or bounce to capture your attention.

### Audio

The "Audio" tab is where you configure the audio settings for xPilot. See the [Audio Devices](#audio-devices) section for more information.

### Miscellaneous

![Settings](media/Settings_Miscellaneous.png ':size=507')

If the **Automatically set transponder to Mode C on takeoff** option is selected, your aircraft's transponder will automatically switch to Mode C after takeoff.

If the **Keep xPilot window visible** option is selected, the xPilot client window will consistently stay visible, remaining on top of other windows.

### Audio Devices

![Settings](media/Settings_Audio.png ':size=507')

The **Microphone Device** is utilized for communication with VATSIM controllers. Whenever you modify your microphone device, it is necessary to recalibrate the microphone volume. You can adjust the volume of your microphone using the slider located below the Microphone Device list. Ideally, the calibration indicator should remain within the green zone when speaking at a normal volume. If the indicator consistently shows red, it is advisable to lower the volume slider.

The **Headset Device** and **Speaker Device** serves as the audio output devices for listening to voice transmissions from controllers and other pilots. You can configure xPilot to send all COM1 audio to your headset device and COM2 audio to your speaker device, or vice-versa.

If the **Split Output Audio Channels** option is enabled, COM1 and COM2 audio will be split into separate audio channels (COM1 will be routed to left channel [left ear] and COM2 will be routed to the right channel [right ear]).

The audio device lists will automatically update if xPilot detects the removal or connection of an audio device.

You can also adjust the volumes for COM1 and COM2 here. Alternatively, you have the option to adjust the COM1 and COM2 volumes using the volume knobs on the aircraft's radio panel. 

**Note**: It's important to note that changes made to the radio volumes inside the aircraft will not be reflected in the volume sliders in xPilot settings, and vice versa. When you restart xPilot, the volumes will return to their previous levels as set by the volume sliders.

If the **Allow aircraft radio stack volume knobs to control radio volume** option is enabled, you can use the volume knobs in your aircraft to control the radio volume. This functionality is applicable as long as the aircraft you are flying utilizes the standard volume dataref; however, certain aircraft developers may use custom datarefs.

### Radio Effects
If the **Enable HF Squelch** option is activated, the static white noise typically heard when tuned to an HF frequency will be eliminated. However, if you prefer a realistic HF frequency experience, it is recommended to keep this option disabled.

By checking the box labeled **Disable Radio Effects**, the incoming voice audio will not be filtered to replicate the sound of a VHF radio. Instead, it will resemble more of a VOIP call. Generally, it is advisable to leave this option unchecked to ensure that the audio maintains a realistic and authentic resemblance to real-world radios.

### Push to Talk
To configure your Push to Talk (PTT) button, you need to set it within X-Plane. For detailed instructions on assigning your PTT, please refer to the [How to Assign PTT](xplane?id=how-to-assign-ptt) section.

## Connecting to VATSIM
To connect to VATSIM, simply click on the <span class="toolbar-btn">CONNECT</span> button. This action will open a connection window. Ensure that you fill in the callsign and aircraft type code fields as they are required. The SELCAL code field is optional.

The aircraft type code refers to the 3 to 4 character ICAO identifier code for the aircraft you are currently operating. This allows other users to see you accurately represented in their simulators with the correct aircraft type. As you enter the type code, xPilot will suggest relevant codes based on your input. You can search by ICAO code, aircraft model, or manufacturer, and xPilot will present you with a list of results to choose from.

![Type Code Suggestions](media/TypeCodeSearch.gif ':size=250')

If you input an invalid aircraft type code, a warning message will appear, asking you to confirm your selection. While you can proceed with the connection using the unknown type code, it's important to note that other users on the network may not see your aircraft rendered correctly in their simulators.

![Invalid Type Code](media/InvalidTypeCode.png ':size=250')

When you are ready to connect to the network, simply click the <span class="blue-btn">Connect to VATSIM</span> button. If the connection is successful, a message will be displayed in the main message area, and the CONNECT button will turn blue with its label changing to DISCONNECT. If there are controllers within range of your location, their information will be listed on the left-hand side of the client under the controller list.

Upon successfully connecting to the network, your callsign will be shown next to the SETTINGS button.

Please refer to the [Shared Cockpit/Observer Mode](client?id=shared-cockpit-observer-mode) section for detailed instructions on how to utilize the shared cockpit (observer) mode.

## Controlling the Transponder
When operating on VATSIM, it is necessary to switch your transponder between Standby Mode and Mode C. Mode C is employed when you are positioned on the active runway or when you are airborne. Enabling Mode C enables controllers to view your altitude on their radar scopes. Additionally, Mode C is utilized on the ground at certain airports that employ an airport surface surveillance system, such as ASDE-X. This information will be indicated on the airport diagram chart or provided in the controller's ATIS information.

**Toggle Transponder Mode**: To switch the transponder mode, you can simply click on the <span class="toolbar-btn">MODE C</span> button within the client. The button will turn green when Mode C is activated. Alternatively, you can directly toggle the transponder mode using your aircraft's transponder panel within the simulator.

![Mode C](media/ModeC.png ':size=70')

**Squawking Ident**: At times, a controller may request you to squawk ident. This action alters the appearance of your data tag on the controller's radar scope, making it easier for them to locate you within their airspace. If instructed to squawk ident, you can press the <span class="toolbar-btn">IDENT</span> button within the client or on your aircraft's transponder panel in the simulator. The IDENT button will illuminate in green once xPilot has transmitted the ident signal to the network. Once the ident process is completed, the button will return to its regular state.

![Transponder Ident](media/TransponderIdent.png ':size=74')

## Communicating with Controllers
Upon connecting to VATSIM, the controller list will be displayed along the left side of the xPilot client window. Controllers will be grouped by facility type, and each entry in the list will show the controller's callsign and frequency. Hovering over a callsign will trigger a popup label displaying the controller's name.

To communicate with a controller, simply tune their frequency on your aircraft's radio panel using either the COM1 or COM2 radio. Ensure that the radio is set to both transmit and receive modes. (You can also tune a frequency for receive only, which is useful when listening to the ATIS on the second COM radio.) The radio stack panel, located at the top left of the xPilot client window, displays the status of the radios. The TX/RX labels will appear white when transmit and receive modes are enabled for the respective COM radio.

In the provided example, COM1 is enabled for both transmit and receive, as indicated by the white TX/RX indicators, while COM2 has transmit and receive modes turned off.

![Radio Panel](media/RadioPanel.png ':size=74')

The "Speaker" and "Headset" icon allows you to toggle if the audio for the respective radio is routed through either the headset or speaker device, as configured in the xPilot audio settings.

To communicate with a controller using text radio messages, make sure you have the "Messages" tab selected. Then, type your message in the text command line located at the bottom of the message area and press Enter on your keyboard to send the message. xPilot will transmit the text message as a text radio message on the COM frequency that you have selected for transmit.

Incoming text radio messages will be displayed in the main messages area. If you are listening (receiving) on multiple COM radios, the text radio message will be prefixed with the frequency on which it was received.

If an incoming text radio message is specifically directed to you, your computer's default audio device will play an alert sound, and the message will appear in a cyan (light blue) color. Text radio messages intended for other pilots or not directed to anyone in particular will appear in gray color.

**Note that your aircraft's avionics must be powered on for the COM radios to function. If your avionics are not powered, the TX and RX indicators for both COM radios will appear grayed out, as shown in the screenshot below, and you will not be able to receive or transmit.**

![Radios No Power](media/RadiosNoPower.png ':size=74')

!> If you encounter issues with xPilot not properly synchronizing your radio transmit and receive status, you can manually force xPilot to transmit and/or receive on a specific radio.<br/><br/>To force xPilot to receive on a specific COM radio, you can use the `.rx` dot command. For instance, if you want to receive on COM1, you can enter `.rx com1 on` in the command line and press Enter.<br/><br/>To force xPilot to transmit on a specific COM radio, you can utilize the `.tx` dot command. For example, if you want to transmit on COM2, you can enter `.tx com2` in the command line and press Enter.<br/><br/>For further information, refer to the [Dot Commands](client?id=dot-commands) section.

## SELCAL
If you have specified a SELCAL (Selective Calling) code when connecting to VATSIM, controllers have the capability to send a SELCAL alert to your aircraft using that code. This feature is utilized during long flights over areas where the standard VHF radio does not provide sufficient range, and noisy HF frequencies are used instead. Pilots often decrease the volume to avoid listening to the HF static, and controllers can send a SELCAL alert to grab their attention when communication is required over HF.

When a SELCAL alert is received, you will hear a tone, and a message will appear in the main message area to notify you of the alert.

## Request Controller Info
To obtain the controller information or text ATIS on VATSIM, you can double-click on the controller entry in the controller list. This action will display the controller information in the main message area.

Alternatively, you can use the `.atis` dot command to request the controller information. For more information on dot commands, please refer to the section on [Dot Commands](client?id=dot-commands).

## Flight Plan
To file flight plans on VATSIM, you need to use the myVATSIM Flight Plan service website. To access this website, simply click the <span class="toolbar-btn">FLIGHT PLAN</span> button in the client. This action will open your default web browser and take you to the myVATSIM flight plan website.

If you haven't already authenticated yourself, you will be prompted to enter your VATSIM credentials, which include your VATSIM ID and Password. Once you have successfully logged in, you can proceed to file your flight plan.

## Private Messages
When you want to communicate privately with other users on VATSIM, such as pilots or controllers, you can use the private messaging feature. When a new private message is received, a tab will be added with the sender's callsign, highlighted in yellow. Clicking on the tab will display the message area for that chat, and the tab text will turn white. If a new message arrives while the tab is not active, the tab will turn yellow again to indicate a new message.

To reply to a private message, simply type your message in the command line at the bottom of the chat tab and press enter. Your outgoing message will appear in the message area in cyan color. Incoming messages from the other user will appear in white.

You can initiate a private chat session by right-clicking on a controller in the controller list and selecting "Open Private Chat" from the context menu. This action will create a new tab for the chat, or switch to an existing tab if one already exists. You can then type your message and press enter to send it.

Alternatively, you can initiate a private chat session by using the `.chat` dot command. More information about dot commands can be found in the [Dot Commands](client?id=dot-commands) section.

## Dot Commands
xPilot supports the following dot commands, which can be entered in the command line just below the message history in any tab.

| <div style="width:300px;">Command</div> | Description |
| ---------- |-------------|
| `.chat <Callsign> <Message>` | Opens a new chat tab for the specified callsign. You can specify an initial message string to send. If no message string is specified, only a new chat window is opened. You can also use `.msg`
| `.clear`| Clears the contents of the active message tab.
| `.copy`| Copies the contents of the active message tab to the system clipboard.
| `.close` | Closes the current chat tab.
| `.atis <Callsign>` | Requests the controller text information/ATIS for the specified callsign.
| `.wx <Station>` | Requests the weather (METAR) for the specified station ID. You can also use `.metar`
| `.wallop <Message>` | Sends a "wallop" to all supervisors connected to the network.
| `.x <Squawk-Code>` | Sets your transponder to the specified squawk code. You can also use `.xpdr`, `.xpndr` or `.squawk`
| `.com1 <Frequency>`| Sets the COM1 radio to the specified frequency.
| `.com2 <Frequency>`| Sets the COM2 radio to the specified frequency.
| `.rx com# On\|Off`| Toggles receiving on the specified com radio. For example: `.rx com1 on`
| `.tx com#`| Enables the COM1 or COM2 radio for transmit. For example: `.tx com2`
| `.towerview`| Connects xPilot to the network in tower view mode.
| `.ignore <Callsign>` | Adds the specified aircraft to the ignore list. xPilot will not render an aircraft model for any aircraft on the ignore list. The list is cleared when xPilot is closed. |
| `.unignore <Callsign>` | Removes the specified aircraft from the ignore list. |
| `.ignorelist` | Lists all the callsigns currently in the ignore list. |
| `.simip` | Sets the IP address of the computer running your X-Plane instance; useful if you want to run xPilot on a separate machine from X-Plane. See [Running xPilot Over a Network](client?id=running-xpilot-over-a-network) for details. |
| `.visualip` | See [Running xPilot Over a Network](client?id=running-xpilot-over-a-network). |
| `.appdata`| Opens the client application data folder using the system file explorer.

## Disconnecting from VATSIM
When you wish to disconnect from VATSIM, simply click on the <span class="blue-btn">DISCONNECT</span> button in the xPilot client. This will initiate the disconnection process.

Additionally, xPilot will automatically disconnect you from the network in the following situations:
- Shutting down the flight simulator
- Switching airports within the flight simulator
- Loading a different flight or scenario in the flight simulator

Upon disconnection, the controller list will be cleared, and all aircraft models associated with VATSIM will be removed from the simulator environment.

## Running xPilot Over a Network

To use xPilot over a network with multiple computers running X-Plane visuals, follow these steps:

1. Install the xPilot plugin on each computer running X-Plane visuals using the xPilot installer.

2. Enable TCP/IP support by modifying the xPilot plugin configuration file. Locate the `Config.json` file in the `X-Plane/Resources/plugins/xPilot/Resources/` directory. Open it with a text editor and change the value of the `UseTcpSocket` option to `true`. Save and close the file. Repeat this step for each X-Plane instance on the visual machines. Note that X-Plane should be closed before modifying the configuration file.

3. Start xPilot and use the command `.visualip` followed by the IP addresses of your visual machines. For example, `.visualip 192.168.1.50 192.168.1.60`. Restart xPilot for the changes to take effect. The visual machine IP addresses will be saved in the xPilot client configuration for future use. To clear the visual machine IP addresses, use the command `.visualip` without specifying any IP addresses.

Alternatively, if you want to run the xPilot client on a separate computer from the one running X-Plane, you can use the `.simip` command. Run xPilot on the separate computer and use the command `.simip <X-Plane_IP>` to set the IP address of the computer running X-Plane. For example, `.simip 192.168.1.100`. To clear the IP address, enter the command `.simip` without specifying an IP address. Note that the xPilot client must be closed before making changes to the configuration file, and it is recommended to use this command only if you are familiar with the setup.

Remember to follow the necessary precautions and ensure that your network and system configurations are properly set up to support xPilot over a network.

## Shared Cockpit (Observer) Mode
xPilot provides support for observer mode, which allows you to connect to the network without your aircraft being visible to other users. This feature is primarily used for shared cockpit operations. To utilize observer mode, follow these steps:

1. The first pilot should connect to the network as usual using their desired callsign, such as `JBU123`.

2. The second pilot, who wishes to join in observer mode, should append a letter to the end of the callsign used by the first pilot. For example, the second pilot can use `JBU123A`. You can use any letter as a suffix.

By using this approach, the second pilot will be able to connect to the network as an observer without their aircraft being visible to other users.

## Downloading Updates
Every time you start xPilot, it automatically checks for updates. If a new version is available, you will receive a prompt to download and install it.

**<span style="color:red;">X-Plane MUST be closed before installing an xPilot update.</span>**

![New Version](media/NewVersionAvailable.png ':size=250')

If you choose to click <span class="gray-btn">No</span>, you will be reminded about the update the next time you launch xPilot.

Clicking <span class="blue-btn">Yes</span> will initiate the download process. Once the download is complete, xPilot will automatically close, and the installer will open. On macOS, a disk image will be mounted, and a Finder window will appear with the installer that needs to be launched.

![New Version Downloading](media/NewVersionDownloading.png ':size=250')
