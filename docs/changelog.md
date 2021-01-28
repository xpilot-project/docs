# Changelog

## 1.3.37 - 01/27/2021
- Add nullptr check for XPLMInstanceRef, possible fix for random crashes

## 1.3.36 - 01/23/2021
- Remove mutex locks from airplane management class
- Nearby ATC Window mouse click events updated. Single-click will request the controller info/text ATIS. Double-click will tune the COM1 frequency to the selected controller/station.

## 1.3.35 - 01/18/2021
- Refactor callback function queuing - possible fix for random crashes

## 1.3.34 - 01/11/2021
- Fix data race during CSL object instance deletion.
- Fix duplicate characters in Text Message Console.

## 1.3.32 - 10/24/2020
- Possible fix for the CTD when the CreateInstance function is called.
- Update XPMP2 library. Previously, the CSL2XSB script was needed to convert CSL model packages (like X-CSL) to work properly with xPilot. Now, xPilot will now automatically convert the CSL model object on demand when it's used.

## 1.3.31 - 08/31/2020
- Implement a "dynamic range compressor" to try to reduce or stop the stray high-volume levels that cause audio clipping. You can read more about it here: https://markheath.net/post/limit-audio-naudio
- Fix DirectoryNotFoundException during Guided Setup.
- Fix ArgumentOutOfRangeException during Guided Setup when setting the input volume level.
- Fix issue with radio volumes not being updated outside of the settings window.
- Re-implement "Aircraft volume knobs control volume" setting option. If this option is checked, the radio volume can be controlled using the volume knobs within the aircraft. Additionally, if this option is checked, the volume level will not be saved and will reset to the aircraft volume knob level each time xPilot and X-Plane are started.
- Add "Tune COM1 Frequency" option to controller list context menu in the xPilot client.
- Installer updated to remove the automatic X-Plane path detection. The X-Plane path step has been re-implemented.

## 1.3.30 - 08/16/2020
- Remove external scripts from installer that were causing false positives with Antivirus software preventing the X-Plane plugin from being installed properly
- Add the ability for multiple Visual IP machines

## 1.3.29 - 08/14/2020
- Installer updated to automatically install the xPilot plugin on all X-Plane installations found on the computer (uses the "x-plane_install_11.txt" to locate the paths).
- Installer will stop the user from starting the installation if X-Plane.exe or xPilot.exe is running.
- Uninstaller will now remove the xPilot plugin from X-Plane.
- Client and Plugin now use Dealer/Router ZMQ socket types. Previously, ZMQ PAIR sockets were used, but were not designed for true TCP communication.
- ZeroMQ library (libzmq) downgraded to v4.3.1. This fixes a CTD when loading X-Plane for some users.
- Flight plan form updated to require equipment suffix when sending flight plan. A "what’s this" link has been added above the equipment suffix that links to the VATSIM PRC.
- Plugin hash verification processing moved to within the plugin. This fixes an issue with using networked computers (sim and visuals) not being able to connect to xPilot.
- Default TCP port number (for new installations) changed to 43001 to avoid conflict with XSwiftBus.
- "Configuration Required" notification text has been updated to remove the requirement to set the X-Plane path.
- Improve radio volume handling:
    - Volume sliders and aircraft volume dataref are now synchronized
    - Changed volume slider range which should allow for more decibel granularity
    - Remove checkbox to "override volume with volume knobs"

## 1.3.27 - 08/08/2020
- Automatically detect X-Plane path which fixes "unauthorized client" error
- Remove "X-Plane.exe Path" option from xPilot Settings

## 1.3.26 - 08/07/2020
- Update CSL download endpoint
- Add additional X-Plane path validation on client startup. If defined path is invalid or not set, prompt user to set path and choose from a list of path(s) based on x-plane_install_11.txt
- Rebuild configuration file if unable to load it
- Improve textual information on CSL Configuration step

