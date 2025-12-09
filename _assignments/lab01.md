---
layout: assignment
due: 
github_url: 
published: false
---

## SSH Setup

1. If you already have ssh access to stargate and github (i.e. `ssh git@github.com` works on stargate) you can skip this step
1. If you don't already have ssh configured
    1. Use the [USF VPN](https://myusf.usfca.edu/vpn) to connect to stargate from USF Connect or your home network
    1. Follow [these instructions](/docs/ssh-beagle-setup.html) to configure ssh

## Lab Requirements

Create a Hello World program in C, show it compiling, running, and testing successfully. Here is a hello.c:

```c
#include <stdio.h>

int main(int argc, char **argv) {
    printf("Hello, CS 315!\n");
    return 0;
}
```

Here is a sample `Makefile`:

```make
PROG = lab01
OBJS = hello.o

%.o: %.c
	gcc -c -g -o $@ $<

$(PROG): $(OBJS)
	gcc -g -o $@ $^

clean:
	rm -rf $(PROG) $(OBJS)
```

## Primary Approach: BeagleV-Ahead boards

1. The CS department has purchased a handful of [BeagleV-Ahead boards](https://www.beagleboard.org/boards/beaglev-ahead) for students to connect to using `ssh`
1. The BeagleV-Ahead boards run Ubuntu and connect to the CS department home directories, just like the `vlab` and `clab` VMs. Therefore your repos are available there.
1. If your laptop gets lost/stolen/broken, you can `ssh beagle` to connect to one of the boards
1. You'll need to run the autograder setup steps from above in order to test your solutions

## Backup Approach: Install a RISC-V environment on your laptop

Follow [these instructions](https://github.com/usfca-cs-tools/docs/blob/main/riscv-setup-ubuntu.md)

You must demonstrate that you can do the following actions with your qemu/ubuntu image
1. Start qemu running ubuntu with start.sh
1. ssh into your ubuntu guest
1. Create hello.c with a terminal-based editor (micro/vim/etc.)
1. Compile hello.c with `make`
1. Run hello
1. Clone your github repo with ssh


## Autograder 

To set up the autograder in your RISC-V environment

1. Clone the repo which contains the code
    ```
    cd
    git clone git@github.com:/phpeterson-usf/autograder
    ```
1. Clone the repo which contains the test cases (these will be updated during the semester)
    ```
    git clone git@github.com:/usf-cs315-s25/tests
    ```
1. Edit `~/.bashrc` using a text editor (micro, vim, nano) and adding the line
    ```
    export PATH=~/cs315/autograder:$PATH
    ```
    Be careful not to add spaces around the `=`
1. Set the new value of `PATH` in the shell environment
    ```text
    source ~/.bashrc
    ```

## Rubric

100 pts as shown by the `grade` script