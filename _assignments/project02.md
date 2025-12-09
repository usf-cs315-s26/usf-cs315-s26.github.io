---
layout: assignment
due: 
github_url: 
published: false
---

## Requirements

1. You will develop RISC-V assembly language implementations of the following problems, and print the results to ensure that both the C implementation and your RISC-V implementation compute the correct answer.
1. Your executables must be named as follows, and must be compiled with a `Makefile`
1. We will test your projects using autograder

**to_upper**

Given a string of upper, lower, and non-alphanumeric characters, transform lowercase letters into uppercase letters.

    $ ./to_upper FooBar1
    C: FOOBAR1
    Asm: FOOBAR1

**swap**

Given an array of integers, swap element at index i with the element at index j:

    ./swap <i> <j> <a0> <a1> <a2> ...

    $ ./swap 0 1 5 4 3 2 1
    C: 4 5 3 2 1
    Asm: 4 5 3 2 1
    ./swap 4 3 11 22 33 55 66 77
    C: 11 22 33 66 55 77
    Asm: 11 22 33 66 55 77

**find_max_index**

Given an array of integers, return the index of the largest integer in the array

    $ ./find_max_index 5 4 3 2 1
    C: 0
    Asm: 0
    $./find_max_index 1 2 3 4 5
    C: 4
    Asm: 4

**sort**

Given the address of an array of unsigned integers, and the length of the array, sort the input array descending (largest to smallest) in place given the C implementation of the sorting algorithm. Your `sort_s` implementation must use `find_max_index_s`

    $ ./sort 10 30 20
    C: 30 20 10
    Asm: 30 20 10

## Given

1. The starter repo contains C implementations for each of the programs
1. Autograder test cases are available

## Rubric

1. 80 points: automated test cases
1. 20 points: interactive grading questions, including but not limited to
    1. Design decisions (why did you choose to do it this way?)
    1. Explanation of your implementation (show me how X works?)
    1. Problems encountered and debugged
    1. Code quality: consistent formatting, no dead or redundant code, no unnecessarily complex code, readable comments
1. Interactive grading logistics
    1. You must show your code in a RISC-V environment (local guest or beagle), and in a terminal editor (not github.com or VS Code or other GUI tool)
    1. Since we have large sections this semester, we will have 10 minute meetings. Please be on time
    and ready to show your code. We don't have time to fix `ssh` or audio/video issues in Zoom.
