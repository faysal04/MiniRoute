# MiniRoute

This repository contains the mock Router/Switch named as MiniRoute.

## Release Notes 
Release Version: 0.1

This release implements basic data path. It makes the following assumptions.

1- port_0 has the default address of 0xAA

2- port_1 has the default address of 0xAB

3- port_2 has the default address of 0xAC

4- port_3 has the default address of 0xAD

5- This release only implements one-to-one packets, If the pakcet type is some other value, the behavior will be unknown.

6- The router checks for checksum. If the checksum is correct, the packet will be routed to destination.

7- If the checksum is incorrect, the behaviour will be unknown.

8- If multiple ports sends a packet target to the same destination, the packet is routed in accordance with ports priority, the priority order from highest to lowest is port_0, port_1, port_2, port_3 


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