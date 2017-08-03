# Networking and UDP network statistics module

- difficulty: high
- complexity: high

## Description

The objective of this exercise is to get familiar with networking in RIOT and
to write a module that collects minimal statistics on the transport layer.

## Instructions

1. Get familiar with networking by using RIOTs default networking
   example `gnrc_networking` \[1\] and exchange UDP packets between two instances
   (either boards or RIOT native \[2\]) following these steps:
* Go to the `gnrc_networking` application \[3\] and have a look in `udp.c` how
  packets are constructed, send and received
* Compile, flash, and run on your board `BOARD=samr21-xpro make all flash term`
   or native `make clean all term PORT=tap0` resp. `tap1`
* Type `help`
* Start UDP server on port 8888 using `udp server 8888`
* Get your IPv6 address using `ifconfig`
* Send your neighbor some messages using `udp send`
* Read the Doc \[4\]

2. Now that you've used the whole UDP/IPv6 network stack, have a look inside the
   implementation of UDP \[5\]. The goal is to write a software component which collects and prints
   simple statistics about the amount of UDP packets and data that has been sent and received.

3. There is an existing `netstats` module in RIOT which is used in `gnrc_networking` by default
   and should be extended. Have a look the the header \[6\] and implementation for e.g. IPv6 \[7\]
   and see how statistics are collected and when they are printed to the console \[8\]. Note that
   this tasks requires a certain amount of personal contribution.

Document _all_ your actions and findings. Create an archive with your solution.

## References

\[1\] [https://github.com/RIOT-OS/RIOT/tree/master/examples/gnrc_networking](https://github.com/RIOT-OS/RIOT/tree/master/examples/gnrc_networking)

\[2\] [https://github.com/RIOT-OS/RIOT/wiki/Family%3A-native](https://github.com/RIOT-OS/RIOT/wiki/Family%3A-native)

\[3\] [https://github.com/RIOT-OS/RIOT/tree/master/examples/gnrc_networking](https://github.com/RIOT-OS/RIOT/tree/master/examples/gnrc_networking)

\[4\] [http://doc.riot-os.org/group__net__gnrc.html](http://doc.riot-os.org/group__net__gnrc.html)

\[5\] [https://github.com/RIOT-OS/RIOT/blob/master/sys/net/gnrc/transport_layer/udp/gnrc_udp.c](https://github.com/RIOT-OS/RIOT/blob/master/sys/net/gnrc/transport_layer/udp/gnrc_udp.c)

\[6\] [https://github.com/RIOT-OS/RIOT/blob/master/sys/include/net/netstats.h](https://github.com/RIOT-OS/RIOT/blob/master/sys/include/net/netstats.h)

\[7\] [https://github.com/RIOT-OS/RIOT/blob/master/sys/net/gnrc/network_layer/ipv6/gnrc_ipv6.c](https://github.com/RIOT-OS/RIOT/blob/master/sys/net/gnrc/network_layer/ipv6/gnrc_ipv6.c)

\[8\] [https://github.com/RIOT-OS/RIOT/blob/master/sys/shell/commands/sc_netif.c](https://github.com/RIOT-OS/RIOT/blob/master/sys/shell/commands/sc_netif.c)
