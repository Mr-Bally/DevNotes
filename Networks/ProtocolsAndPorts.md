# Protocols and Ports

- - - -

## Table of Contents

* [Overview](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/ProtocolsAndPorts.md#overview)
* [Data transfer protocols](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/ProtocolsAndPorts.md#data-transfer-protocols)
* [DNS](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/ProtocolsAndPorts.md#dns)
* [NTP](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/ProtocolsAndPorts.md#ntp)
* [Transmission control protocol](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/ProtocolsAndPorts.md#transmission-control-protocol)
* [Transport layer addressing](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/ProtocolsAndPorts.md#transmission-layer-addressing)

## Overview

* Protocols are part of the Application Layer (7) of the OSI model
* But protocols all have a layer 4 component (Transport layer) which is implemented via ports
* e.g. HTTP uses port 80, HTTPS 443

## Data transfer protocols

* HTTP : Hypertext transfer protocol
* HTTPS : HTTP Secure
* FTP : File Transmission protocol
* sFTP : Secure
* TFTP : Trivial File Transport Protocol (for very small file transfers)
* SMB : Server message block

### Email

* SMTP : Simple Mail Transfer Protocol
* POP3 / IMAP : Used by client to pull emails from a server

### Authentication

* LDAP : Lightweight Directory Access Protocol, used in Windows 10
* LDAPs : Encrypted version of the above

### Network Management

* SSH : Secure Shell
* Telnet : Unencrypted
  * Both used by network admin to communicate with other devices on the network
* SNMP : Simple Network Management protocol, sends out request to all devices and requests info like what ports are open, logs etc
* RDP : Remove desktop protocol : allows you to remotely control a device

## DNS

* Stands for Domain Name System Protocol
* Converts URLs to IP addresses
* Allows us to lookup addresses and communicate over the internet
* All devices on the internet must have a public IP address to be able to communicate

## NTP

* Network Time protocol
* NTP server can reply to client requests as to the exact time
* Replies are done in UTC to avoid timezone issues

## Transmission Control Protocol

### TCP

* One of the most important protocols for the modern internet
* Protocol for a 3 way handshake
  * Client sends a SYN (synchronise message) to the server
  * Server responds with a SYN-ACK
  * Client responds ACK
  * Now a session has been established and a connection between the client and the server exists
  * Once this has been established we can use another protocol like HTTP to send and request data
  * Means we can request that data be resent if the we as the client does not receive it and respond saying we have received the data when we do

* Also uses a 4 way disconnect
  * 1st device sends FIN message
  * 2nd device sends a FIN-ACK
  * 1st device sends anther FIN message
  * 2nd device sends another FIN-ACK message and the session is ended
* Alternatively a devices sends a TCP RST (reset) message (immediately severes the connection)

### UDP

* User Datagram Protocol, another transport layer protocol
* UDP wraps up some application level data
* Then sends it onto the network to an address
* No handshake or session is established
* Hence there is no reliable communication (message may or may not be received)
* Used for small efficient data transfer

## Transport layer addressing

* Use port numbers to ID the application level protocol which is being used
* Server port numbers : Categorised into well known and registered port numbers
* Well known ports 0 - 1023 (e.g. HTTP port 80, SSH port 22)
* Layer 7 application protocols are reliant on having a port and transport protocol
* All transport network protocols rely on IP
* Registered ports 1024 - 49,151
* Client Port Numbers : Ephemeral (short lived) port numbers
* Ports 49,152 - 65,535 are not assigned, controlled, or registered
