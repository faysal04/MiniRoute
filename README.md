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