## 1.3.25 - 08/07/2020
- Fix missing aircraft issue (attempt #2)
- Change how app config json string is saved to file (attempt to fix corrupt app config)

## 1.3.24 - 08/06/2020
- Add "Guided Setup" for new installations of xPilot
- Add ability to run xPilot on two instances of X-Plane (one copy for the sim and the other for visuals)
- Fix issue with missing aircraft
- Change endpoint for change log
- Fetch flight plan information from network instead of datafeed
- Don't enforce FIPS policy on xPilot client
- Add command to toggle aircraft labels
- Fix jittery aircraft in ABC (A Better Camera)
- Add additional mutex checks to airplane/interpolation stack maps to ensure proper synchronization
- Fix issue with max label distance/label cutoff options not being saved

## 1.3.23 - 08/03/2020
- Fix "Waiting for X-Plane connection..." issue
- Only change radio volume datarefs if volume knob control override is enabled (fixes issue with volume level not saving)

## 1.3.22 - 08/02/2020
- Enforce UTF-8 encoding in VATSIM datafeed data
- Fix form scaling
- Disable "Connect" button if no CSL paths are defined
- Fix flight plan import from .vfp file
- Allow main interface form to be resized smaller
- Fix missing SoundManager implementation (this will fix the missing notification sounds issue)

## 1.3.21 - 08/01/2020
- xPilot is now open-source
- Client configuration file is now serialized in JSON. Upgrades from earlier versions will require reconfiguration.
- Add volume knob control override option
- Add option to change the aircraft label distance
- Improve NetMQ message queuing
- Update XPMP2 library

## 1.3.20-Alpha - 07/14/2020
- Fix issue that caused X-Plane to crash when hiding or dragging the Notification Bar in VR
- Fix issue that caused X-Plane to crash due to an X-Plane SDK function being called outside the main X-Plane thread

## 1.3.19-Alpha - 07/07/2020
- Fix issue that caused X-Plane to crash when notifying the us that another plugin has acquired AI aircraft first

## 1.3.18-Alpha - 07/06/2020
- Fix issue that caused X-Plane CTD with new notification box
- Add missing command handler for Contact ATC Override

## 1.3.17-Alpha - 06/30/2020
- Added dual radio volume control capability. This means you can now control the radio volume via the volume knobs separately for COM1 and COM2. The volume multiplier has also been slightly increased since the initial release in 1.3.16.
- Fixed unhandled exception when downloading network server list.
- Added transparent notification window that appears at the top of the X-Plane window. This replaces the automatic popup of the radio text message window (now known as the "Text Message Console").
- Text Message Console command has been renamed from "xpilot/toggle_text_window" to "xpilot/toggle_text_message_console".
- Added network callsign data (xpilot/login/callsign). The dataref value is empty when not connected to the network.
- Added COM1/COM2 radio receive indicator datarefs (xpilot/audio/com1_rx and xpilot/audio/com2_rx). These datarefs replace the previous ("xpilot/audio/rx") dataref. A value of 1 indicates radio audio is being received. A value of 0 indicates no audio is being received.
- Update imgui library

## 1.3.15-Alpha - 06/17/2020
-  Added file browser to CSL configuration to easily browse and select the path to the CSL models
-  Aircraft label color options have been reverted to radio buttons
-  Tweak GUI windows so that they are centered on the screen on first load
-  Added close button to tabs in Text Message window
-  X-Plane native map integration has been re-enabled
-  Legacy TCAS hack added for previous X-Plane versions that do not support the new TCAS override
-  Added popup modal if an error occurs while trying to save the xPilot preferences
-  Frame rate detection code moved from client to X-Plane plugin

## 1.3.14-Alpha - 05/26/2020
-  Add menu option (in X-Plane) to disable TCAS
-  Additional validation on remote aircraft type codes (Max 4 characters. If dash exists, get text left of dash (e.g. B737-700 = B737))
-  Automatically replace forward slash (/) with backslash (\\) in CSL path configuration

## 1.3.13-Alpha - 05/26/2020
-  Fix issue that caused X-Plane to crash when initializing TCAS

## 1.3.12-Alpha - 05/22/2020
-  Allow plugin GUI windows to be moved
-  Add missing aircraft callsign labels to X-Plane map
-  Add nullptr check to TCP messaging socket

## 1.3.11-Alpha - 05/22/2020
-  Additional sanity checks for missing or misconfigured CSL paths
-  Fix ASSERT error when updating CSL paths
-  Fix imgui font atlas to prevent font artifacts when opening and closing a window
-  Update libzmq to latest version
-  Refactor plugin configuration management
-  Refactor aircraft label color management; color options are now buttons instead of radio buttons
-  TCAS now working (X-Plane 11.50b8 or newer only). TCAS is not supported in earlier versions of X-Plane
-  Possible fix for plugin GUI windows not showing for some users (needs further testing)

## 1.3.10-Alpha - 05/17/2020
-  Numerous code fixes that should help with the random crashes
-  Code improvements for X-Plane 11.50 B9
-  Includes a potential fix for the randomly increasing radio volume
-  Changed the min/max values for the input and output volumes (per AFV specs)
-  Added callsign to taskbar text when connected
-  Disabled integration with X-Plane map due to a bug in X-Plane that causes crashes when the map is opened
-  Added (again) the ability to change the VHF Equalizer
-  Added "xpilot/audio/vu" dataref (input audio volume level)
-  New TCAS integration (https://developer.x-plane.com/article/overriding-tcas-and-providing-traffic-information/). Only supported in X-Plane 11.50b8 or newer. TCAS will not be supported in earlier versions of X-Plane.
-  Renamed plugin menu items: 
    -  Settings -> Preferences
    -  Who's Online? -> Nearby ATC
    -  Radio Messages -> Text Window
-  X-Plane commands renamed. This may require you to re-map them in X-Plane if you used them previously:
    -  Nearby ATC Window
    -  Text Window
    
Fair warning: You may notice some odd behavior with other aircraft and how they are rendered in your sim. There is a bug in a previous version of xPilot which caused it to not properly share the aircraft configurations with other pilot clients, which results in odd behaviors with the aircraft surfaces (e.g. the aircraft oscillating up and down, landing gear extending and retracting randomly, etc.). This problem will correct itself once other users upgrade their xPilot version.

## 1.3.7-Alpha - 04/29/2020
- - Previously 1.3.6, but I forgot to include the new plugin in the installer- - 
-  Fixed an issue (hopefully!) that causes a crash to desktop when xPilot tries to remove a remote aircraft
-  Fixed issue with aircraft labels mirrored in Vulkan mode (aircraft labels were still visible if the camera view was turned 180Â°)
-  xPilot will attempt to read the vertical offset value from the CSL object directly if an offset is not found in the xsb_aircraft.txt file
-  Use true semantic versioning (major.minor.patch)

## 1.3.5.0-Alpha - 04/25/2020
-  Redesigned Radio Messages Window (https://forums.vatsim.net/topic/27243-xpilot-alpha-1350-alpha-now-available/)
-  Fixed imgui assertion crash

## 1.3.4.1-Alpha - 04/26/2020
-  Fixed an issue that caused unwarranted text radio transmissions when using the Radio Messages window within X-Plane
-  Aircraft labels are now positioned above aircraft instead of on the body of the aircraft

## 1.3.4.0-Alpha - 04/26/2020
-  "Fetch From Server" button will now fetch a pre-filed flight plan on first click
-  Fix issue with aircraft "falling to the ground" when flaring on landing
-  xPilot will now automatically disconnect if the xPilot X-Plane plugin becomes disabled (e.g. through a plugin manager)
-  Refactored interop messaging (that's how xPilot communicates with the xPilot X-Plane plugin)
-  Added missing spoiler/speed brake aircraft configuration property; this means you should now see if an aircraft deploys their spoilers/speed brakes (if their pilot client supports the aircraft configuration packet)
-  General program stability improvements

## 1.3.3.0-Alpha - 04/19/2020
-  The default CSL folder (Resources/plugins/xPilot/Resources/CSL) is no longer automatically added as an entry to the CSL Package configuration. Read more on the CSL Package configuration changes below.
-  Added the ability to change aircraft label colors (5 additional predefined color options).
-  Updated version check code. There is now an option specify which version channel (alpha, beta, stable) you want to use to check for updates.
-  Statically link C++ runtime libraries which eliminates the need to download the latest Visual Studio C++ redistributable package.
-  Miscellaneous performance tweaks.

## 1.3.1.1 - 04/13/2020
-  Fixes an issue that caused X-Plane to crash or hang if not CSL paths are defined, or if the default CSL directory is empty.

## 1.3.1.0 - 04/13/2020
-  Fixes an issue that caused CSL packages within the default CSL folder to not be loaded. xPilot will now also look up to 5 folder layers deep for CSL packages.
-  Aircraft labels now work in Vulkan mode.
-  Fixed issue that caused aircraft labels to not initially load and would require toggling them off and on.
-  Added an option to override the "Contact ATC" command.
	-  Enabling this option will disable the _Contact ATC_ command within X-Plane so these users do not have to manually map and un-map the command when using other networks.
	
## 1.3.0.2 - 04/08/2020
-  Fixes the character encoding of specific log file entries.
-  Fixes an issue that caused font artifacts within the Settings window if the xPilot plugin was disabled and re-enabled through a plugin manager.

## 1.3.0.1 - 04/08/2020
-  Fixes an unhandled exception for users not running X-Plane 11.50 when xPilot checks if Vulkan mode is enabled.

## 1.3.0.0 - 04/08/2020
-  Initial X-Plane 11.50 support by implementing the Instancing API to draw aircraft CSL objects.
-  TCAS aircraft are now injected into the default X-Plane map.
-  The plugin configuration has been converted to use JSON format. This will require CSL paths to be re-configured through the [xPilot settings within X-Plane](#).

## 1.2.1.0 - 01/24/2020
-  Fixes an issue with tuning the COM1 frequency through the _Who's Online_ window within X-Plane.
-  Fixes an issue that could cause default X-Plane ATIS to still play even if disabled through the xPilot settings.

## 1.2.0.0 - 01/23/2020
-  New low frame rate detection logic
-  Added the ability to connect with only an output audio device. This is useful for users who wish to fly as "receive only".
-  Added voice server auto-reconnect
-  Fixed an issue with the - .wallop-  command not sending the full message.

## 1.1.9.1 - 01/07/2020
-  Added an option to open the _Radio Messages_ window if a high priority message or alert is received. A high priority message may include (but not limited to): network disconnect notification, new private message notification, low frame rate warning.
-  Low frame rate notifications are now displayed in a transparent message box at the top of the simulator window. Note: If you have the "High Priority Messages" option enabled, the window will _still_ open when a low frame rate warning is triggered.

## 1.1.9.0 - 01/06/2020
-  Significant tweaks to the frame rate logic. Special thanks to Chris Collins and the rest of the XSB team for their assistance on this.
-  PTT configuration has been added back into the xPilot client. You can still set your PTT using the X-Plane keyboard/joystick bindings if you prefer.
-  The xPilot Toggle has been brought back into the client and the command has been removed from the X-Plane bindings.
-  The transparent radio messages area has been replaced with a GUI window (similar to the settings and who's online list).

## 1.1.8.0 - 01/04/2020
-  Added a "Who's Online" window that is accessible within X-Plane. The window can be opened either through the xPilot plugin menu or by assigning a keyboard/joystick shortcut using X-Plane Keyboard Shortcuts. You can quickly tune your COM1 active frequency by double clicking on a controller in the list. You can also right click on the controller line and request the text ATIS/controller info.
-  Removed PTT configuration from the xPilot client. You must now set your PTT within X-Plane using X-Plane keyboard shortcuts.
-  Removed "Toggle xPilot Visibility" from the xPilot client. You may now set a key to bring xPilot forward using X-Plane keyboard shortcuts.
-  Changing the plugin port number now requires xPilot and X-Plane to be restarted. This is to prevent weird anomalies that occurred when changing the port number on demand.

## 1.1.7.0 - 12/15/2019
-  Identified and fixed an issue that caused higher than normal CPU utilization. In my limited testing, the CPU utilization for xPilot has been reduced up to 50%. This should help to resolve stuttering issues.
-  Settings window within X-Plane now uses ImGui for the UI controls
-  Model matching debug is now turned off by default. It can be enabled in the xPilot settings within X-Plane
-  Added a menu option within X-Plane to quickly enable or disable the built-in X-Plane ATIS (it can be accessed through Plugins > xPilot > Enable Default ATIS)
-  Removed low frame rate popup dialog. xPilot will now automatically disconnect you from the network if your framerate is continuously below 20fps.

## 1.1.6.0 - 11/28/2019
-  Fix issue that could prevent the transponder ident button from sending the ident status to the network
-  Add network connection status dataref (xpilot/login/status) integer, 0 = disconnected, 1 = connected
-  Add audio receive status dataref (xpilot/audio/rx) integer, 0 = no audio being received, 1 = audio being received
-  Play alert sound if forcibly disconnected from the network
-  Play alert sound if unintentionally disconnected from the voice server
-  Fix issue that could cause an unhandled exception if the ptt key/button is pressed prematurely through the binded X-Plane command before the voice server connection is started
-  Re-design Settings window
-  Reinstate aural notification for incoming radio messages. A new option has been added to the settings window to disable this. Note: You will still receive an aural notification for direct radio messages regardless of your settings
-  Changing the audio input and output device now takes effect immediately.
-  The "Disable realistic radio effects" now takes effect immediately
-  Add change log to the new update dialog
-  If X-Plane is still running when an update is downloaded, a notification message will appear prompting the end user to close X-Plane before installing the update
-  Don't connect to voice server in towerview mode
-  Set xpilot/ptt dataref value if the PTT set within the UI client is toggled

## 1.1.5.0 - 11/06/2019
-  Changed sound for new incoming private message
-  Aircraft are removed from the sim if it's been 10 seconds or longer since their last position update
-  Added ability to load and save flight plans (supports vPilot flight plan format)
-  Added "Swap" button in flight plan window to swap the departure and destination field values

## 1.1.4.1 - 11/06/2019
-  Fix issue that may cause aircraft on the ground to be sunken into the terrain

## 1.1.4.0 - 11/05/2019
-  Added the ability to bind a joystick button and/or keyboard key for your PTT within X-Plane ("xpilot/ptt" command). This should allow VR users to bind a PTT button on their VR device
-  Increased dataref refresh rate from 1hz to 5hz (this makes things like switching your com radio frequency a bit quicker)
-  Implemented plugin version validation. You will be alerted within the main xPilot window if your plugin version is out of date.
-  Network CID and password are now trimmed of extra whitespace characters
-  Fixed an issue that could cause an unhandled exception if the observer callsign length was too long

## 1.1.3.0 - 11/02/2019
-  Added .rx and .tx dot commands for aircraft models that do not use standard com radio datarefs
-  Only play aural notification for direct radio messages
-  Play aural notification when a private message is received

## 1.1.2.0 - 10/28/2019
-  Further optimization to the aircraft management class (to help address the issue with lagging aircraft when there are lots of aircraft in the vicinity)
-  Stock ATIS is now only disabled when xPilot is connected to the network. When xPilot is disconnected, the stock ATIS is enabled again

## 1.1.1.1 - 10/23/2019
-  Added TCAS functionality to plugin
-  Fix issue that can cause an unhandled exception when connecting to voice server if network credentials are incorrect
-  Remove character casing restriction on flight plan remarks field
-  Tweak .msg/.chat commands to accept an initial message string
-  Save flight plan if fetched from server
-  Fix issue that prevented SELCAL code from being saved in the recent connection history

## 1.1.1.0 - 10/21/2019
-  Implemented .towerview command
-  Fixed input and output volume levels
-  Fixed issue that may cause X-Plane to crash when attempting to remove an aircraft

## 1.1.0.7 - 10/21/2019
-  New aircraft interpolation code. This should help prevent other aircraft from randomly disappearing or freezing
-  Fix issue that caused an unhandled exception upon the voice server disconnect.

## 1.1.0.6 - 10/19/2019
-  Fix issue that caused X-Plane to crash when an aircraft was removed from the sim
-  Further optimize networking code between X-Plane and xPilot
-  More tweaks to the ground clamping code

## 1.1.0.3 - 10/18/2019
-  Fix for aircraft sunken below the ground

## 1.1.0.2 - 10/15/2019
-  Ensures pilots end up on the right frequency (HF aliasing)

## 1.1.0.1 - 10/14/2019
-  Fixes issue with transponder mode not being correctly relayed to the FSD server for Toliss Airbus

## 1.1.0.0 - 10/13/2019
-  Initial public beta release