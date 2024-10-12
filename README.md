# WELCOME
Feel free to contact me via email at richardmaliyetu@gmail.com

# Project Overview

## Introduction:
This project is a basic producer-consumer model implemented using threads, where a producer generates data blocks and a consumer processes them. The goal was to create a simple, multi-threaded program that uses a deque (double-ended queue) to handle data. The producer enqueues data at random intervals, and the consumer dequeues it, with both running simultaneously until the user decides to stop them. It also uses signal handling to allow the user to safely terminate the program (via Ctrl+C on Mac).

## Contact:
For any questions or issues with grading, please feel free to reach out at:
**Email:** r215@umbc.edu

## Installation and Setup
**Setup:**
Before running the project, ensure you have a Linux environment with gcc installed. You'll also need basic POSIX thread support (pthread) since the project uses threads.

**Dependencies:**
  gcc compiler
  POSIX threads (pthread)
  Make (if you want to build using the Makefile)
  
## Build and Compile:
To build the project, use the provided Makefile. Simply run: **make main**

This will compile the main program and produce an executable named **deque_program**.

If you want to compile the test program as well, you can run: **make test**

## Running the Program
To run the main program: **make main**

To run the test program: **make test**

## Memory leak tests
If you want to check for memory issues using valgrind, you can run:

**make main_memcheck** for main program memory leaks

**make test_memcheck** for test program memory leaks 

### Note: 
The main program will run indefinitely until manually stopped with Ctrl+C.

## Testing Strategy

**Test Cases:**
Several scenarios were tested to ensure correct functionality:

  Basic functionality: Ensuring that the producer can enqueue data, and the consumer can dequeue it without errors.
  
  Randomness: Verifying that data is enqueued and dequeued in random order (either front or rear), as expected.
  
  Thread Safety: Ensuring that multiple producer and consumer threads can operate without crashing or corrupting data.
  
  Edge cases: Tested with empty deque operations (e.g., what happens when the consumer tries to dequeue from an empty deque).
  
  Signal handling: Ensuring that the program terminates gracefully upon receiving a SIGINT signal (via Ctrl+C).


**Troubleshooting**

Common Issues:
Unused parameter warning: When compiling, you might see warnings about the signal parameter being unused. This can be ignored 

Random crashes or segmentation faults: These might happen if the deque isn’t initialized correctly, or if memory management is off. Double-check the init_deque and delete_deque functions and make sure that all data is being managed properly.

Threads not terminating properly: Make sure you're using Ctrl+C to stop the program, as it’s set up to terminate threads safely upon receiving a SIGINT.

**References**

POSIX Threads (pthread) Documentation: Used for creating and managing threads in this project.
Link: https://www.cs.cmu.edu/afs/cs/academic/class/15492-f07/www/pthreads.html

Deque implementation inspiration: A basic understanding of double-ended queues was taken from various online resources like GeeksforGeeks.
Link: https://www.geeksforgeeks.org/c-implementation-double-ended-queue/

Signal Handling in C: Reference for implementing signal handling to terminate threads: GNU C Library Signal Handling
Link: https://ftp.gnu.org/old-gnu/Manuals/glibc-2.2.3/html_chapter/libc_24.html

AI-based Input: AI tools like ChatGPT were used to help debug and refactor parts of the code, especially in terms of thread management and memory handling strategies.
