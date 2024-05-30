---
layout: home
title: Settings
parent: X-Plane Plugin
nav_order: 1
---

# Settings
The xPilot plugins settings can be accessed through the X-Plane menu: `Plugins > xPilot > Settings`.

All xPilot Plugin settings are saved to a file named `Config.json` in the `X-Plane/Resources/plugins/xPilot/Resources` folder.

## General

![X-Plane Settings](/assets/images/XplaneSettings.png)

* **Automatically Show Notification Panel**<br/>If this option is enabled, if a new radio text message is received, it will display in a small translucent panel at the top right of the X-Plane window.

* **Hide Notification Panel After...**<br/>This option sets how long the notification panel should stay open (in seconds) before it automatically disappears.

* **Notification Panel Position**<br/>This option allows you to set the position of the Notification Panel in the X-Plane window.

* **Show Aircraft Labels**<br/>If this option is enabled, floating labels will be placed above all aircraft in the sim.

* **Aircraft Label Type**<br/>Select the type of label to show above other aircraft in the sim. Available options are: Callsign, Aircraft Type, Callsign + Aircraft Type, and Airline Code + Aircraft Type.

* **Callsign Label Color**<br/>You can set a custom or pre-defined aircraft label color (if the callsign labels are enabled). There are four pre-defined colors: yellow, red, green and cyan. You can alternatively pick your own color by clicking the color square to the left of *Or Choose Color*.

* **Max Callsign Label Distance**<br/>This option sets how far away you can see aircraft labels (1-nautical miles to 10-nautical miles).

* **Hide Callsign Labels at Visibility Distance**<br/>If this option is enabled, aircraft labels will not be sown if the plane is beyond the current visibility range. If left unchecked, aircraft labels will show regardless of the current visibility conditions (i.e., if a plane is hidden in fog or behind clouds, the label will still show).

* **Default Aircraft Type ICAO**<br/>The fallback aircraft ICAO type designator that is used if no appropriate CSL model can be found for a plane. The plane will instead be rendered as this aircraft type as opposed to not rendering at all.

* **Enable Transmit Indicator**<br/>Enable this option to see a green transmit indicator at the top left corner of your X-Plane window when you press your Push to Talk.

## Sounds

![X-Plane Settings](/assets/images/XplaneSoundSettings.png)

* **Enable Aircraft Engine Sounds**<br/>Enable this option to add ambient engine sounds to other aircraft.

* **Aircraft Engine Sound Volume**<br/>This slider changes the engine sound volume of other aircraft.

* **Aircraft Sound Playback Device**<br/>Select the audio device where you want the aircraft engine sounds to play. If left blank, xPilot will use the system default audio device.

## Contrails

![X-Plane Settings](/assets/images/XplaneSettingsContrails.png)

* **Enable Contrails**<br/>Enable this option to enable contrails on jet aircraft (may affect frame rate).

* **Minimum Altitude**<br/>The minimum altitude at which contrails are visible for jet aircraft.

* **Maximum Altitude**<br/>The maximum altitude at which contrails are visible for jet aircraft.

* **Life Time**<br/>How long (in seconds) does a contrail "puff" survive?

* **Multiple Contrails**<br/>Enable on contrail per aircraft engine (more realistic, but may affect frame rate).

## CSL Configuration

xPilot has no complex or special model matching rule sets that need to be installed or configured. You must have at least one CSL model set package installed before you can use xPilot. The most popular model set is Bluebell CSL. When you first install xPilot, you will be prompted to install a CSL model set. See the [CSL Installation](/docs/installation/csl.html) for details on how to install the CSL model set.

In the xPilot Plugin settings (accessed via `Plugins > xPilot > Settings`), there is a section to define the path(s) to where your CSL model sets are installed. You can define up to seven different paths.

![CSL Configuration](/assets/images/XplaneCSLConfiguration.png)

To define a new path, click the <span class="xplane-btn">Browse</span> button and browse to the root folder of your CS models, or manually type in the full path. If there are multiple subfolders, xPilot will search the folders for additional models.

You can disable a path from being loaded when you start X-Plane by unchecking the <span class="xplane-btn">Enabled</span> checkbox.

Each time you load the xPilot client, it will verify that you have CSL models installed and properly configured. If no models are found, or the path is invalid or not enabled, the Connect button will become disabled and a red error message will be presented in the main message area:

![CSL Error](/assets/images/ClientCSLError.png)

If you see this error, make sure you have a CSL model package installed (such as Bluebell CSL Models) and that the path is properly configured in the xPilot plugin settings. Restart xPilot and X-Plane after making the corrective changes.

**<span style="color:red;">Any time you make changes to the CSL configuration you must restart X-Plane for the changes to take effect.</span>**

## Advanced Options

![Advanced Options](/assets/images/XplaneAdvancedSettings.png)

* **Override "Contact ATC" Command**<br/>If this option is enabled, xPilot will ignore the "Contact ATC" X-Plane command. This is generally only useful for users who also fly on PilotEdge.

* **Log.txt Log Level**<br/>This option limits how much information is written to the X-Plane log.txt file. **Debug** will write the most information, whereas **Fatal** will write the least amount of information. It is recommended that you only change this if you experience odd behavior and need to log additional information for support requests.

* **Log Model Matching Results**<br/>If this option is enabled, debug information will be logged to the X-Plane log.txt file about how a CSL model was chosen. You should only enable this option if you need to determine why planes aren't rendering as expected.