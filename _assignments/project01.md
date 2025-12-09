---
layout: assignment
due: 
github_url: 
published: false
---

## Requirements
1. You will implement a base conversion tool called `project01`. It converts numbers expressed in bases 2, 10, and 16 into the other two bases. Examples:
	```text
    $ ./project01 10 -o 2
    0b1010
    $ ./project01 0xFF -o 10
    255
    $ ./project01 0b11011110101011011011111011101111 -o 16
    0xDEADBEEF
    $ ./project01 0b11111111111111111111111111111111 -o 10
    4294967295
    $ ./project01 0x0000000B -o 10
    11
    $ ./project01 0b123 -o 2
    Bad input
	```

1. You must implement the base conversions yourself, without using C library `printf(%d)`, `printf("%x")`,  `scanf()`, or `atoi()`
1. You must provide a `Makefile` which builds an executable called `project01`

## Given
We will review processing command line arguments in C

Pseudocode for `uint32_t string_to_int(char *str)`

    init retval to 0
    init placeval to 1 (anything to the 0 power is 1)
    loop over str from the highest index down to 0
        calculate the integer corresponding to the character at that index	
        calculate the value of that place by multiplying the integer * placeval
        add the value to the retval
        update to placeval to placeval * base
    return the return value

Pseudocode for `void int_to_string(uint32_t value, char *str, int base)`

    init buffer to empty
    while value != 0
        quot = value / base
        rem = value % base
        calculate the character value of rem
        append the character value to the buffer
        value = quot
    copy buffer into str in reverse order

## Rubric

1. 100 points as shown by autograder running on beagle/riscv64
