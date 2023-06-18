sh run int Gi0/0/1.20


show standby br


## To check end device reachability
```
ping vrf INSIDE <user or printer or machine ip> 
```
show ip arp vrf INSIDE


show ip route vrf INSIDE <user ip>
  

sh ip bgp all sum
  

show dmvpn
  

sh arp vrf OUTSIDE
  

ping vrf INSIDE 10.195.96.1 repeat 500
  

ping vrf OUTSIDE 14.142.179.197 source 14.142.179.198 repeat 1000 size 1360
