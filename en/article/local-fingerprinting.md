# Local device fingerprinting in proximity

## Introduction

Assume that the fingerprinting actor is in the neighboring room or apartment and has good directional antennae and redundant sniffer receivers.

All remote options are also applicable:

* [remote-fingerprinting.md](remote-fingerprinting.md)

## Side channel attacks

Unique emanations or even information leakage can also occur on channels other than what was meant for communication.

https://en.wikipedia.org/wiki/Side-channel_attack

* collecting fingerprints from door knobs, doorbells, a glass, pens or other objects
* collecting DNA from plastic cups, candy wrappers, chairs and coat hangers
* hidden cameras: facial recognition, object recognition
* microphones hidden or bounced via a laser from a distance: typing biometrics, conversation, ultrasonic emanation
* high speed photodetectors: flickering of display or LEDs
* power consumption
* electromagnetic radio emissions
* EMI conducted over a single common wire (ground)

## General options

* time of day of connection and active use
* MAC OUI
* MAC address, randomization algorithm
* classify kind of flows based on distribution of frame size and inter-frame timing over time and direction
* if the signature of certain higher level events can be detected on either L2/L3, track their precise timing to recover and analyze their clock source (TSC or RTC): DHCP renew, connectivity rechecking, RSS polling, keepalive, heartbeat, JavaScript refreshing news, error timeouts

## LAN options

* sometimes further passive analysis or even interaction is possible with the target
* if the AP or gateway itself is rogue
* ARP poisoning to gain MITM
* captive portal connectivity checks
* burst timing or repetition: DHCP, NTP
* DHCP hostname, options, requested address
* DNS: visited sites, options, behavior
* IPs, ASNs, geoIP of visited sites or utilized VPN, DoH, NTP, software updates
* mDNS
* ARP probe repetition, targets, fields
* IPv6 neighborhood discovery
* SSDP
* SMB
* HTTP URLs
* TLS SNI
* some of the HTTPS websites and URLs may be identified by packet size distribution

## Wireless options

* analyze analog waveform of a well known frame using an SDR
* determine nanosecond precision timing of different sections
* unmodulated carrier, preamble, data
* time to stabilize and warm up carrier, shape during warmup
* sidelobes, roll-off
* reconstruct values of band-pass filters
* noise level
* bit length, shape, ramp up, overshoot
* exact calibrated frequency
* jitter, skew, temperature dependence of oscillator (partially controlled, but transitions may still be visible)
* relative bit/symbol signal levels
* relative overall power levels
* profile you within just a few microseconds using very cheap accessories, probably within a few hundred dollars using an SDR.

## WLAN options

Some of these depend on the OS/driver, others depend on the firmware/MCU of the NIC.

* measure the jitter, skew and temperature dependence of the MAC TSF clock
* if some of the events are controlled from an oscillator different than the TSF (e.g., probing by the OS RTC or TSC), measure its properties as well
* advertised wireless station capability IEs and their order: probe, association
* probe request timing, names, hop pattern
* power saving sleep behavior
* retransmission delay, max count, histogram
* data frames: non-advertised capabilities of station
* generating and handling non-mandatory bits within frames (e.g., duration field in ACK)
* device kind by estimating relative clock cycle counts by nanosecond precision timing of the state machine transitions: initial association, reconnection, RTS/CTS, GTK rekey
* opens up LAN options if the network has a PSK or is susceptible to GTK based injection

## Cellular broadband options

Measure via an SDR:

* used frequency bands
* channel bandwidth
* channel bonding

Infer:

* ISP
* subscription
* connection technology
* modem kind
