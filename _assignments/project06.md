---
layout: assignment
due: 
github_url: 
published: false
---

## Due 

1. Submit all of the .dig files and .hex files required to run your processor implementation
1. Submit a PDF for your Decoder spreadsheet
1. Interactive grading will be scheduled on Wed 4/23. The signup link will be given in Campus Wire.

## Requirements

1. You will implement a single-cycle microarchitecture for a subset of the RISC-V instruction set architecture in Digital
    1. You may use any of Digital's library of components
    1. We will introduce some new and useful tools and techniques for Digital in lecture
1. You need to pass unit tests and complete program tests provided below. Note that the complete program requirements are the same as for Project04. The unit tests will help you incrementally build and test your processor. We will provide a starter instruction memory with the unit tests and the complete program tests from Project04.
1. In order to make the given functions for testing runnable on your processor the given files contain these changes:
    1. A `main` function at the top of the file (offset 0)
    1. The end marker (`unimp`) indicates when the program should stop
    1. No `.global` or `.align 4` directives should be present in the programs
1. Your processor implementation will include the following major sub-circuits:
    1. The Program Counter (`PC`) will be one 64-bit register with enable (`EN`) and clear (`CLR`) inputs.
    1. Machine code programs will be stored in ROM components, just as we did in Project05. Like in Project05 your instruction memory will be able to select the program you want to execute.
    1. A Register File that can support reading 2 registers in a single clock cycle: `RD0`, `RD1`
    1. The Arithmetic Logic Unit (ALU) will perform data processing tasks such as `add`, `sub`, `mul`, and shifting (`sll`, `slr`, `sra`). You will need to support more than these operations.
    1. The Branch Control Unit (BCU) will perform conditional branch computation and PC updates. You will need to decide where to put this logic in the top-level circuit.
    1. Data Memory. We will use a Digital RAM component for data memory. This will be used for stack memory by our test programs. We will configure the RAM component to hold 64 bit word values. This will make it easy to support `ld` and `sd`. You will need to add logic for word- and byte-size memory operations.
    1. The Control Unit will decode machine code instructions and generate control signals.
    1. The Data Path will connect data between the various sub-circuits
    1. The Control Path will connect the Control unit to various sub-circuits and multiplexers

## Given
1. We will discuss the major sub-circuits in lecture and you will have hands-on time to develop and ask questions
1. We have compiled [Project 06 Guide Part 3](/docs/project06-part-3.html)
1. We will provide a starter instruction memory with the unit tests and complete program tests.
1. We will provide a Python script for creating a decode ROM hex file.

## Tests

**Unit  Tests**

The ROMs for these tests contains the necessary machine code

- 00-add-r
- 01-add-i
- 02-sll-r
- 03-sll-i
- 04-srl-r
- 05-srl-i
- 06-sd-ld
- 07-sw-lw
- 08-jal
- 09-j
- 10-beq
- 11-blt
- 12-bge
- 13-mul
- 14-lui
- 15-sb-lb

**Complete  Program Tests**

You must add (using `as`, `objdump`, and `makerom3.py`) the machine code to these ROMs

- 16-quadratic
- 17-get_bitseq
- 18-max3
- 19-fib-rec
- 20-is-pal
- 21-to-upper
- 22-sort
- 23-str-to-int

## Rubric
For interactive grading you should be able to run the autograder tests and manually execute your sort_s and merge_sort_s programs.
- (30 points) Automated unit tests
- (40 points) Automated complete program tests
- (10 points) Interactive grading question #1
- (10 points) Interactive grading question #2
- (10 points) Neatness
