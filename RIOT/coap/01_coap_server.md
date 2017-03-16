# Simple CoAP Server

- difficulty: low
- complexity: low

## Description

The objective of this exercise is to implement a simple CoAP server in RIOT.
CoAP [1] is a HTTP like protocol for constraint network and nodes that allows
to implement RESTful services [2].

## Instructions

1. Implement a CoAP server with 2 resources for RIOT using _gcoap_
2. Both resources should be retrievable via GET using plain text format:
    - `info/board` returns the RIOT board name
    - `info/mcu` returns the RIOT MCU name
3. The tool should print all unicast IPv6 addresses during start.
4. Compile and start the tool using RIOT native and a tap interface
5. Use the libcoap client [3] to discover the resources via `.well-known/core`
   and retrieve available resources; use one of the IPs output, see above.

Document _all_ your actions and findings. Create an archive with your solution.

## References

[1]: http://coap.technology/
[2]: https://en.wikipedia.org/wiki/Representational_state_transfer
[3]: https://libcoap.net/
