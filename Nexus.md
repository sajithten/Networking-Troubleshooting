```
sh fabricpath route switchid 1532
```
##  To check status of switch stack members
```
sh switch detail
```
## To check fan, temp of fex 110
```
sh env fex 110 

```
## To check interface state under po102
```
show port-channel summary interface port-channel 102
```
```
sh ip route 10.38.72.200 vrf 1:1100
```
## To cpu usage
```
show processes cpu history sh processes cpu sort | ex 0.0
```
## To clear counter for an interface
```
clear counters interface Ethernet110/1/7 
```
