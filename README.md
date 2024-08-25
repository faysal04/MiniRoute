# MiniRoute

This repository contains the mock Router/Switch named as MiniRoute.

## Release Notes 
Release Notes - MVP

Default Addresses:
  Default addresses have been configured as follows:

  port_0 = 0xFA
  port_1 = 0xFB
  port_2 = 0xFC
  port_3 = 0xFD

Control Registers:
    Control registers now default to a value of 0xFF.

Packet Validation:
    Packet validation now occurs before any further processing. This includes verifying the source address, destination address, and checksum. If any of these checks fail, an error will be returned, and normal operations will only proceed if the packet passes all validation steps.

Broadcast and Device Connected Registers:
    The "Broadcast Enabled" and "Device Connected" registers apply only to the output port. The DUT will always read input packets, regardless of the status of these registers.

Invalid Packet Handling:
    Packets with invalid packet types will be ignored.

Operation After Reset:
    MiniRoute can operate normally after a reset using default values, with configuration possible at any time.

Note: This is the MVP release. A patch release will be added later this week.
