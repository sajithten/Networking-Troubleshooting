tcpdump -npi any host 3.239.32.114 and "10.63.56.196 or 3.63.56.166”

tcpdump -nnpi any -vv host 3.35.167.5 and 10.42.185.27

set static-route 10.38.64.8/32 nexthop gateway address 3.36.235.1 on

cphaprob stat - list the state of the high availability cluster members. Should show active and standby devices.

cphaprob -a if - display status of monitored interfaces in a cluster

cphaprob -l list -  display registered cluster devices and status

cphaprob syncstat - display sync transport layer statistics

cphaprob ldstat - display sync serialization statistics

cphastop - stop a cluster member from passing traffic. Stops synchronization. (emergency only)

Fw version- to check the version ex. 80.40

show route destination 10.126.74.247 - this is server IP

show arp dynamic all

tcpdump -nnpi any host 10.2.128.250

tacacs_enable TACP-15 - to change to expert mode( priveliege mode) - default pass: IrAmpsNqNIqOZp6N9kfzD3GGEv

Fw stat - to know the policy status.

Cp view - to check the CPU status

cpconfig - change SIC, licenses and more

cpview -t - show top style performance counters

cphaconf set_ccp broadcast
cphaconf set_ccp multicast
cplic print

clusterXL_admin down –p - disable this node from cluster membership

cphaconf cluster_id get - get cluster Global ID membership

cphaconf set_ccp broadcast/multicast - set cluster mode

cplic print - license information

cpstart - start all checkpoint services

cpstat fw - show policy name, policy install time and interface table

cpstat ha - high availability state

cpstat blades - top rule hits and amount of connections

cpconfig    change SIC, licenses and more

cpview -t    show top style performance counters

cphaprob stat    list the state of the high availability cluster members. Should show active and standby devices.

cphaprob -a if    display status of monitored interfaces in a cluster

cphaprob -l list    display registered cluster devices and status

cphaprob syncstat    display sync transport layer statistics

cphaprob ldstat    display sync serialization statistics

cphastop    stop a cluster member from passing traffic. Stops synchronization. (emergency only)

clusterXL_admin down –p    disable this node from cluster membership

cphaconf cluster_id get    get cluster Global ID membership

cphaconf set_ccp broadcast/multicast    set cluster mode

cplic print    license information

cpstart    start all checkpoint services

cpstat fw    show policy name, policy install time and interface table

cpstat ha    high availability state

cpstat blades    top rule hits and amount of connections

cpstat os -f all    checkpoint interface table, routing table, version, memory status, cpu load, disk space

cpstat os -f cpu    checkpoint cpu status

cpstat os -f multi_cpu    checkpoint cpu load distribution

cpstat os -f sensors    hardware environment (temperature/fan/voltage)

cpstat os -f routing    checkpoint routing table

cpstat mg -f log_server    monitor log servers performance (events/sec)

cpstop    stop all checkpoint services

cpwd_admin monitor_list    list processes actively monitored. Firewall should contain cpd and vpnd.

show sysenv all    show hardware sensors (fans,power supply,temp,volt)

show asset all    show serial numbers and hardware info

show route destination xx.xx.xx.xx    show routing for specific host

ip route get xx.xx.xx.xx    show routing for specific host

iclid / show cluster state    show cluster fail over history

promote_util    promote the Secondary Management server to become the Primary server

cp_conf sic init key123 norestart    reset SIC without restarting the firewall process
