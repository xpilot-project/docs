---
layout: home
title: Notification Panel
parent: X-Plane Plugin
nav_order: 5
---

# Notification Panel
All notifications (text radio messages, private messages, network broadcast alerts, server messages, etc.) will appear in the translucent notification panel at the top right of the X-Plane window. If you hover over the notification panel, a scrollbar will appear allowing you to scroll through the messages. The notification panel will automatically hide after a set time. See the [Settings](/docs/xplane/settings.html) section for details on how to configure the timeout period.

![Notification Panel](/assets/images/NotificationPanel.png)

{: .important-title }
> VR Users
>
> Due to limitations with the X-Plane VR API, a VR window cannot be programmatically placed in a specific location. Because of this, the notification panel will be placed front and center each time it opens. As a workaround, toggle the notification panel (either through the plugin menu or via a binded command) to force the panel to stay open and then move it someplace else (like in the co-pilots seat).