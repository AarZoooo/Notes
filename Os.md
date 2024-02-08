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

- Keeps multiple jobs in main memory
- Generally non-primitive
- When a process is demanded by I/O, the CPU can start the execution of the next process


**Advantages:**

- Less idle time
- CPU Utilisation is increased

**Disadvantages:**

- Execution of process takes more time

---

### Multi-Tasking Operating System

It organises jobs just like Multi-Program OS, but it divides the execution into repeated cycles of a small time quantum.

<img src = "https://www.itrelease.com/wp-content/uploads/2018/07/Multitasking-in-operating-system.png" height = 400></img>

- Extension of Multi-Program OS
- Fast switching of multiple jobs
- Primitive
- Also called **Time Sharing OS**

**Advantages:**

- Increase in CPU Utilisation and Response Time
- Faster execution of processes

**Disadvantages:**

- Tasks may compete for system resources

---

### Multi-Processing Operating System

The OS Divides the tasks for each CPU Cores, thus multiple processes are executed at once.

<img src="https://lh4.googleusercontent.com/znhDsqLpcd0ssF3vkNUJaxjMDvcUnXHrXoSGqs1lwe-C9kfG0v6VckvMDkJ4F0pgm7b2ryvx2Z-YESVPNhwGCNbdWy4eUJRjIuibFp_7Rc93KkceFm9qG0_no4Ggfoeq-4zOptrZfCvxulkc97iz5AI" height = 400></img>

- Multiple CPUs share memory buses and memory devices
- Multiple Processes executed at the same time

**Advantages:**

- Reliable
- Fast Processing
- Maximum Throughput

**Disadvantages:**

- More Complex
- Expensive
- More Memory requirement

---

### Distributed Operating System

This OS uses multiple CPUs and devices, but to the user it appears as a single centralised device.

<img src = "https://media.geeksforgeeks.org/wp-content/uploads/20230605102519/What-is-Distributed-Operating-System.png" height = 400></img>

- Users can access multiple components accross the system
- Multiple tasks are executed simultaneously at different system nodes

**Advantages:**

- Scalable: Can be expanded by adding more hardware to the network
- Fault-Tolerance: Can continue working after some hardware failure
- Less Delay

**Disadvantages:**

- Expensive
- Complex

---

### Real Time Operating System

This OS is used when time is the most important factor. This OS is strict on time.

<img src = "https://www.guru99.com/images/1/121119_0515_Realtimeope1.png" height = 400>

- Strict on time
- Time intervals are required to process and respond

**Advantages:**

- Better Resource management
- Simple to develop
- Error-free

**Disadvantages:**

- Expensive
- Complex Algorithms used
- Potential Crashes

---