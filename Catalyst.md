- sh int <interface name>  sh int port-channel 1  - To check status of an Interface:
  
- sh cdp nei  - To check all neighbour devices:
  
- show cdp nei | i POWwdSINhyder03 - to check particular neighboring devices
  
- show cdp nei | i sec CI -
  
- show int desc | i /1/14 | Po14
  
- To check which device connected to a particular interface(for eg: fa 0/23):  sh cdp nei <interface name> detail
  
- sh int description - To check Interface details & status
  
- To traceroute a particuler reachable AP which is connected to a switch for instance, gehwdefrbucmc27
  
- To get the Serial Number and Module details of a switch: sh inventory
  
- sh mac address-table int Ethernet104/1/1 - To View mac address seen on a specific interface in switch
  
- To View the dynamically learnt MAC addresses on switch show mac address-table dynamic
  
- To check how long a switch will store learnt MAC Addresses: show mac address-table aging-time
  
- To View History of logs: sh log & sh log | i <interface name>
  
- sh clock - To View System time
  
- To View IP addresses in a specific vlan: sh run int vlan2091
  
- To view the port and time the last TCN was received on and To check if the STP is stable: show spanning-tree detail | inc ieee|occurr|from|is exec  or  sh spanning-tree detail | i last
  
- To check whether the device is primary and secondary: show standby brief
  
- To check what type or Spanning tree port on a switch interface: show spanning‐tree interface <Interface name>
  
- To Display spanning-tree debugging messages: debug spanning‐tree events
  
- To Check uptime of device: show version | i uptime
  
- To check log on a port: show log | i 1/0/50
  
- To check STP Flap: sh spanning-tree detail | i last
  
- To check ROM: sh ver | in ROM
  
- To check Power supply: sh power
  
- To see L3 devices(for eg: rs) which is not showing in “sh cdp nei” command: sh int description | i SDWAN or  sh run int <Interface name to which L3 device connected, for ex: “Ten 5/10”>
  
- To view which vlan a particular Interface assigned to: sh run int g4/26
  
- To block a MAC address on an interface: mac address-table static 00:0E:8E:61:0F:A9 vlan 261 drop
  
- sh env all - To check temp, threshold, fan status
  
- show mac address-table address 00:0E:8E:61:0F:A9 - To trace the mac at layer 2
  
- sh mac address-table | in 46fa.8122.1ab3
  
- sh int status err
  
- to clear counters: clear counters int port-channel101
  
- sh int Ethernet1/21 status - to check duplex on interface:
  
- sh int FastEthernet0/28 switchport - To check interface switchport information
  
- sh int port-channel 101
  
- ping 10.185.224.76 source Vlan2300
  
- To View IP nd mac address for a specific VLAN in switch: sh ip arp vlan5
  
- show ip arp 172.23.0.5
  
- sh ip arp | i 10.60.8.141
  
- show ip arp Vlan2300 | i 10.185.224.76
  
- show logg last 10
  
- sh logg last 10 | i 0014.4ffe.23d9
  
- show logg logfile | i Loops
  
- traceroute mac 0000.0201.0601 0000.0201.0201
  
- traceroute mac interface fastethernet0/1 0000.0201.0601 interface fastethernet0/3 0000.0201.0201
  
- POWsdEPLwrocl03#ping vrf 1:2100 10.5.112.19 source Vlan2925 repeat 100 size 1350
  
- sh ip bgp all summary - To check BGP Neighbor Down
  
- sh bgp sessions vrf vrf_sdc - To check bgp neighbor in specific vrf
  
- sh ip ospf neighbor - To check OSPF Neighbor Down
  
- sh log | i %OSPF-5-ADJCHG
  
- sho etherchannel summary
  
- show switch virtual link  show redundancy  show redundancy states
  
- show tech
  
- sh power inline - To chech POE status of interface
  
- sh switch virtual
  
- sh switch virtual dual-active summary
  
- sh switch virtual redundancy
  
- sh switch virtual link port
  
- sh switch virtual dual-active fast-hello
  
- sh redundancy
  
- sh etherchannel summary
  
- show int status
  
- POWsdMMXciene04#ping 10.132.45.41 source 10.132.4.2 repeat 500
  
- POWsdMMXciene04#ping 10.132.45.41 source 10.132.4.2 repeat 100 size 1350
  
- POWsdEESmalag01# show vlans ports 19
  
- show processes cpu   show processes cpu history - To check CPU utilization
  
- sh proc cpu sorted sh proc cpu sort | ex 0.0 - To show which process is using the most CPU time
  
- terminal length 0 - to get lengthy result without page break
  
- term no len 0 -
  
- sh switch > session 4 - to login switch stack 4
  
- show environment status - to check power supply status
  
- sh run | i snmp
  
- show interface Te2/1/1 transceiver detail
  
- sh port-channel summary int po200
  
- CSSsdMUSalpdc02b-v# ping 10.141.3.107 vrf 1:1600 count 50
  
- sh int vlan id 251
  
- sh vlan id 251
  
- sh switch detail - To check stack ports details
  
- copy flash: ftp: - To copy ios image from switch to chart server
  
- show diagnostic result switch all
