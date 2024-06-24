# Number literals

Here’s all the different ways to write a number in Nougaro:

* `123`
* `12.3`
* `123e2`
* `12.3e2`
* `123e-2`
* `123e+2`
* `12.3e-2`
* `12.3e+2`

!!! note
    You can put `+` or `-` in front of the number to specify its sign. Example: `-123`.

Other bases:

* `0b01110` (base 2, binary)
* `0o17403` (base 8, octal)
* `0x4EF1A` (base 16, hexadecimal)
* `0b10e30`
* `0o70e30`

!!! note
    `0xA0e30` will be interpreted as the hexadecimal number `A0E30` (`3*16^1 + 15*16^2 + 10*16^4`) and not as `0xA0 * 10^30`
