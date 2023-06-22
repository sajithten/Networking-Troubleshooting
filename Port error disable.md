## Error disable port state
Err-disabled Port State, Enable & Disable Autorecovery Feature 
 
Errdisable is a feature that automatically disables a port on a Cisco Catalyst switch. When a port is error disabled, it is effectively shut down and no traffic is sent or received on that port.

The error disabled  feature is supported on most Catalyst switches running the Cisco IOS software. Including all the following models:

Catalyst 2940 / 2950 / 2960 / 2960S
Catalyst 3550 / 3560 / 3560-E / 3750 / 3750-E
Catalyst 4000 / 4500 / 4507R
Catalyst 6000 / 6500
  The Errdisable error disable feature was designed to inform the administrator when there is a port problem or error.  The reasons a catalyst switch can go into Errdisable mode and shutdown a port are many and include:

Duplex Mismatch

Loopback Error

Link Flapping (up/down)
Port Security Violation
Unicast Flodding
UDLD Failure
Broadcast Storms
BPDU Guard

When a port is in error-disabled state, it is effectively shut down and no traffic is sent or received on that port. The port LED is set to the orange color and, when you issue the show interfaces command, the port status shows as Errdisabled.

Following is an example of what an error-disabled port looks like:
```
2960G# show interface gigabit0/7

 

GigabitEthernet0/7 is down, line protocol is down (err-disabled)
 

  Hardware is Gigabit Ethernet, address is 001b.54aa.c107 (bia 001b.54aa.c107)
 

  MTU 1500 bytes, BW 100000 Kbit, DLY 100 usec,
 

     reliability 234/255, txload 1/255, rxload 1/255
 

  Encapsulation ARPA, loopback not set
 

  Keepalive set (10 sec)
 

  Auto-duplex, Auto-speed, media type is 10/100/1000BaseTX
 

  input flow-control is off, output flow-control is unsupported
 

  ARP type: ARPA, ARP Timeout 04:00:00
 

  Last input 18w5d, output 18w5d, output hang never
 

  Last clearing of "show interface" counters never
 

  Input queue: 0/75/0/0 (size/max/drops/flushes); Total output drops: 0
 

  Queueing strategy: fifo
 

  Output queue: 0/40 (size/max)
 

  5 minute input rate 0 bits/sec, 0 packets/sec
 

  5 minute output rate 0 bits/sec, 0 packets/sec
 

     1011 packets input, 862666 bytes, 0 no buffer
 

     Received 157 broadcasts (0 multicast)
 

     0 runts, 0 giants, 0 throttles
 

     3021 input errors, 2 CRC, 0 frame, 0 overrun, 0 ignored
 

     0 watchdog, 144 multicast, 0 pause input
 

     0 input packets with dribble condition detected
 

     402154 packets output, 86290866 bytes, 0 underruns
 

     0 output errors, 0 collisions, 1 interface resets
 

     0 babbles, 0 late collision, 0 deferred
 

     0 lost carrier, 0 no carrier, 0 PAUSE output
 

     0 output buffer failures, 0 output buffers swapped out
     
```
To recover a port that is in an Errdisable state, manual intervention is required, and the administrator must access the switch and configure the specific port with 'shutdown' followed by the 'no shutdown' command. This command sequence will enable the port again, however, if the problem persists expect to find the port in Errdisable state again soon.

---
```
show interface status err-disabled

```
