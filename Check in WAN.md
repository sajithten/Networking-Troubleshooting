To check the public ip
```
show runnin-config vpn 0 int gre1
```
To check in primary nd secondary router if we find any drop, if so then need to check with ISP.
```
ping vpn 0 <public ip> rapid count 100
```
if no drop then check in thousand eyes if any latency, packet loss

[tower.network.apps.ge.com](http://tower.network.apps.ge.com/) - ansible - automation tool, we run script for health checkup

[capm02.apps.ge.com](http://capm02.apps.ge.com/) - to check utilization
if they need toptalkers report - then go to Network Flow Tos in capm

Thousandeyes - to check latency of WAN link, to check latency on which node on the path, To check Packet loss,
