# Network Services

- - - -

## Table of Contents

* [Overview](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/NetworkServices.md#definitions)

## Definitions

* LAN : Local Area Network (Describes a small network area)
* WLAN : Wireless Local Area Network (A more specific type of LAN)
* WAN : Wide Area Network (For connecting networks together that aren't physically close
* SAN : Storage Area Network (Area of the network dedicated for storage capabilities)
* PAN : Personal Area Network (For example Bluetooth)

* Socket : An IP address with a tranport layer port number e.g. 203.0.13.6:9293
  * Allows you to forward on ports
* Traffic shaping : Giving priortiy to certain traffic on a network
* TLD : Top level domain (e.g. .ca, .com .gov)
* Second level domain name : Centre part of a URL e.g. google in www.google.com
  * Can have multiple levels of domain name : e.g. www.engineering.university.edu has 3 levels of domain name

* DNS Record types
  * A - IPv4 Record
  * AAAA - IPv6 Record
  * CNAME - Canonical Name Record (e.g. everytime you see a certain address return anthother one, basically an alias)
  * MX - Mail Exchange Record
  * NS - Identifies Authoritative Name Server
  * PTR - Pointer Record (similar to CNAME but does not automatically do the lookup for the client for the IP)
  * SRV - Service Record (points to layer 6 or 7 service)
  * TXT - Text record for misc use
  