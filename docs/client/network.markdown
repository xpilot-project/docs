---
layout: home
title: Running xPilot Over a Network
parent: xPilot Client
nav_order: 11
---

# Running xPilot Over a Network
To use xPilot over a network with multiple computers running X-Plane visuals, follow these steps:

1. Install the xPilot plugin on each computer running X-Plane visuals using the xPilot installer.

2. Enable TCP/IP support by modifying the xPilot plugin configuration file. Locate the `Config.json` file in the `X-Plane/Resources/plugins/xPilot/Resources/` directory. Open it with a text editor and change the value of the `UseTcpSocket` option to `true`. Save and close the file. Repeat this step for each X-Plane instance on the visual machines. Note that X-Plane should be closed before modifying the configuration file.

3. Start xPilot and use the command `.visualip` followed by the IP addresses of your visual machines. For example, `.visualip 192.168.1.50 192.168.1.60`. Restart xPilot for the changes to take effect. The visual machine IP addresses will be saved in the xPilot client configuration for future use. To clear the visual machine IP addresses, use the command `.visualip` without specifying any IP addresses.

Alternatively, if you want to run the xPilot client on a separate computer from the one running X-Plane, you can use the `.simip` command. Run xPilot on the separate computer and use the command `.simip <X-Plane_IP>` to set the IP address of the computer running X-Plane. For example, `.simip 192.168.1.100`. To clear the IP address, enter the command `.simip` without specifying an IP address. Note that the xPilot client must be closed before making changes to the configuration file, and it is recommended to use this command only if you are familiar with the setup.

Remember to follow the necessary precautions and ensure that your network and system configurations are properly set up to support xPilot over a network.