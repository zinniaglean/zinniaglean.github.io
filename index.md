# Nio (Beta)

Nio is a reboot of the Turing Complete stack-based esoteric programming language "nori.io" by "notherone".

The interpreter reads the program left-to-right, character per character, and always moves right.

## Commands

The interpreter ignores every other character than these, making them no-op.

### Main commands

| Command     | Description                                                   |
| ----------- | ------------------------------------------------------------- |
| `>`         | Push the value next to it                                     |
| `<`         | Pop the last value                                            |
| `N`         | Push the numeric user input                                   |
| `I`         | Push the user input                                           |
| `,`         | Push the user input as an ASCII value                         |
| `O`         | Output the last value to the console then pop it              |
| `o`         | Output the last value to the console then pop it w/newline    |
| `X`         | Clear the output                                              |
| `.`         | Output the last ASCII value to the console then pop it        |
| `@`         | Swap the last two values                                      |
| `$`         | Reverse the whole stack                                       |
| `:`         | Duplicate the top value                                       |
| `+`         | Add last two values together                                  |
| `-`         | Subtract last two values together                             |
| `*`         | Multiply last two values together                             |
| `/`         | Divide last two values together                               |
| `^`         | Raise last two values together                                |
| `z`         | Square root the last value                                    |
| `%`         | Modulo last two values together                               |
| `c`         | Ceil the last number                                          |
| `f`         | Floor the last number                                         |
| `r`         | Push a random number                                          |
| `b`         | Push a random bit (either 0 or 1)                             |
| `B`         | Push a random byte                                            |
| `[`         | Jump past the matching `]` if last value is 0                 |
| `]`         | Jump back to the matching `[` if last value is 1              |
| `?`         | Pops a number off the stack and skips as many values next to it as the number |
| `=`         | Set the IP position to the value next to it (GOTO)            |
| `W`         | Set the IP position to 0 (repeat the program)                 |

Nio arithmetic is in NOS × TOS order.

Every mathematical operation pops the operands.

### Non-vanilla features

You can define strings with the syntax `""`, comments with `~~ ~~`, and variables with the syntax `|<name>|<value>`.

## Example programs

### Cat program

```IO```

### Numerical cat program

```NO```

### Bit inverter

```>1@-```

### Hello world

```>"Hello, world!"O```

### Simple adder

```NN+O```

### Cooler adder

```NN@:O>" + "O:O+>" = "OO```

### Rectangle area

```nio
>"Width: "O N
>"Height: "O N*O
```

### Continuously generate random bytes

```BOW```

### Random character generator

```r>94*f>32+.```

### Random CJK character generator

*Note: might not work on all terminals*

```nio
r>28607*f>12353+   ~~ generate a code point ~~
::>64/f>64*-       ~~ get the bottom 6 bits ~~
>128+@             ~~ store the last byte ~~
>64/f              ~~ remove the bottom six bits ~~
::>64/f>64*-       ~~ get the bottom 6 bits ~~
>128+@             ~~ store the next byte ~~
>64/f              ~~ remove the bottom six bits ~~
>224+              ~~ store the first byte ~~
...                ~~ print the character ~~
```

### 99 bottles of beer

```nio
>99
[
:O
>" bottles of beer on the wall, "O :O >" bottles of beer.
Take one down and pass it around, "O
>1-
:O >" bottles of beer on the wall.

"O
]
```

## Credits
**notherone**: Creating the original esolang<br>
**JJRubes**: Creating the tokenizer<br>
**olus2000**: Proving Turing-completeness<br>
**alphie_xen**: Fixing bugs<br>
**Zinnia Glean**: Rebooting the esolang<br>

## See also

[nori.io++ (noripp)](https://github.com/MoshiKoi/noripp) by MoshiKoi
