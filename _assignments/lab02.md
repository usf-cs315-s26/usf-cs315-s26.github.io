---
layout: assignment
due: 
github_url: 
published: false
---

## Requirements

1. You will develop C and RISC-V assembly language implementations of the following arithmetic problems. 
1. Your executable must be compiled with a Makefile
1. Before you add files to your repo, do a `$ make clean` so you don't add/commit build products like executables or .o files
1. We will test the labs using autograder

**add4:** Adds four 32-bit integers together and returns the result. Example:

    $ ./add4 1 2 3 4
    C: 10
    Asm: 10

**quadratic:** Runs the quadratic equation (ax^2 + bx + c) on the 32-bit integers x, a, b, c and returns the result. Example:

    $ ./quadratic 4 3 2 1
    C: 57
    Asm: 57

**min:** Calculates the smaller of two 32-bit integers and returns its value. Example:

    $ ./min 2 3
    C: 2
    Asm: 2

## Given

We will demonstrate a framework for compiling C and assembly language source files, and calling assembly language functions from C

## Rubric

1. 100 points as shown by autograder running on a beagle riscv64 host

