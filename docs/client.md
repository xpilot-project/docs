# xPilot Client

The xPilot client is the main user interface that is used to connect to the VATSIM network.

![xPilot](media/Client.png ':size=274')

!> **macOS Users:** When you launch xPilot for the first time on macOS, you will be asked to allow xPilot to access the microphone. You must allow access in order to use the voice communication functionality of the client.<br/>![Microphone Access](media/MacOSMicrophoneAccess.png ':size=186')

## Settings

To configure the xPilot client, click the **Settings** button. You will see the screen shown below.

![Settings](media/Settings.png ':size=612')

Before you can connect to the network, you must configure your VATSIM credentials. If you wish to utilize voice communications, you must also configure your microphone and listen device.

The VATSIM ID, VATSIM Password and Name fields should be self-explanatory. The Home Airport field is optional.

Select a VATSIM server which you would like to connect to. You should choose a server that is geographically closest to you. The VATSIM servers are inter-connected, so you will be able to see all pilots and controllers regardless of which server you are connected to.

If the **Automatically set transponder to Mode C on takeoff** is enabled, your aircraft's transponder will automatically change to Mode C after takeoff.

The toggle options on the right allow you to choose which events will cause aural sound notifications. The application icon in the task bar will also flash/bounce to grab your attention if xPilot is not the active window.

If **Keep xPilot window visible** is checked, the xPilot client window will always remain visible (on top).

### Push to Talk
Your Push to Talk button must be set within X-Plane. See the [How to Assign PTT](xplane?id=how-to-assign-ptt) section for information on how to bind your PTT.

### Audio Devices
The Audio API will show the audio drivers available to xPilot. If you are on Windows, this dropdown will show multiple options: MME, Windows Direct Sound, Windows WASAPI and Windows WDM-KS. MME or Windows WASAPI are the most common, but another option might work better with your audio device.

The **Microphone Device** is what will be used to communicate with VATSIM controllers. xPilot employs automatic gain control to automatically increase the gain of your microphone input volume. In some circumstances, you may need to manually increase the input volume of your microphone device in your system settings if it is too low.

The **Listen Device** is the audio device that will be used as the output device for listening to voice transmissions from the controllers and other pilots.

If the audio device is not yet plugged in, you will need to close and restart the xPilot client to refresh the device lists.

You can also adjust the COM1 and COM2 volumes here. Alternatively, you can adjust the COM1 and COM2 volumes via the volume knobs in the aircraft radio panel. **Note:** The volume sliders in the xPilot settings do not reflect adjustments made via the aircraft radio stack volume knobs, and vice versa. So, if you adjust the radio volumes inside the aircraft, the volume sliders will not reflect this change; when you restart xPilot, the volumes will revert to the previous volume levels as set by the volume sliders.

If the **Allow aircraft radio stack volume knobs to control radio volume** is checked, the radio volume can be controlled using the volume knobs in your aircraft. This will work as long as the aircraft your flying uses the standard volume dataref; some aircraft developers use custom datarefs.

### Radio Effects
If the **Enable HF Squelch** is enabled, you will not hear the static white noise when tuned to an HF frequency. If you want a realistic HF frequency experience, leave this option off.

If you check the box labeled **Disable Radio Effects**, the incoming voice audio will not be filtered to sound like a VHF radio &mdash; it'll sound more like a VOIP call. Generally, you want to leave this option unchecked so that the audio sounds realistic.

## Connecting to VATSIM
To connect to VATSIM, click the **CONNECT** button. You will see the Connect window. The callsign and aircraft type code field is required. The SELCAL code is optional.

The aircraft type code is the 3 to 4 character ICAO identifier code for the aircraft you are flying. This will allow other users to see you in their sim as the correct aircraft type. xPilot will suggest type codes based on what you type in the type code field. You can search by ICAO code, aircraft model or manufacturer, and xPilot will present you with a list of results to choose from. 

![Type Code Suggestions](media/TypeCodeSuggestions.png ':size=250')

If you specify an invalid aircraft type code, you will a warning message prompting you to confirm your selection. You may continue connecting using the unknown type code, however, other network users may not see your aircraft rendered correctly in their simulator.

![Invalid Type Code](media/InvalidTypeCode.png ':size=250')

Press the Connect button when you are ready to connect to the network. If the connection was successful, you will see a message in the main message area, and the Connect button will light blue and its label will change to "Disconnect". If there are controllers within range of your location, they will appear in the controller list on the left-hand side of the client. 

Your callsign will appear next to the **Settings** button after successfully connecting.

[See below](client?id=shared-cockpit-observer-mode) for details on using the shared cockpit (observer) mode.

## Controlling the Transponder
When flying on VATSIM, you will need to toggle your transponder between Standby Mode and Mode C. Mode C is used when you enter the active runway and any time you are airborne. Mode C allows the controller to see your altitude on their radar scope. Mode C is also used on the ground at some airports if they are using an airport surface surveillance system, such as ASDE-X. This will be noted on the airport diagram chart or in the controller's ATIS information.

