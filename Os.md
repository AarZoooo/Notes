# UNIT 1

## Introduction

### Operating System
A set of software that acts as an interface between User and Computer Hardware. It also allocates and manages resources of the system to make it run efficiently. For example, it performs tasks like **Memory Management**, **Process Scheduling**, **File Management** etc.

### Functions

1. **Process Management -** Manages processes, including creation, scheduling, and termination.

2. **Memory Management -** Allocates and deallocates memory to processes, handles virtual memory, and prevents memory conflicts.

3. **File Management -**  Manages files on storage devices, including creation, deletion, and access control.

4. **Device Management -** Controls input/output devices, handles device drivers, and manages device queues.

5. **User Interface -** Provides interfaces for user interaction, such as graphical user interfaces (GUIs) or command-line interfaces (CLIs).

### Features

1. **Concurrency -** Handles multiple tasks simultaneously, ensuring efficient resource utilization.

2. **Resource Allocation -** Allocates resources like CPU time, memory, and I/O devices to processes or users in a fair and efficient manner.

3. **Abstraction -** Provides a simplified interface to users and applications, abstracting complex hardware details.

4. **Protection and Security -** Enforces access controls and provide mechanisms to protect system resources from unauthorized access and malicious activities.

5. **Interactivity -** Responds to user inputs promptly, providing a smooth and interactive computing experience.

6. **Extensibility -** Allows for the addition of new features and functionalities through modular design and extensible interfaces.

## Types of OS

### Batch Operating System

This OS creates **batches** of similar jobs to efficiently use resources.

<img src = "https://eng.libretexts.org/@api/deki/files/35038/BatchOS.jpeg?revision=1" height = 400></img>

- Jobs don't interact with the computer directly
- Operator takes all the jobs and groups the similar jobs into batches
- Operator takes the output from batches and shows them to the user

**Advantages:**
- Multiple users can share the same OS
- Less idle time

**Disadvantages:**
- Expensive
- Long waiting time

**Examples:** Punch Cards, Magnetic Tapes

---

### Multi-Program Operating System

It organises jobs so that CPU always has one process to execute, thus increasing efficiency.

<img src = "https://miro.medium.com/v2/resize:fit:1400/1*2kuD8t-fMimdPBZz6UCfAg.png" height = 400></img>

- Less idle time
- Keeps multiple jobs in main memory
- Generally non-primitive
- When a process is demanded by I/O, the CPU can start the execution of the next process
- 
