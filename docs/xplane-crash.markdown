---
layout: page
title: X-Plane Crash
nav_order: 6
---

# X-Plane Quit Unexpectedly
In the event of an unexpected quit or crash (referred to as a "Crash to Desktop" or CTD) in X-Plane, you can refer to the `Log.txt` file to determine the cause. The last line of the `Log.txt` will typically indicate the reason for the crash. If xPilot is responsible for the crash, the last line will end with `--=={This application has crashed because of the plugin: xPilot}==--`.

Please note that the `Log.txt` file is overwritten each time you restart X-Plane. Therefore, it is crucial to make a copy of the `Log.txt` before restarting X-Plane if you wish to analyze the crash.

Additionally, X-Plane often generates crash reports in the `Output/crash_reports` directory. When reporting a crash, it is essential to include both the crash report and the `Log.txt` file. This information is vital for identifying the cause of the crash.