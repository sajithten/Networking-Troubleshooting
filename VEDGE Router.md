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
