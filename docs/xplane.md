# X-Plane Interface

The xPilot plugin communicates with the xPilot client and interfaces with X-Plane to render aircraft in the sim.

## Settings

The xPilot plugins settings can be accessed through the X-Plane menu: `Plugins > xPilot > Settings`.

All xPilot Plugin settings are saved to a file named `Config.json` in the `X-Plane 11/Resources/plugins/xPilot/Resources` folder.

![X-Plane Settings](media/XplaneSettings.png)

* **Automatically Show Message Preview Panel**<br/>If this option is enabled, if a new radio text message is received, it will display in a small translucent panel at the top right of the X-Plane window.

* **Hide Message Preview Panel After...**<br/>This option sets how long the message preview panel should stay open (in seconds) before it automatically disappears.

* **Enable Aircraft Labels**<br/>If this option is enabled, floating callsign labels will be placed above all aircraft in the sim.

* **Aircraft Label Color**<br/>You can set a custom or pre-defined aircraft label color (if the aircraft labels are enabled). There are four pre-defined colors: yellow, red, green and cyan. You can alternatively pick your own color by clicking the color square to the left of *Or Choose Color*.

* **Max Label Distance**<br/>This option sets how far away you can see aircraft labels (1-nautical miles to 10-nautical miles).

* **Hide Labels at Visibility Distance**<br/>If this option is enabled, aircraft labels will not be sown if the plane is beyond the current visibility range. If left unchecked, aircraft labels will show regardless of the current visibility conditions (i.e., if a plane is hidden in fog or behind clouds, the label will still show).

* **Log.txt Log Level**<br/>This option limits how much information is written to the X-Plane log.txt file. **Debug** will write the most information, whereas **Fatal** will write the least amount of information. It is recommended that you only change this if you experience odd behavior and need to log additional information for support requests.

* **Log Model Matching Results**<br/>If this option is enabled, debug information will be logged to the X-Plane log.txt file about how a CSL model was chosen. You should only enable this option if you need to determine why planes aren't rendering as expected.

* **Override "Contact ATC" Command**<br/>If this option is enabled, xPilot will ignore the "Contact ATC" X-Plane command. This is generally only useful for users who also fly on PilotEdge.

* **Default Aircraft Type ICAO**<br/>The fallback aircraft ICAO type designator that is used if no appropriate CSL model can be found for a plane. The plane will instead be rendered as this aircraft type as opposed to not rendering at all.

## CSL Configuration

xPilot has no complex or special model matching rule sets that need to be installed or configured. You must have at least one CSL model set package installed before you can use xPilot. The most popular model set is Bluebell CSL. When you first install xPilot, you will be prompted to install a CSL model set.

In the xPilot Plugin settings (accessed via `Plugins > xPilot > Settings`), there is a section to define the path(s) to where your CSL model sets are installed. You can define up to seven different paths.

![CSL Configuration](media/XplaneCSLConfiguration.png)

To define a new path, click the `Browse` button and browse to the root folder of your CS models, or manually type in the full path. If there are multiple subfolders, xPilot will search the folders for additional models.

You can disable a path from being loaded when you start X-Plane by unchecking the `Enabled` checkbox.

Each time you load the xPilot client, it will verify that you have CSL models installed and properly configured. If no models are found, or the path is invalid or not enabled, the Connect button will become disabled and a red error message will be presented in the main message area:

![Client CSL Error](media/ClientCSLError.png)

If you see this error, make sure you have a CSL model package installed (such as Bluebell CSL Models) and that the path is properly configured in the xPilot plugin settings. Restart xPilot and X-Plane after making the corrective changes.

**<span style="color:red;">Any time you make changes to the CSL configuration you must restart X-Plane for the changes to take effect.</span>**

## Command Bindings

There are several commands that can be binded to one or more keyboard keys, joystick buttons or switches within X-Plane. If you are not familiar with how to setup command shortcuts in X-Plane, please refer to the [X-Plane 11 Manual](https://www.x-plane.com/manuals/desktop/index.html#configuringkeyboardshortcuts) for more information.

**<span style="color:red;">At minimum, you must configure the Radio Push to Talk (PTT) command binding in order to communicate with controllers via voice on the network.</span>**

Available X-Plane Commands:

* **Radio Push to Talk (PTT)**<br/>Bind `xPilot: Radio Push-To-Talk (PTT)` command to transmit on a radio frequency while connected to the network.

* **Toggle Default X-Plane ATIS**<br/>Bind `xPilot: Toggle Default X-Plane ATIS` command to enable or disable the default X-Plane ATIS. xPilot will automatically disable the default ATIS when connected to the network, but you may enable it again using this command (or via the xPilot plugin menu).

* **Toggle Nearby ATC Window**<br/>Bind `xPilot: Toggle Nearby ATC Window` command to show or hide the Nearby ATC window.

* **Toggle Aircraft Labels**<br/>Bind `xPilot: Toggle Aircraft Labels` command to show or hide aircraft labels.

* **Toggle Message Preview Panel**<br/>Bind `xPilot: Toggle Notification Panel` command to show or hide the message preview panel.

* **Toggle Message Console**<br/>Bind `xPilot: Toggle Message Console` command to show or hide the text message console.

* **Toggle TCAS Control**<br/>Bind `xPilot: Toggle TCAS Control` command to request or release TCAS control. If another plugin already owns the TCAS targets and doesn't release them on request, xPilot will not have control.

## Text Message Console

In addition to using the xPilot Client interface to send or receive text radio messages or private messages, you can use the Text Message Console in X-Plane. You can open the Text Message Console through the X-Plane menu via `Plugins > xPilot > Text Message Console` or by binding a keyboard key or joystick button or switch to quickly toggle the visibility of the window. See the [Command Bindings](xplane?id=command-bindings) section for details.

![Text Message Console](media/TextMessageConsole.png)