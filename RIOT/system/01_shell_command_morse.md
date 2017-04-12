# String to Morse parser

- difficulty: mid
- complexity: low

## Description

The objective of this exercise is to implement a RIOT shell command handler
which parses input strings to Morse signals expressed via LED.

## Instructions

1. Get familiar with the shell using [1] and the timer module xtimer [2].
2. Program a shell command handler that parses strings to Morse code [3]. Note
that you don't necessarily need a board for development. You can also
develop under native [4] as there is an LED abstraction.
3. Generate a new module with your code under *RIOT/drivers* which can be included
via Makefile.

Document _all_ your actions and findings. Create an archive with your solution.

## References

[1]: https://github.com/RIOT-OS/RIOT/tree/master/tests/shell
[2]: https://riot-os.org/api/group__sys__xtimer.html
[3]: https://en.wikipedia.org/wiki/Morse_code
[4]: https://github.com/RIOT-OS/RIOT/wiki/Family%3A-native