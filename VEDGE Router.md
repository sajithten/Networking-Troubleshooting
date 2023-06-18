## To check link status
```
sh omp peer
```
To check interface on netbrain
```
sh int description | t 
sho app cflowd flows | i 5246
```
## To check flapping for gre tunnel
```
sh int gre* | t 
```

AIRrsEPLinnow01# tools iperf options "-c [ping.online.net](http://ping.online.net/) -P 10"
AIRrsEPLinnow01# tools iperf options "-c [ping.online.net](http://ping.online.net/) -P 10 -r"

show running-config vpn 1999 int ge0/1.288 - 

## To check arp entries in wired nd wireless user’s
```
show arp vpn 1999 
```
## To check link status btw vsmart nd vbond

```
sh omp peers |t 

```
## To check ISP tunnel mac address, no isp communication if mac is 0
```
sh arp vpn 0 |t 
```

POWrsSMYkuala01# ping vpn 0 165.225.112.14 rapid count 100 size 1360

## step troubleshoot for packet drop

```
[4:27 PM] Raut, Santosh (GE Corporate, consultant)

RNWrsEPLgolen02# show interface description | tab

IF      IF      IF                                                                                                    AF                      ADMIN   OPER    TRACKER                                                                            VPN   INTERFACE    TYPE  IP ADDRESS        STATUS  STATUS  STATUS   DESC                                                                      
---------------------------------------------------------------------------------------------------------------------------------------------------0     gre1         ipv4  172.20.61.105/30  Up      Up      NA       GRE1 to Zscaler                                                           0     gre2         ipv4  172.20.61.109/30  Up      Up      NA       GRE2 to Zscaler                                                           0     ge0/0        ipv4  62.67.24.202/29   Up      Up      NA       WAN_CIRCUIT Asset 441756230 | CENTURYLINK - CktID:441756230               0     ge0/1        ipv4  -                 Up      Up      NA       RNWsdEPLgolen01 Gi1/0/5 | Physical uplink to LAN                          0     ge0/2        ipv4  -                 Up      Up      NA       TLOC Extension to other vEdge at site                                     0     ge0/3        ipv4  -                 Up      Up      NA       RNWsdEPLgolen01 Gi2/0/5 | Physical uplink to LAN                          0     ge0/4        ipv4  -                 Down    Down    NA       -                                                                         0     ge0/5        ipv4  -                 Down    Down    NA       -                                                                         0     ge0/6        ipv4  -                 Down    Down    NA       -                                                                         0     ge0/7        ipv4  -                 Down    Down    NA       -                                                                         0     system       ipv4  10.39.234.23/32   Up      Up      NA       -                                                                         0     ge0/2.9      ipv4  172.31.63.2/30    Up      Up      NA       -                                                                         0     ge0/2.10     ipv4  172.31.63.6/30    Up      Up      Up       -                                                                         0     loopback100  ipv4  1.39.234.23/32    Up      Up      NA       -                                                                         
^CAborted: by user
RNWrsEPLgolen02# show running-config vpn 0 int gre1
vpn 0
interface gre1  description             "GRE1 to Zscaler"  ip address 172.20.61.105/30  tunnel-source-interface ge0/0  tunnel-destination      165.225.206.22  no shutdown  access-list ACL_ZSCALER_IN in
!
!
RNWrsEPLgolen02# show running-config vpn 0 int gre2
vpn 0
interface gre2  description             "GRE2 to Zscaler"  ip address 172.20.61.109/30  tunnel-source-interface ge0/0  tunnel-destination      165.225.72.34  no shutdown  access-list ACL_ZSCALER_IN in

4:27 PM] Raut, Santosh (GE Corporate, consultant)

RNWrsEPLgolen02# ping vpn 0 165.225.206.22 rapid count 200 size 1360
Ping in VPN 0
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!.!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!.!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!.!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
--- 165.225.206.22 statistics ---
200 packets transmitted, 197 received, 2% packet loss
RNWrsEPLgolen02# ping vpn 0 165.225.72.34 rapid count 200 size 1360
Ping in VPN 0
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
--- 165.225.72.34 statistics ---
200 packets transmitted, 200 received, 0% packet loss
RNWrsEPLgolen02# ping vpn 0 165.225.72.34 rapid count 300 size 1360
Ping in VPN 0
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
--- 165.225.72.34 statistics ---
300 packets transmitted, 300 received, 0% packet loss
RNWrsEPLgolen02# ping vpn 0 165.225.206.22 rapid count 300 size 1360
Ping in VPN 0
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!.!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
--- 165.225.206.22 statistics ---
300 packets transmitted, 299 received, 1% packet loss
RNWrsEPLgolen02#
RNWrsEPLgolen02#

```
