<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

This decoder converts a 4-bit Binary Coded Decimal (BCD) input into signals that drive a standard 7-segment display. The inputs are labeled **input a** (LSB) through **input d** (MSB). The outputs correspond to the individual segments **output a** through **output g**.

The system uses Boolean logic gates derived from Karnaugh Map (K-map) simplification. Each output is active (1) when the corresponding segment needs to be lit to form a decimal digit (0-9).
## How to test

To verify the implementation, set the inputs to the binary values below and ensure the outputs match the truth table. Each "1" in the output columns indicates that the specific segment should be ON.

| Digit | input d | input c | input b | input a | out a | out b | out c | out d | out e | out f | out g |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 0 |
| 1 | 0 | 0 | 0 | 1 | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
| 2 | 0 | 0 | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 0 | 1 |
| 3 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 0 | 0 | 1 |
| 4 | 0 | 1 | 0 | 0 | 0 | 1 | 1 | 0 | 0 | 1 | 1 |
| 5 | 0 | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 0 | 1 | 1 |
| 6 | 0 | 1 | 1 | 0 | 1 | 0 | 1 | 1 | 1 | 1 | 1 |
| 7 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 0 | 0 | 0 | 0 |
| 8 | 1 | 0 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 9 | 1 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 0 | 1 | 1 |

**Clock Frequency:** Set the clock to **10kHz**. At this frequency, you should observe stable, flicker-free transitions between digits as the inputs change.

**Invalid Inputs:** For input combinations 1010 through 1111 (binary 10-15), the outputs are designed to be all **0** (display off), as these are outside the valid BCD range.
## External hardware
7-segment display