**Toggle Transponder Mode**: To toggle the transponder mode, you can click the **MODE C** button on the client. The button will change to a green color when Mode C is on. You can also toggle the transponder mode directly in your aircraft's transponder panel in the sim.

![Mode C](media/ModeC.png ':size=70')

**Squawking Ident**: a controller may ask you to squawk ident. This causes your data tag to appear differently on the controller's radar scope, helping them locate you in their airspace. If you are asked to squawk ident, you can press the **IDENT** button on the client, or in your aircraft's transponder panel in the sim. The **IDENT** button will light up green when xPilot has sent the ident signal to the network. When the ident is finished, the button will return to its normal state.

![Transponder Ident](media/TransponderIdent.png ':size=74')

## Communicating with Controllers
When you connect to VATSIM, all controllers in range will be displayed in the controller list along the left side of the xPilot client window, grouped by facility type. Each entry in the list will have the controller's callsign and frequency. If you hover over the callsign, a popup label will appear displaying the controller's name.

In order to communicate with a controller, simply tune the controller's frequency in your aircraft's radio panel using either the COM1 or COM2 radio. The radio must also be selected for transmit and receive. (You can also tune a frequency for receive only; this is helpful when listening to the ATIS on the second COM radio). At the top left of the xPilot client window, you will see the radio stack panel. The TX/RX labels will turn white when transmit and receive are enabled for that COM radio.

In the example below, COM1 is enabled for transmit and receive, as indicated by the white TX/RX indicators. COM2 transmit and receive is turned off.

![Radio Panel](media/RadioPanel.png ':size=76')

To communicate with a controller via text radio messages, ensure you have the main "Messages" tab selected, type in your message in the text command line at the bottom of the message area and press Enter on your keyboard to send the message. xPilot will send the text message out as a text radio message on whichever COM frequency you have selected for transmit.

Incoming text radio messages are shown in the main messages area. If you are listening (receiving) on more than one COM radio, the text radio message will be prefixed with the frequency it arrived on.

If an incoming text radio message is directed at you specifically, an alert sound will play out of your computer's default audio device, and the message will appear in a cyan (light blue) color. Text radio messages directed towards other pilots (or towards no one in particular) will appear in a gray color.

**Your aircraft's avionics must be powered on for the COM radios to work. If your avionics are not powered, the TX and RX indicators will be grayed out for both COM radios (see screenshot below) and you will not be able to receive or transmit**

![Radios No Power](media/RadiosNoPower.png ':size=74')

!> If xPilot is having trouble syncing your radio transmit and receive status, you can force xPilot to transmit and/or receive on a specific radio instead.<br/><br/>To force xPilot to receive on a specific COM radio, use the `.rx` dot command. For example, to force receiving on COM1, you would enter `.rx com1 on` in the command line and press enter.<br/><br/>To force xPilot to transmit on a specific COM radio, use the `.tx` dot command. For example to force transmitting on COM2, you would type `.tx com2` in the command line and press enter.<br/><br/>See the [Dot Commands](client?id=dot-commands) section for more information.

## SELCAL
If you specified a SELCAL (Selective Calling) code when connecting to VATSIM, controllers will have the ability to send a SELCAL alert to your aircraft using that code. This is used to get your attention during long flights over areas where standard VHF radio doesn’t have enough range, and noisy HF frequencies are used instead. The pilot will typically turn down the volume so he doesn’t have to listen to the HF static, and controllers will send a SELCAL alert to get his attention when they need to talk to him over HF.

If a SELCAL alert is received, a tone will sound, and a message will be displayed in the main message area alerting you.

## Request Controller Info
Each controller on VATSIM maintains their controller information (also known as a text ATIS). To request this information, double-click on the controller entry in the controller list. The controller information will appear in the main message area.

You can also request the controller information using the `.atis` dot command. Refer to the section on [Dot Commands](client?id=dot-commands) for details.

## Flight Plan
Flight plans must be filed using the myVATSIM Flight Plan service website. If you click the `Flight Plan` button in the client, your default web browser will open to the myVATSIM website. If you are not authenticated, you will be asked to enter your VATSIM credentials (ID and Password).

## Private Messages
Occasionally, you may wish to contact other users (pilots or controllers) via private message. Or they may contact you via private message. When a new private message arrives, a tab will be added with the sender’s callsign, highlighted in yellow. When you click on the tab, the message area for that chat will be displayed and the tab text will turn white. The first line will show the user’s name. If a new message arrives while the tab is not active, the tab will turn yellow again.

To reply to a private message, type your message in the command line at the bottom of the chat tab and press enter. Your outgoing message wil appear in the message area in a cyan color. Incoming messages will appear in white.

