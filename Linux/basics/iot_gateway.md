# Setup an IoT gateway based on Linux

- difficulty: low
- complexity: mid

## Description

The objective of this exercise is to setup a simple IoT Linux gateway, that
will interconnect sensor nodes, e.g. running RIOT-OS, with other (wired) local
networks or even up to the global Internet. This requires to announce a routable
IPv6 prefix and forward data between different network domains, i.e., from
wireless IEEE 802.15.4 to wired ethernet.

## Instructions

1. Setup an IoT enabled Linux host with LoWPAN interface, see previous task [1].
2. Build and install RADVD, use the linux-wpan fork and branch `6lowpan` [2].
3. Configure RADVD to announce a ULA prefix on the LoWPAN interface [3].
4. Setup and start a RIOT node that can answer ICMPv6 ping requests.
5. Send several pings to the RIOT node on its ULA IPv6 address.

Document _all_ your actions and findings.

## References

- recommended hardware:
    - Raspberry Pi B+, 2B, or 3B
    - OpenLabs IEEE 802.15.4 transceiver module [4]
    - RIOT board, e.g. SAM R21 Xplained Pro [5], Zolertia Remote [6]
- for all tests use default channel `26` and PAN ID `0x23`
- the RIOT node should be flashed with `example/gnrc_networking`

[1]: https://github.com/RIOT-OS/Exercises/blob/master/Linux/basics/iot_node.md
[2]: https://github.com/linux-wpan/radvd
[3]: http://unique-local-ipv6.com/
[4]: http://openlabs.co/store/Raspberry-Pi-802.15.4-radio
[5]: http://www.atmel.com/tools/atsamr21-xpro.aspx
[6]: http://zolertia.io/product/hardware/re-mote
