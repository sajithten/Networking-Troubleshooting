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