You can initiate a private chat session by right-clicking on a controller in the controller list and choose "Open Private Chat" from the context menu. This will create a new tab (or switch to an existing tab if one exists). You can type your message and press enter to send it.

You can also initate a private chat session by using the `.chat` dot command. Refer to the section on [Dot Commands](client?id=dot-commands) for details.

## Dot Commands
xPilot supports the following dot commands, which can be entered in the command line just below the message history in any tab.

| <div style="width:300px;">Command</div> | Description |
| ---------- |-------------|
| `.chat <Callsign> <Message>` | Opens a new chat tab for the specified callsign. You can specify an initial message string to send. If no message string is specified, only a new chat window is opened. You can also use `.msg`
| `.clear`| Clears the contents of the active message tab.
| `.close` | Closes the current chat tab.
| `.atis <Callsign>` | Requests the controller text information/ATIS for the specified callsign.
| `.wx <Station>` | Requests the weather (METAR) for the specified station ID. You can also use `.metar`
| `.wallop <Message>` | Sends a "wallop" to all supervisors connected to the network.
| `.x <Squawk-Code>` | Sets your transponder to the specified squawk code. You can also use `.xpdr`, `.xpndr` or `.squawk`
| `.com1 <Frequency>`| Sets the COM1 radio to the specified frequency.
| `.com2 <Frequency>`| Sets the COM2 radio to the specified frequency.
| `.rx com# On\|Off`| Toggles receiving on the specified com radio. For example: `.rx com1 on`
| `.tx com#`| Enables the COM1 or COM2 radio for transmit. For example: `.tx com2`
| `.towerview <IP-Address> <Callsign>`| Connects xPilot to a proxy server (such as provided by Euroscope) in observer mode for the purpose of creating a tower view. The IP address defaults to 127.0.0.1 (localhost) and the callsign defaults to TOWER.
| `.ignore <Callsign>` | Adds the specified aircraft to the ignore list. xPilot will not render an aircraft model for any aircraft on the ignore list. The list is cleared when xPilot is closed. |
| `.unignore <Callsign>` | Removes the specified aircraft from the ignore list. |
| `.ignorelist` | Lists all the callsigns currently in the ignore list. |
| `.simip` | Sets the IP address of the computer running your X-Plane instance; useful if you want to run xPilot on a separate machine from X-Plane. See [Running xPilot Over a Network](client?id=running-xpilot-over-a-network) for details. |
| `.visualip` | See [Running xPilot Over a Network](client?id=running-xpilot-over-a-network). |

## Disconnecting from VATSIM
When you are ready to disconnect from VATSIM, click the **DISCONNECT** button on the xPilot client. The controller list will be cleared and all the aircraft in the sim will be removed. 

xPilot will automatically disconnect you from the network if you shut down the sim. You will also be disconnected if you switch airports or load a different flight in the sim.

## Running xPilot Over a Network
If you have a networked setup with one or more computers running your X-Plane visuals, you can configure xPilot to inject aircraft onto each of these machines. You must first run the xPilot installer on each of the machines so that the xPilot plugin is installed.

In xPilot, use the command `.visualip <VisualMachine1> <VisualMachine2>...` to set the IP addresses of your visual machines. For example, `.visualip 192.168.1.50 192.168.1.60`. **You must restart xPilot after setting the visual machine IP(s) for the changes to take effect.** The machine IP addresses with be saved in the xPilot client configuration for the next time you launch xPilot. To clear the visual machine IP(s), use the command `.visualip` (without the IP addresses).

Alternatively, you can run the xPilot client on a separate computer from your machine running X-Plane. Use the command `.simip` to set the IP address of the computer running your X-Plane instance. For example: `.simip 192.168.1.100`. To clear the IP address, enter the command `.simip` (without an IP address). The xPilot client must be closed before making changes to the configuration file. **<span style="color:red;">Only run this command if you know what you're doing!</span>**

## Shared Cockpit (Observer) Mode
xPilot supports the ability to connect in observer mode so that your aircraft does not appear to other users on the network. This feature is intended for use with shared cockpit operations. To use this feature, the first pilot should connect to the network normally, and the second pilot should connect in observer mode. The second pilot must use the same callsign as the first pilot, with a letter appended to the end.

For example, if the first pilot’s callsign is `JBU123`, the second pilot should use `JBU123A`. Any letter suffix will work.

## Downloading Updates
Each time you launch xPilot, it will check if there is a new version available. If there is a new version available, you will be prompted to download and install it.

![New Version](media/NewVersionAvailable.png ':size=250')

If you click **No**, you will be prompted again the next time you open xPilot.

Clicking **Yes** will begin the download process. Once the download completes xPilot will close and the installer will open. On macOS, the disk image will mount, and a Finder window will open with the installer that needs to be launched.

**<span style="color:red;">You must close X-Plane before installing the update, otherwise, the xPilot plugin cannot be updated properly.</span>**

![New Version Downloading](media/NewVersionDownloading.png ':size=250')
