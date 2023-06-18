## firewall version
```
fw ver
```
##  show interface names
```
fw ctl iflist    
```
## show control kernel memory and connections
``
fw ctl pstat    
``
## show SecureXL status
``
fwaccel stat 
``
## Get the policy from the firewall manager
``
fw fetch <manager IP>
``
## compile and install a policy on the target's gateways.
``
fwm load <policy name> <gateway name>    
``
##  list interfaces and IP addresses
``
fw getifs
``
##  show the content of the connections log
``
fw log
``
## search the current log for activity between specific times
``
fw log -b "MMM DD, YYYY HH:MM:SS" "MMM DD, YYYY HH:MM:SS"
``
## search for dropped packets in the active log; also can use accept or reject to search
``
fw log -c drop    
``
##  tail the current log
``
fw log -f   
``
## export an old log file on the firewall manager
``
fwm logexport -i <log name> -o <output name> -n -p    
``
##  rotate logs
``
fw logswitch   
``
## list firewall logs
``
fw lslogs    
``
##  firewall status, should contain the name of the policy and the relevant interfaces.
``
fw stat   
``
## show which policy is associated with which interface and package drop, accept and reject
``
fw stat -l    
``
## displays firewall tables
``
fw tab    
``
## number of connections in state table
``
fw tab -s -t connections    
``
## routing for remote vpns
``
fw tab -f -t vpn_routing -u    
``
##  number of remote users connected (VPN)
``
fw tab -s -t userc_users 
``
## clear all translated entries
```
fw tab -t xlate -x 
```
## clear local firewall policy
```
fw unloadlocal    

```

## trace the packet flow to/from the specified host
``
fw monitor -e "accept host(10.1.1.10);"    
``
##  Check reason of your packet being dropped
```
fw ctl zdebug + drop | grep 'x.x.x.x\|y.y.y.y'   
```
