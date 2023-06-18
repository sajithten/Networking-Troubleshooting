## To check whethe IP is natted
```
show xlate | in 10.236.4.134

```
```
sh fai his
```
## For replicating traffic, mac add is the outside interface mac add

```
packet-tracer input inside tcp 10.253.17.89 1234 10b3.d50d.750f 10.37.2.10 3889

```
## Live connection
```
show connection | i 10.37

```
##  For live capture

```
cap ccpi type raw-data interface inside match ip host 10.x(source) host 10.x(destination)
```
## To stop packet capture
```
capture pc-traffic-ssh interface INSIDE match tcp host any eq 22
sh capture
sh capture capo-out
Sh capture capo-in
no capture ccpi 
```
## To check rules present 
```
show access-list | i 10.180

sh run | i 10.180

```
