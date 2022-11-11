# FAQ

## Where is the xPilot client config file?
* Windows: `C:/Users/<USER>/AppData/Local/org.vatsim.xpilot/AppConfig.json`
* macOS: `~/Library/Application Support/org.vatsim.xpilot/AppConfig.json`
* Linux: `~/.local/share/org.vatsim.xpilot/AppConfig.json` (you will have to enable hidden files/folders to see the `.local` folder)

!> If you have the xPilot client running, you can enter the command `.appdata` which will open the folder directly.

## Disconnected due to low frame rates
VATSIM requires that the X-Plane users maintain at least 20 frames-per-second during flight. The reason for this is to prevent a phenomena called "time dilation", which is when the simulation rate of X-Plane drops below real-time, which results in an aircraft flying slower on radar than what their groundspeed reports. X-Plane enforces a strict 20 FPS minimum to ensure the simulation rate runs in real-time. You can read more about this here: https://www.x-plane.com/kb/the-simulators-measurement-of-time-is-slow/

## I can't see any TCAS targets on my plane's radar
Make sure you don’t have any other plugins installed that could be interfering with xPilot (e.g. XSwiftBus, XSB, X-IvAP, etc.)

## Network Error: The server failed to respond to the authentication challenge
This is typically caused by a poor connection between you and the network server you are connected to. Try changing to a different server and try again.

## I can't transmit and/or receive audio in my aircraft. The COM radios are grayed out in xPilot
Make sure your radio stack in the aircraft is properly configured for TX and RX. In some cases, the aircraft model may not have a working audio panel, in which case you can trick xPilot into enabling TX and/or RX via the `.tx` and/or `.rx` dot commands. See the [Dot Commands](client?id=dot-commands) section for details.

## xPilot doesn't connect to X-Plane - stuck on "Waiting for X-Plane Connection"
* <strong>Windows Users:</strong> Add xPilot.exe to the Windows Defender exclusions list, and/or try running xPilot as an Administrator.
![Windows Defender Exclusion](media/WindowsDefenderExclusion.gif)
* Verify xPilot has an entry in X-Plane's plugin menu. If this is not the case, make sure there is an xPilot plugin in `X-Plane/Resources/plugins/xPilot`.
* Ensure that X-Plane is running with a flight open and that it is not blocked by your Firewall. See [Allowing X-Plane through your firewall](https://www.x-plane.com/kb/allowing-x-plane-through-your-firewall/).
* Restart your computer.<br/><br/>
The **Port we receive on (legacy)** in X-Plane must also be set to **49000** under **X-Plane Settings > Network**. Also, verify that the switch at the bottom of the Network tab is set to **Allow incoming connections**. Restart X-Plane after making these changes.![X-Plane Network Settings](media/XplaneNetworkSettings.png ':size=720')

## Error connecting to voice server. Please check your VATSIM credentials and try again.
If you recently created or reactivated your VATSIM account, you will need to wait a few minutes for your account to synchronize with the servers; and in some cases, up to 24-hours. Until your account is synchronized, you will not be able to use voice &mdash; only text. You must also take and pass the "P0: Basic VATSIM Member" exam. Otherwise, check your credentials and try again; the password is case sensitive.

## CSL Installation: The X-Plane folder is not readable (Windows Users)
If you get this error while trying to install the CSL model set, it means your user does not have permission to access the folder where X-Plane is installed. Try running the xPilot client as an Administrator and try again.

![X-Plane folder is not readable](media/XplaneFolderNotReadable.png ':size=250')

## macOS: Error reading file...
Due to macOS security settings, if you receive a "Error reading file..." error when updating xPilot, click the folder icon, choose the X-Plane folder path and try again.

![Error Reading File](media/MacOSErrorReadingFile.png ':size=759')
