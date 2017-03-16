# Simple CoAP Server

- difficulty: low
- complexity: mid

## Description

The objective of this exercise is to implement a CoAP server in RIOT that uses
JSON as content formats. It extends on the previous task.

## Instructions

1. Extend the simple CoAP server, implemented as described in [1].
2. Change the content format of all resources to JSON, use the jsmn package [2].
3. Create a 3rd resource `print/` that handles CoAP PUT messages and outputs the
   packet content. Packet content format should be JSON: `{ 'msg': '<text>'}`,
   `<text>` should be printed.
4. Test the tool again using RIOT native and libcoap client.

Document _all_ your actions and findings. Create an archive with your solution.

## References

[1]: https://github.com/smartuni/exercises/RIOT/coap/01_coap_server.md
[2]: https://github.com/zserge/jsmn
