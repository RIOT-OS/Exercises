# Setup an IoT gateway based on Linux

- difficulty: low
- complexity: mid

## Description

The objective of this exercise is to setup an IoT Linux gateway that also acts
as a RPL root node. RPL is a routing protocol designed for constraint nodes and
networks, it allows to interconnect sensor networks with other (wired) local
networks or even up to the global Internet. RPL will take of announcing a
routable IPv6 prefix and forward data between different network domains, i.e.,
from wireless IEEE 802.15.4 to wired ethernet.

## Instructions

1. Setup an IoT enabled Linux host with LoWPAN interface, see previous task [1].
2. Build and install unstrung, use the fork in [2] and branch `pr/fix_update_child_route`.
3. Start unstrung, i.e., `sunshine`, as RPL root node on your IoT Linux gateway again with a ULA prefix [3].
4. Setup and start a RIOT node that has RPL activated, see hints below
5. Send several pings to the RIOT node on its ULA IPv6 address.

Document _all_ your actions and findings.

## References

- recommended hardware:
    - Raspberry Pi B+, 2B, or 3B
    - OpenLabs IEEE 802.15.4 transceiver module [4]
    - RIOT board, e.g. SAM R21 Xplained Pro [5], Zolertia Remote [6]
- for all tests use default channel `26` and PAN ID `0x23`
- the RIOT node should be flashed with `example/gnrc_networking`
- for interop of RPL between Linux and RIOT-OS, uncomment in Makefile:
    `CFLAGS += -DGNRC_RPL_DODAG_CONF_OPTIONAL_ON_JOIN`

[1]: https://github.com/smartuni/exercises/Linux/01_iot_node.md
[2]: https://github.com/smlng/unstrung/tree/pr/fix_update_child_route
[3]: http://unique-local-ipv6.com/
[4]: http://openlabs.co/store/Raspberry-Pi-802.15.4-radio
[5]: http://www.atmel.com/tools/atsamr21-xpro.aspx
[6]: http://zolertia.io/product/hardware/re-mote
