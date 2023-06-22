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
## To disable domain lookup
```
no ip domain-lookup
```
---
## To set speed
This example shows how to configure port 1 on module 2 to auto:
```
Console> (enable) set port speed 2/1 auto
Port 2/1 speed set to auto-sensing mode.
Console> (enable)
  ```
This example shows how to configure port 2 on module 2 port speed to 10 Mbps:
```
Console> (enable) set port speed 2/2 10
Port 2/2 speed set to 10 Mbps.
Console> (enable)
  ```
This example shows how to configure port 4 on module 3 port speed to 16 Mbps:
```
Console> (enable) set port speed 3/4 16
Port(s) 3/4 speed set to 16Mbps.
Console> (enable)
  ```
  ---
