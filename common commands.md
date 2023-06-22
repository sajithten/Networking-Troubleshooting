The following commands create a message-of-the-day banner and enable its display:
```
Router(config)# banner motd  # All routers will be rebooted at Sunday 10AM #
Router(config)# motd-banner
```
The motd-banner command isn’t strictly necessary, since the display is enabled by default. To disable the display, use the no motd-banner command:
```
Router(config)#no banner motd
```
---
