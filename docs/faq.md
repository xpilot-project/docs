# FAQ

* **Where is the xPilot client config file?**
    * Windows: `C:/Users/<USER>/AppData/Local/org.vatsim.xpilot/AppConfig.json`
    * macOS: `~/Library/Application Support/org.vatsim.xpilot/AppConfig.json`
    * Linux: `~/.local/storage/org.vatsim.xpilot/AppConfig.json`

* **I'm being constantly disconnected because my frame rates are too low**<br/>
VATSIM requires that the X-Plane users maintain at least 20 frames-per-second during flight. The reason for this is to prevent a phenomena called "time dilation", which is when the simulation rate of X-Plane drops below real-time, which results in an aircraft flying slower on radar than what their groundspeed reports. X-Plane enforces a strict 20 FPS minimum to ensure the simulation rate runs in real-time. You can read more about this here: https://www.x-plane.com/kb/the-simulators-measurement-of-time-is-slow/

* **I can't see any TCAS targets on my plane's radar**<br/>
Make sure you don’t have any other plugins installed that could be interfering with xPilot (e.g. XSwiftBus, XSB, X-IvAP, etc.)

* **Network Error: The server failed to respond to the authentication challenge**<br/>
This is typically caused by a poor connection between you and the network server you are connected to. Try changing to a different server and try again.

* **I can’t transmit and/or receive audio in my aircraft. The COM radios are grayed out in xPilot**<br/>
Make sure your radio stack in the aircraft is properly configured for TX and RX. In some cases, the aircraft model may not have a working audio panel, in which case you can trick xPilot into enabling TX and/or RX via the `.tx` and/or `.rx` dot commands. See the [Dot Commands](client?id=dot-commands) section for details.

* **xPilot doesn't connect to X-Plane - stuck on "Waiting for X-Plane Connection"**<br/>
Ensure that X-Plane is running and that it is not blocked in your Windows Firewall (https://www.x-plane.com/kb/allowing-x-plane-through-your-firewall/). Also ensure that the UDP ports in X-Plane (`Settings > Network > UDP Ports`) are set to `49010`, `49000` and `49001`, respectively (these are the default port numbers). xPilot specifically uses port 49000 *(Port we receive on (legacy))* to communicate with X-Plane. If you have to reset the ports back to the defaults, you will need to restart X-Plane and xPilot for the changes to take effect. Also, if you have the `xswiftbus` plugin for the Swift pilot client, please try to remove it as it interferes with the operation of xPilot's.

* **Error connecting to voice server: Connect failed (Forbidden -)**<br/>
If you recently created or reactivated your VATSIM account, you will need to wait a few minutes for your account to synchronize; and in some cases, up to 24-hours. Until your account is synchronized, you will not be able to use voice &mdash; only text.
