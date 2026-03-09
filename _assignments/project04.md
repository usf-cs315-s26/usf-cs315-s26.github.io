---
layout: assignment
due: 2026-03-24 23:59:59 -0700
github_url: https://classroom.github.com/a/_gaeGcOR
published: true
---

## Requirements 

1. You will write an emulator in C for a subset of the RISC-V Instruction Set Architecture (ISA). 
1. You do not have to emulate the entire instruction set - just enough to emulate the given implementations of `fib_rec`, `get_bitseq`, `int_to_str`, `is_pal`, `max3`, `quadratic`, `sort`, `str_to_int`, and `to_upper`. 
1. Your emulator will need the logic (decoding and emulating instructions) and state (`rv_state`) from lab04
1. Your emulator will support dynamic analysis of instruction execution. Here are the metrics you will collect:
    1. \# of instructions executed (`i_count`)
    1. \# of I-type and R-type instructions executed (`ir_count`)
    1. \# of LD instructions executed (`ld_count`)
    1. \# of ST instructions executed (`st_count`)
    1. \# of jump instructions executed including `j`, `jal`, `jalr` (`j_count`)
    1. \# of conditional branches taken (`b_taken`)
    1. \# of conditional branches not taken (`b_not_taken`)
1. Your emulator will include an implementation of a processor cache simulator for the following cache types: 
    1. A direct mapped cache with a block size on 1 word (given)
    1. A direct mapped cache with a block size of 4 words
    1. A 4-way set associative cache with a block size of 1 word and LRU slot replacement
    1. A 4-way set associative cache with a block size of 4 words and LRU slot replacement

## Given
1. In lecture and lab, we will: 
    1. illustrate how to decode machine code and execute the operations specified
    1. illustrate a direct-mapped cache and describe the data structures and algorithms required for a set-associative cache
    1. We have written a [Guide to Cache Memory](/docs/cache-memory.html) to help you develop your cache implementation
1. In-class coding will be pushed to Github. You will provide the rest of the code yourself
1. You will need to `git pull` in the tests repo to get this semester's test cases

## Grading Rubric
**Automated testing**

70 pts: Automated tests

**Code Review**

1. Option 1: Use an LLM, 10/30 points for code review, up to 80/100 for the project
1. Option 2: Write original code, up to 30/30 pts for code review, up to 100/100 for the project. 
  2. Clean repo, consistent naming and indentation, no dead code, no unnecessarily complex code
  3. Code walkthrough including your implementation of emulation, dynamic analysis, and the instruction cache.
