---
layout: assignment
due: 
github_url: 
published: false
---

## Requirements

1. You will develop RISC-V assembly language implementations of the following problems, and print the results to ensure that both the C implementation and your RISC-V implementation compute the correct answer.
1. Your executables must be named as follows. A `Makefile` is provided in the given repo.
1. We will test your projects using autograder
1. Automatically-generated code using a C compiler or generative AI (Chat GPT etc.) is not acceptable. You must develop the programs yourself.

**pack_bytes**

Given four 1-byte values (unsigned), you will combine them into a single 32-bit signed integer value.

    $ ./pack_bytes
    usage: pack_bytes <b3> <b2> <b1> <b0>

    $ ./pack_bytes 1 2 3 4
    C: 16909060
    Asm: 16909060

    $ ./pack_bytes 255 255 255 255
    C: -1
    Asm: -1

**unpack_bytes**

Given a signed 32 bit integer value, unpack each byte as an unsigned value:

    $ ./unpack_bytes 1000000
    C: 0 15 66 64
    Asm: 0 15 66 64

    $ ./unpack_bytes -2
    C: 255 255 255 254
    Asm: 255 255 255 254

**get_bitseq** (this will be developed in class)

Given a 32-bit unsigned integer, extract a sequence of bits and return as an unsigned integer. Bits are numbered from 0 at the least-significant place to 31 at the most-significant place. Here is the usage:

`get_bitseq <value> <start_bit> <end_bit> `

    $ ./get_bitseq 94117 12 15 
    C: 6
    Asm: 6

    $./get_bitseq 94117 4 7
    C: 10
    Asm: 10

**get_bitseq_signed**

Given a 32-bit unsigned integer, extract a sequence of bits and return as a signed integer. Bits are numbered from 0 at the least-significant place to 31 at the most-significant place. When computing the signed return value you can assume the end_bit is the most significant bit of the signed bit range. You need to sign-extend this value to become a 32-bit 2's complement signed value. Here is the usage:

`get_bitseq_signed <value> <start_bit> <end_bit>`

    $ ./get_bitseq_signed 94117 12 15 C: 6
    Asm: 6

    $./get_bitseq_signed 94117 4 7
    C: -6
    Asm: -6

**str_to_int**

Given an input number and base, convert the string to an integer. The given code prints the integer in base 10 using `printf()`

    $./str_to_int 0xff -o 10
    C: 255
    Asm: 255

**int_to_str**

Given an input number and base, use the given `str_to_int_c()` implementation to get an integer. You will implement `int_to_str_s` to convert the integer into its string representation.

    $ ./int_to_str 0xff -o 2
    C: 0b11111111
    Asm: 0b11111111

## Given

The starter repo contains C implementations for each of the programs

## Rubric

1. 80 points: automated test cases. You may need to `git pull` in the tests repo.
1. 20 points: code quality graded offline. 
    1. Consistent formatting
    1. No dead or redundant code
    1. No unnecessarily complex code
    1. Readable comments
    1. No build products in the repo
