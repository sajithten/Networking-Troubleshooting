Duplex mismatch occurs when the two communicating Ethernet devices end up with duplex settings that are not the same, either because of manual settings or the autonegotiation process.

To prevent a duplex mismatch, you have two options:
- Set all devices to autonegotiation.
- Hard-code all device-speed and duplex settings on both the switch and the device.

```
Switch#config terminal
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#int fa0/2 
Switch(config-if)#
Switch(config-if)#spee
Switch(config-if)#speed ?
  10    Force 10 Mbps operation
  100   Force 100 Mbps operation
  auto  Enable AUTO speed configuration

Switch(config-if)#speed auto
```
