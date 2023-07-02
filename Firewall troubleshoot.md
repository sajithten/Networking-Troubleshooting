![image](https://github.com/sajithten/Networking-Troubleshooting/assets/110303586/7ab865fe-dfb8-4a8b-a022-02cb1b8476e2)
1. ask source, des and dest port, if they using citrix virtual desktop, ask ip add inside the virtual desktop
2. check on splunk, we can put source as 10.196.39.0/24 instead of 10.196.39.138. If we get a deny rule, then ask user to Raise Firewall SE Request by providing the link, firewall name
3. If we not get any result in splunk,:
one reason could be there’s no firewall in place at all.
Another reason could be the source not initiating the connection correctly, traffic blocked from source like maybe in windows firewall or in the source server. so we ask user to send a telnet request from source server to destination on particular port by this syntax, telnet <dest ip> <dest Port>. >, (Note: Telnet must be enabled on the user system, to enable: programs and features > turn Windows features on or off > Telnet Client option. >check the box) if they getting connection refused or denied or not able to connect, it could mean they connection is coming through yet not reaching to destination, another way is ask user for the trace, tracert <dest ip>, check if there’s a firewall in path or not.
Another way is, go to the firewall nd put a packet capture and see traffic hitting the firewall or not.
4. sometime we could see traffic is allowed on splunk logs but user still not able to connect, though user still get telnet refuse. such case we consider the local windows firewall is blocking either in source side or in dest side (ref GEINCTASK17200882)
5. but we don’t have any proof to say issue on user side, in that case we go for packet capture with wireshark either dest or source server accordingly (ref GEINC11269981, packet capture of destination)
![image](https://github.com/sajithten/Networking-Troubleshooting/assets/110303586/64f20d9d-5ed2-411c-a33c-f8655e0aeef1)
GEINC11269981 this captured on destination server, basically we look for any Reset Events, could see RST events from the destination that was going out, here traffic is reaching to destination(i.e ge firewall is allowing traffic) & traffic is resetting from destination end, so need to be checked in the destination firewall (for windows system: windows firewall, for Linux system: IP table)

6. for Palo Alto logs not visible on splunk, we need to login to panorama >Monitor > traffic > under search give > (addr in <ip>) (addr in <ip>)
![image](https://github.com/sajithten/Networking-Troubleshooting/assets/110303586/e9a68027-8c15-4968-bb1d-118a9cda2804)

7. sometimes traffic goes through multiple firewalls, we ask user to raise FRA, still traffic will be blocked in the next firewall, again we ask user to raise FRA
    
8. In the case of Public URL, it won’t pass through firewall, public url like all the internet access, it will go through PITC proxy i.e, plug proxy setup, we need to nslookup the url, if not resolving then move case to Proxy team
    
9. when a case where url not be resolved, and url not going through the proxy as well, one possibility could be url will exit from the cloud internet gateway itself directly, it wont pass through firewall.other possibility is, do nslookup url, it will resolve, and go cmd of our laptop and check routing table netstat -nr , we’ll see IP of url in our laptop routing table

![image](https://github.com/sajithten/Networking-Troubleshooting/assets/110303586/8feee03d-7d7f-46ed-ad3c-027017caacb2)

netstat -nr , routing table of her computer, 1st entry default route points to GE bcs computer is on F5 vpn, 2nd entry is the backup default route which point to internet, other entries 13.xxx 52.xxx 52.120.xx points towards house router 192.168.0.1 so that is MSteams local breakout that is how her MSteams traffic from her laptop is going straight to the internet and not coming through the VPN
other possibility is , there is PAC file [corp.setpac.ge.com/pac.pac?debug=YES&ip=10.172.121.66](http://corp.setpac.ge.com/pac.pac?debug=YES&ip=10.172.121.66) , change ip to the user’s ip to get user’s PAC file. there we get the definition for it, we could find here it as well

other possibility will be something with DMZ server

10. some servers are based behind Vault firewall, aviation vault basically, lot of restrictions for traffic, when we get splunk logs with vault firewall, we route the case to vault team
11. If we not get any logs, then sometimes there would be route missing when user trying to initiate traffic and that not reaching to firewall, get netstat -nr from user machine and seen if route is present or not.
12. in 3PR Firewalls Natting happens especially 205.1.173.x range is very common for 3PR
13. In Palo Alto we capture packet by packet capture command to see traffic is passing
In PA GUI: Monitor > Packet capture > Add > firewall or transmit stage > fill > on Packet capture. Most of time all packet is visible on Logs Traffic tab & Threat Tab as well
14. when we see “windows security Events” in splunk logs, that means traffic is blocked from local windows defender firewall of user system, so we inform user issue with their side

