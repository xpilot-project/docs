# Getting Help {docsify-ignore}

If you're having trouble configuring or using xPilot, please use the [xPilot Support Forum](https://forums.vatsim.net/forum/352-xpilot/) or [Discord](https://vats.im/xpilot-discord).

## X-Plane Quit Unexpectedly
If X-Plane quits unexpectedly (known as a "Crash to Desktop" or CTD), the last line in the `Log.txt` will usually indicate what caused the application to crash. If xPilot caused X-Plane to crash, the last line in the `Log.txt` will end with `--=={This application has crashed because of the plugin: xPilot}==--`

The `Log.txt` is overwritten each time you restart X-Plane, so it's important to save a copy of it before you restart X-Plane.

X-Plane will also usually create a crash report in `Output/crash_reports`. The crash file will either be a `.dmp` or `.rpt` file (or maybe even both).

**It's very important that you include both the crash report and the `Log.txt` when reporting a crash. Without this information, it's impossible to know what caused X-Plane to crash.**

## FAQ

**I can't see any aircraft when I connect**\
Ensure that you don't have other plugins that could be interfering with xPilot (e.g. XSwiftBus, XSB, X-IVAP, etc.). If you are using X-Plane 11.50, make sure you are using xPilot 1.3.0 or greater. Check that the paths to your CSL package folders are defined in the xPilot settings within X-Plane (Plugins > xPilot > Settings).

**I'm being constantly disconnected because my frame rates are too low**\
xPilot requires that the user always maintains at least 20 FPS during flight. The reason for this is to prevent a phenomena called "time dilation", which is when the simulation rate of X-Plane drops below real-time, which results in an aircraft flying slower on radar than what their groundspeed reports. X-Plane enforces a strict 20 FPS minimum to ensure the simulation rate runs in real-time. You can read more about this here: https://www.x-plane.com/kb/the-simulators-measurement-of-time-is-slow/

**I can't see any TCAS targets on my plane's radar**\
Make sure you don't have any other plugins installed that could be interfering with xPilot (e.g. XSwiftBus, XSB, X-IvAP, etc.)

**Network Error: The server failed to respond to the authentication challenge**\
This is typically caused by a poor connection between you and the network server you are connected to. Try changing to a different server and try again.

**I can't transmit and/or receive audio in my aircraft. The COM radios are grayed out in xPilot**\
Make sure your radio stack in the aircraft is properly configured for TX and RX. In some cases, the aircraft model may not have a working audio panel, in which case you can trick xPilot into enabling TX and/or RX via a dot command. To enable TX on a specific COM radio, use the command `.tx com#`. To enable RX on a specific COM radio, use the command `.rx com# on/off`. For example, to force COM1 to transmit, you would type `.tx com1`. Similarly, to enable RX on COM2, you would use the command `.rx com2 on`.

**xPilot doesn't connect to X-Plane - stuck on "Waiting for X-Plane Connection"**\
If xPilot is indefinitely stuck on the "Waiting for X-Plane Connection" message, this means that xPilot is unable to communicate with X-Plane via a UDP port. Ensure that X-Plane is running and that it is not blocked in your Windows Firewall (https://www.x-plane.com/kb/allowing-x-plane-through-your-firewall/). Also ensure that the UDP ports in X-Plane (Settings > Network > UDP Ports) are set to 49010, 49000 and 49001, respectively (these are the default port numbers). xPilot specifically uses port 49000 ("Port we receive on (legacy)") to establish its connection with X-Plane. If you do need to make a change to the UDP port(s), make sure to restart X-Plane for the changes to take effect.

**Error connecting to voice server: Connect failed (Forbidden -)**\
If you recently created or reactivated your VATSIM account, you will need to wait up to 24-hours for your account to synchronize. Until your account is synchronized, you will not be able to use voice - only text.

## Known Issues

* **Some plugins or addons are known to cause X-Plane to crash when paired with xPilot. These crashes are attributed to the new TCAS Override API that was implemented in X-Plane 11.50.**

    * Little Xpconnect: Upgrade to v1.0.19 (or whichever version is newest). https://github.com/albar965/littlexpconnect/releases/tag/v1.0.19

    * Active Sky XP: Make sure you have the (beta) latest version installed.