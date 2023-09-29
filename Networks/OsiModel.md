# OSI Model

- - - -

## Table of Contents

* [Overview](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/OsiModel.md#overview)
* [Physical Layer](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/OsiModel.md#physical-layer)
* [Datalink Layer](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/OsiModel.md#datalink-layer)
* [Network Layer](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/OsiModel.md#network-layer)
* [Transport Layer](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/OsiModel.md#transport-layer)
* [Session and Presentation Layer](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/OsiModel.md#session-and-presentation-layer)
* [Application Layer](https://github.com/Mr-Bally/DevNotes/blob/main/Networks/OsiModel.md#application-layer)

## Overview

* OSI Model is concerned with data networking. I.E. Moving data from one device to another.
* Stands for: Open Systems Interconnect Model
* Developed in the early 1970s
* Some parts are outdated and more theoretical than practical
* Starts at layer 1 (Physical) and moves up to application layer (7)

## Physical Layer

* The physical infrastructure e.g.
  * Cables
  * Wiring
  * Wireless connections
  * Twisted pairs
  * Fibre optic
  * CoAx cable
  * Routers / switches

## Datalink Layer

* Composed of the network protocols
* Can be different for the different stages of networking
  * e.g. computer to router, router to ISP etc
* Mainly ethernet used for the internet communication (due to high speed)
* Datalink is limited to communication between devices (e.g. terminal to modem)

## Network Layer

* Uses IP Addresses
  * Provides a unique address for all devices on the internet
  * Allows us to route data to a specific location
  * Allows communication from end to end rather than just between two devices like datalink

## Transport Layer

* Concerted with setting up a connection between two endpoints
  * e.g. for a phone call you would need to dial a number, make a connection and somebody would need to pick up the phone
  * Implements this using the Transmission Control Protocol (TCP)

## Session and Presentation Layer

* The 5th and 6th layers are more theoretical than something which is practically used
* Presentation layer:
  * Concerns itself with things like the character encoding (e.g. ASCII converting characters to integers)
  * Was an issue when different compainies would use different encodings (e.g. IBM using EMCDIC)
  * Presentation would sort networking between the character encodings and 'translate' them
  * Less of an issue now given internet standardisation or occurs in the application layer
* Session Layer :
  * ICA protocol can be used
  * But tends to be done at the application layer

## Application Layer

* Implements protocols for pulling data from a server
* Most common protocol HTTP/ HTTPS
* Tells the server what data we want to pull and how the browser will utilise it
