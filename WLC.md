## To set your terminal to display without any breaks
```
config paging disable 
```
## To check for AP joined or not
```
show ap join stats summary all 
```
## To check no.of SSID broadcasted
```
show wlan summary 
```
## To check details of 2nd SSID from output of showwlansummary cmd
```
show wlan 2 
```
## To check no. clients associated in wlan 2
```
show client wlan 2 
```
## To ignore mic expiry
```
config ap cert-expiry-ignore mic enable 
```
## To check client details ex: how long client connected
```
show client detail 7C:21:4A:25:29:6B 
```
## To get the logs for specific mac add when trying to connect
```
debug mac addr 10:3D:1C:6F:23:A9
debug client 10:3D:1C:6F:23:A9
config paging enable

debug client AC:67:5D:2D:2E:9F 

debug disable-all

```
## To reset AP
```
ap name RNWwdEPLgolen22 reset 
```
## To get mgmt ip for login gui
```
show sysinfo 
```
## To check AP uptime
```
sh ap uptime 
```
## To change wlc date manually
```
config time manual 07/06/22 11:00:00 
```
##  To check client connected to AP
```
show wireless client summary 
```
## To see switch details connected to AP
```
show ap cdp neighbors all 
```
