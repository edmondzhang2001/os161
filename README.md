# OS/161 Operating System

## Overview
OS/161 is a teaching operating system designed to introduce the concepts of kernel development. It runs on the System/161 machine simulator and features a standalone kernel with a simple userland, all written in C.

## Key Components

### Synchronization
The OS provides robust synchronization mechanisms including locks, condition variables, and reader-writer locks. The implementation of these primitives allows the OS to handle concurrent operations securely. These are defined in `synch.h` with the implementations in `synch.c`. A reader-writer lock example is available, showcasing typical usage patterns for ensuring safe concurrent access to shared resources.

### System Calls and Process Support
A comprehensive system call interface is implemented, allowing the kernel to support user program execution. The system supports essential file system calls such as `open`, `read`, `write`, `lseek`, `close`, `dup2`, `chdir`, and `__getcwd`. It also includes process support with `getpid`, `fork`, `execv`, `waitpid`, and `_exit`, establishing OS/161 as a multitasking system.

### Virtual Memory
The virtual memory system provides address translation, TLB management, and page replacement. While swapping is not currently supported, the virtual memory implementation ensures the kernel can manage memory efficiently without exhaustion.

## Building OS/161

To build the OS/161 kernel, navigate to the source directory and use the following commands:

./configure
bmake
bmake install

## Running OS/161

To start the kernel on System/161:

sys161 kernel

## Userland Programs

The kernel is capable of running user programs. System calls have been tested thoroughly to handle various edge cases and provide stable operation.

## Error Handling

Error handling in OS/161 adheres to the descriptions provided in the man pages of the distribution. Where situations arise that are not documented, appropriate error codes from `kern/include/kern/errno.h` are used.

## Getting Help

For assistance configuring and running the kernel, refer to the OS/161 documentation at [ops-class.org](http://www.ops-class.org/asst/0).

## License

OS/161 is licensed under the terms provided by Harvard University, allowing modification and distribution in both source and binary forms.

## Acknowledgments

Special thanks to the educators and contributors at Harvard University for providing 
