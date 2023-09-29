# Ethernet and Switching

- - - -

## Table of Contents

* [Overview](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/EthernetAndSwitching.md#overview)
* [Network details](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/EthernetAndSwitching.md#network-details)
* [Ethernet Structure](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/EthernetAndSwitching.md#ethernet-structure)
* [IP Routing](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/EthernetAndSwitching.md#ip-routing)

## Overview

* Layer 2 - Data link layer
  * Moving data between individual devices
* Switches used to connect devices on a network together

## Network details

* CSMA/CD : Carrier Sense Multiple Access with Collision Detection
  * Multiple devices using the same network
  * Detection for data collisions
  * Wait a random amount of time then resend the data
* Half duplex : Devices can communicate both ways over a network
  * But not at the same time
  * E.g. walkie talkie
* Full Duplex : Devices can communicate both ways of a network at the same time
* Simple : Devices can only communicate one way over a network

## Ethernet Structure

Ethernet places data in frames. Each frame has:

* Destination MAC address (48 bits)
* Source MAC Address (48 bits)
* Type (of data) (16 bits)
* FCS (32 bits) (Frame Check Sequence : does a cyclical redundancy check to make sure the data has not been corrupted)
* Data (packet) (1500 bytes)

## IP Routing

* Network layer (end to end communication between devices)
* Contains TTL value : Time to live, how many "hops" a packet can make before giving up to prevent flooding the network
* Uses ARP : Address resolution protocol, for finding the destination MAC address for an IP packet (by using the IP address)
  * Devices keep an ARP table cache, entries age out
* The Default Gateway
  * Just a default router
  * PC sends data to this router when it doesn't know where to send it (usually on a LAN)
