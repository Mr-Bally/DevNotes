# IP Addresses

- - - -

## Table of Contents

* [Overview](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/IpAddresses.md#overview)
* [IP Address](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/IpAddresses.md#ip-address)
* [Classful and Classless Addressing](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/IpAddresses.md#classful-and-classless-addressing)
* [IP address types](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/IpAddresses.md#ip-address-types)
* [CIDR Notation](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/IpAddresses.md#cidr-notation)
* [Private IP addresses](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/IpAddresses.md#private-ip-addresses)

## Overview

* Internet Protocol (IP) belongs on layer 3 (Network layer) of the OSI model
* Responsbile for moving data from one device on the internet to the other
* Each device on the public interent needs a unique address

### IP address

* Made up of 4 numbers between 0 and 255 e.g. 255.0.113.0
* In total there are 32 bits broken into 4 8 bit numbers (Octets)
* First 3 numbers are the network portion, last number is the host portion
* Network portion is like the postcode whereas the  portion is like the house number
  * IE the network portion is the area of the network the device is on, the host portion is the specific device on that part of the network

## Classful and Classless Addressing

* Classful Addressing (used prior to 1995)
  * Used IP ranges to determine the class of IP address
  * Class A B C are Unicast (peer to peer)
  * Class D are Multicast (not supported on the public internet) casting to multiple devices
  * Each class the network portion of the address increases (e.g. Class A 1 octet is the network portion, Class B is 2 octats etc)

* Classless Addressing (used post 1995)
  * This determines what portion of the address is the network and which portion is the host
  * Subnet Mask reveals what portion this is e.g.
  * 255.255.255.0 -> First 3 octets are the network portion
* For classless addressing this subnet mask can occur anywhere
  * e.g. 255.0.0.0 or 255.255.240.0 if the mask is exactly half the address

## IP address types

* Network address : ID for a group of devices
  * "Network prefix"
  * E.g. Postcode for an area of devices
  * Has all binary 0s in the HOST portion of the address

* Broadcast address : ID for all devices on a network
  * Can send messages to all devices on a network
  * All Binary 1s in the host portion of the address

* Host Address : ID a unique device on the network
  * Has a mix of 0s and 1s (never all 0 or all 1)

## CIDR Notation

* Classless Interdomain Routing
* Used to simplify subnet mask and IP address
* Use a / to notate the bits in the network portion

> e.g. IP address :  203.0.113.10 1001011 00000000 01110001 00001010
> Subnet Mask : 255.255.255.0 11111111 11111111 11111111 00000000
> Network prefix is 24 bit so use /24 to notate the length of the network prefix
> Finally 203.0.113.10/24

## Private IP addresses

* There are 3 sets of private IP address ranges defined
* Which are not routable on the public internet
* Can use this IP ranges for local or private networks
* Also have the APIPA (Automatic Private IP Addressing) : 169.254.0.0/16 (AVOID using this)
* 127.0.0.1 : Loopback address to your local machine
