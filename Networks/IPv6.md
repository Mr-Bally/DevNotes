# IPv6

- - - -

## Table of Contents

* [Overview](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/IPv6.md#overview)
* [Address Acquisition](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/IPv6.md#address-acquisition)

## Overview

* IPv4 is 32 bits long (4 octets)
* IPv6 is 128 bits long (8 hexidecimal values or hextets)
  * Tend to remove any leading 0s in each hextet to reduce the size
  * Expontentially more addresses available than IPv4
* Interface ID has 2 to 64 power (on a single network /network portion)
* Network portion  2 to 64 power
* Generally not written in binary due to size of the address
* Split between 64 bits for the network portion and 64 bits for the interface indentifier

## Address Acquisition

* SLAAC : Stateless Address Autoconfiguration
* Find out what network they are on
* Then generate the interface indentifier (64 bits) either randomly (windows) or use MAC address (Unix/ Mac)

> MAC Address : composed of manufactor ID and serial number on the network card
