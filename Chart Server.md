## To console device from neighboring device
```
ssh -l 503287061:serial 10.69.96.21
```
## To ssh to device from JUMP
```
ssh -l 503287061 <CI or IP add>
```
## To remove the known hosts from chart server
```
rm -f .ssh/known_hosts
```
## when showing "Host key verification failed" when trying to ssh a new device right after it's configuration done
```
ssh-keygen -R <CI or IP>
```
## grep command
```
g gehsc | grep bangb
```
## Traceroute devices from Jump server
```
traceroute <CI>
```
## To check in chart server whether destination IP port number is open or closed or filtered
```
nmap -Pn 10.114.19.201 -p 443
```
## To copy ios from chart server(use this when switch in enable mode)
```
copy tftp://192.35.38.45/cat3k_caa-universalk9.SPA.03.07.05.E.152-3.E5.bin flash: 
```
