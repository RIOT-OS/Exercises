# Setup an IoT enabled Linux host

- difficulty: low
- complexity: low

## Description

The objective of this exercise is to setup an IoT enabled Linux host using
standard, open IoT technologies and protocols. Wireless communication will
be based on IEEE 802.15.4 and 6LoWPAN/IPv6.

## Instructions

1. Setup a Raspberry Pi with the latest Raspbian Linux release [1].
2. Build and install the Linux WPAN tools [2], [3].
3. Install network sniffer command line tools, i.e., `tshark`.
4. Configure a WPAN monitor interface with default channel (see below).
5. Setup and start a RIOT node that can answer ICMPv6 ping requests
6. Run a network sniffer to detect the link local IPv6 address of the RIOT node.
7. Configure a LoWPAN network interface with default parameters (see below).
8. Send several pings to the RIOT node on its link local IPv6 address.

Document _all_ your actions and findings.

## References

- recommended hardware:
    - Raspberry Pi B+, 2B, or 3B
    - OpenLabs IEEE 802.15.4 transceiver module [4]
    - RIOT board, e.g. SAM R21 Xplained Pro [5], Zolertia Remote [6]
- for all tests use default channel `26` and PAN ID `0x23`
- the RIOT node should be flashed with `example/gnrc_networking`

[1]: https://www.raspberrypi.org/downloads/
[2]: http://wpan.cakelab.org/
[3]: https://github.com/linux-wpan/wpan-tools
[4]: http://openlabs.co/store/Raspberry-Pi-802.15.4-radio
[5]: http://www.atmel.com/tools/atsamr21-xpro.aspx
[6]: http://zolertia.io/product/hardware/re-mote
