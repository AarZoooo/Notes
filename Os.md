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

## System Calls

These are interfaces provided by the OS that lets the user commands request deeper level services, like file operations, process management etc. Basically it's a way of user level processes to talk with the kernel.

- Typically written in a high-level language (C / C++)
- Examples are:
    - **Win32 API** for Windows
    - **POSIX API** for Unix, Linux and Mac OS X
    - **Java API** for JVM 

### 1. Process Control Call

- Create or Terminate a process. 
- Wait for a process
- Get Process ID for a process
- Allocate or free memory
- Debugger and Locks

### 2. File Management Call

- Create, Open, Read, Write, Close or Delete a file
- Get or set file attributes

### 3. Device Management Call

- Request, Release, Read, Write or Control a device
- Get or set device attributes

### 4. Information Maintenance Call

- Get or set System time
- Get status of a process
- Get system information

### 5. Protection Call

- Get or set permissions
- Control access to resources
- Allow or deny user access

## System Programs

These are programs provided by the OS to control or manipulate certain aspects of the system.

### Types:

- **Text Editors** like Notepad, nano, vi

- **File Management tools** like File Explorer (Windows), Finder (macOS), ls (Linux)

- **Compiler and Interpreter** like gcc, javac, python

- **Debuggers** like gdb, WinDbg

- **System Monitoring tools** like Task Manager (Windows), Activity Monitor (macOS), top (Linux)

## Process

An instance of a running program is a process. An OS is responsible to allocate resources to a process for its execution. OS uses **Process Control Block (PCB)** to keep track of processes.

- **Process** represents execution of a program.
- **PCB** stores data related to a process like process ID, state, priority, CPU registers, and memory management information
- **Process Scheduling** is performed by the OS by allocating specific CPU time to each process based on certain algorithms and priorities

## Threads

A process can be divided into lightweight sub-processes that can be individually identified. These are called Threads.

- **Resource Sharing:** Threads share same memory space and resources
- **Independence:** Threads can execute independently
- **Concurrency:** Threads execute simultaneously, allowing multiple tasks to be performed at the same time
- **Communication:** Threads of a same process communicate with each other, as they share same resources
- **Lightweight:** Threads are parts of a process so they are lightweight

## CPU Scheduling

It is the process of determining which processes or threads should be allocated CPU time and in what order. Basically it is arranging processes or threads in a line or multiple lines based on some priority and then letting them execute individually or multiple at the same time.

### Types:

**1. Preemptive Scheduling**

- OS can interrupt a running process and allocate those resources to another process with higher priority
- Ensures fairness by prohibiting long-running processes to occupy resources for a long time
- Common in **Real Time OS** and **Multi-User Systems** where responsiveness is critical

**2. Non-Preemptive Scheduling**

- OS can't interrupt a running process. When a running process voluntarily releases the resources, only then the OS can reallocate another process
- Simpler to implement
- May lead to poor responsiveness

### Criteria for Scheduling:

1. **CPU Utilisation:** Maximizing the utilisation of CPU by keeping it busy
2. **Throughput:** Maximizing the number of processes completed in unit time
3. **Turnaround Time:** Minimizing the time taken by a process from start to end
4. **Waiting Time:** Minimizing the total waiting time by processes
5. **Response Time:** Minimizing the time taken between a request and its result

### Scheduling Algorithms:

1. **FCFS (First Come First Serve):** Processes are executed in the order they arrive
2. **SJN (Shortest Job Next):** Process with the shortest CPU time is executed next
3. **RR (Round Robin):** Processes executed in a cyclic manner repeatedly, each time for a small CPU time quantum
4. **Priority Scheduling:** Processes have priorities, and the process with highest priority executes first
5. **Multilevel Queue Scheduling:** Processes are categorized into different queues based on priority, and scheduling is performed among these queues.

## Inter-Process Communication

This allows processes that are running simultaneously to exchange data and synchronize their actions.

### Methods:

- **Shared Memory:** Processes share a region of memory to communicate directly
- **Message Passing:** Processes share messages to each other through the OS
- **Pipes:** One-Directional channel of communication between two processes
- **Sockets:** Endpoints over a network, that allow two processes to communicate
- **Signals:** Asynchronous messages sent by processes or the OS to signal events, or handle exceptions

## Remote-Procedure Calls (RPC)

RPC allows a process to execute on a remote system as if it were a local system. This is achieved by hiding the network communication between the different parts of the system, making the remote call procedure transparent to the programmer. Distributed Computing is acieved using this.

- RPCs typically follow a **Client-Server Architecture**, where the Client systems put processes, and those processes are executed in the Server system.
- Parameters and Results which flow through the network are serialized and deserialized between systems to facilitate the communication, also called **Marshalling and Unmarshalling**
- **Stub Code** on the client side and **Skeleton Code** on the server side handle Marshalling and Unmarshalling of RPCs

## Process Synchronization

It is the process of arranging processes or threads that are running simultaneously in such a way that they don't cause trouble to each other when they access the same resources. This prevents issues like race conditions, deadlocks, and starvations.

### Race Condition

> to be continued

<br>

# UNIT 2

## Memory Management

It is the process of controlling and coordinating computer memory, assigning portions called blocks to various running programs to optimize overall system performance.

**Importances:**

- Allocation and Deallocation of memory before and after process execution
- Minimize the fragmentation issues
- Proper utilization of Main Memory

### Address Binding

Address binding is the process of mapping the program's logical or virtual addresses to corresponding physical or main memory addresses.

#### Compile time

The compiler translates symbolic addresses to absolute addresses. If you know at compile time where the process will reside in memory, then absolute code can be generated.

- Advantage: Minimum setup time.
- Disadvantage: If the program to get loaded into the main memory is targeting to a memory location which is already occupied by any other program, then collision will occur. The current program will override.

#### Load time

The compiler translates symbolic addresses to relative (relocatable) addresses. The loader translates these to absolute addresses. If it is not known at compile time where the process will reside in memory, then the compiler must generate relocatable code.

#### Execution time

If the process can be moved during its execution from one memory segment to another, then binding must be delayed until run time. The absolute addresses are generated by hardware.

---

> **Frames:** Partitions of the main memory

> **Pages:** Partitions of the secondary memory

### Logical Address

It is generated by CPU while a program is running.

- User can view the logical address
- Used as a reference to access the physical memory location
- Generated by CPU
- Has two parts: **Page Number**, **Page Offset**

### Physical Address

It is the address in the Main Memory. It is generated by Memory Management Unit

- User can't view the physical address
- Can't be directly accessed
- Generated by memory management unit
- Has two parts: **Frame Number**, **Frame Offset**

## Techniques of Memory Management

### 1. Contiguous memory management

Assigning continuous blocks of memory to the processes. Types of Contiguous memory management are:

- **Fixed (static) partition** 

    Characteristics:
    - Number of partitions are fixed
    - Size of each partition may or may not be same

    Disadvantages:
    - Internal Fragmentations
    - Limit in Process size
    - External Fragmentation
    - Limitation on degree of multi-programming

    <br>

- **Variable (dynamic) partition**

    Memory is allocated to processes only when they come into the RAM.

    Characteristics:
    - No Internal Fragmentation
    - No limitations on Processes or Process sizes

    Disadvantages:
    - External Fragmentation
    - Allocation and Deallocation is complex


### 2. Non-Contiguous memory management

The program is divided into blocks and loaded at different portions of memory.

- **Paging**
        
    Characteristics:

    - Fixed size partitions
    - Secondary and Main memory is divided into equal and fixed size partitions
    - The partitions of secondary memory are known as **Pages**, and those of the main memory are known as **Frames**.
    - Details of each page is stored in **Page table**
    - Number of pages (size) = Number of frames (size)
    - Closer to the Operating System
    - Sufferes from internal fragmentation
    - Invisible to the User

- **Segmentation**

    Characteristics:

    - Process is divided into segments, which need not be of same size.
    - Uses variable partitioning
    - Details of each segment is stored in **Segment table**
    - Closer to the User
    - Suffers from external fragmentation
    - Visible to the User

        Let us have these Segments with their base addresses:

            Segments | Base A
            ---------+-------
               S1    |  100
               S3    |  200
               S5    |  500
               S2    |  700
               S4    |  1000
                     |  1200
          
        Therefore the queue for execution is going to be:

            Base A  |  Limit
            --------+-------
              100   |   100
              700   |   300
              200   |   300
              1000  |   200
              500   |   200

## Virtualization
        
It is a technique that allows the execution of process that are not completely in memory.

Virutal memory simpley appears to be present but it is not present physically.

- Programmer should not worry about the size of process and available physical memory
- Large sized programs can easily execute
- It reduces external fragmentation
- Degree of multi-programming is increased

### Page Fault

A type of interruption that happens when a running process ascesses the main memory page that are mapped into virtual memory but not loaded in the main memory.

### Page Replacement

The process in which a page from main memory is replaced with a page from secondary memory. It is a technique used by OS to decide which memory page to **swap out**. It also decides how much memory is to be allocated to each memory process.

**Algorithms used:**

- **First In First Out (FIFO)**
    - Very Simple to use
    - Oldest inserted Page is replaced with new page
    - Performance is not good
- **Optimal Page Replacement (OPR)**
    - Replaces the page which is least likely to be used in the future
- **Least Recently Used (LRU)**
    - Replaces the least recently used page, i.e. Page which has not been used for the longest time in the Main memory.

---

### Numerical Example for FIFO

**Reference String:-** 7, 0, 1, 2, 0, 3, 0, 4, 2, 3, 0, 3, 1, 2, 0

**Memory Block Size:-** 3

    Case 1:                     Case 2:                     Case 3:

    +-----+                     +-----+                     +-----+
    |  7  |  -> Page Fault      |  7  |                     |  7  |  
    +-----+                     +-----+                     +-----+
    |     |                     |  0  |  -> Page Fault      |  0  |  
    +-----+                     +-----+                     +-----+
    |     |                     |     |                     |  1  |  -> Page Fault
    +-----+                     +-----+                     +-----+

    Case 4:                     Case 5:                     Case 6:

    +-----+                     +-----+                     +-----+
    |  2  |  -> Page Fault      |  2  |                     |  2  |  
    +-----+                     +-----+                     +-----+
    |  0  |                     |  0  |  -> Page Hit        |  3  |  -> Page Fault
    +-----+                     +-----+                     +-----+  
    |  1  |                     |  1  |                     |  1  |  
    +-----+                     +-----+                     +-----+

    Case 7:                     Case 8:                     Case 9:

    +-----+                     +-----+                     +-----+
    |  2  |                     |  4  |  -> Page Fault      |  4  |  
    +-----+                     +-----+                     +-----+
    |  3  |                     |  3  |                     |  2  |  -> Page Fault
    +-----+                     +-----+                     +-----+
    |  0  |  -> Page Fault      |  0  |                     |  0  |  
    +-----+                     +-----+                     +-----+

    Case 10:                    Case 11:                    Case 12:

    +-----+                     +-----+                     +-----+
    |  4  |                     |  0  |  -> Page Fault      |  0  |  
    +-----+                     +-----+                     +-----+
    |  2  |                     |  2  |                     |  2  |  
    +-----+                     +-----+                     +-----+
    |  3  |  -> Page Fault      |  3  |                     |  3  |  -> Page Hit
    +-----+                     +-----+                     +-----+

    Case 13:                    Case 14:                    Case 15:

    +-----+                     +-----+                     +-----+
    |  0  |                     |  0  |                     |  0  |  -> Page Hit
    +-----+                     +-----+                     +-----+
    |  1  |  -> Page Fault      |  1  |                     |  1  |  
    +-----+                     +-----+                     +-----+
    |  3  |                     |  2  |  -> Page Fault      |  2  |  
    +-----+                     +-----+                     +-----+

Therefore:

- **Cases =** 15
- **Page Faults =** 12, **Average =** $\frac{12}{15}$
- **Page Hits =** 3, **Average =** $\frac{3}{15}$

---

### Numerical Example for OPR

**Reference String:-** 7, 0, 1, 2, 0, 3, 0, 4, 2, 3, 0, 3, 2, 1, 2, 0, 1, 7, 0, 1

**Memory Block Size:-** 4

    Case 1:                     Case 2:                     Case 3:                     Case 4:

    +-----+                     +-----+                     +-----+                     +-----+
    |  7  |  -> Page Fault      |  7  |                     |  7  |                     |  7  |    
    +-----+                     +-----+                     +-----+                     +-----+
    |     |                     |  0  |  -> Page Fault      |  0  |                     |  0  |  
    +-----+                     +-----+                     +-----+                     +-----+
    |     |                     |     |                     |  1  |  -> Page Fault      |  1  |
    +-----+                     +-----+                     +-----+                     +-----+
    |     |                     |     |                     |     |                     |  2  |  -> Page Fault
    +-----+                     +-----+                     +-----+                     +-----+

    Case 5:                     Case 6:                     Case 7:                     Case 8:

    +-----+                     +-----+                     +-----+                     +-----+
    |  7  |                     |  3  |  -> Page Fault      |  3  |                     |  3  |    
    +-----+                     +-----+                     +-----+                     +-----+
    |  0  |  -> Page Hit        |  0  |                     |  0  |  -> Page Hit        |  0  |  
    +-----+                     +-----+                     +-----+                     +-----+
    |  1  |                     |  1  |                     |  1  |                     |  4  |  -> Page Fault
    +-----+                     +-----+                     +-----+                     +-----+
    |  2  |                     |  2  |                     |  2  |                     |  2  |  
    +-----+                     +-----+                     +-----+                     +-----+

    Case 9:                     Case 10:                    Case 11:                    Case 12:

    +-----+                     +-----+                     +-----+                     +-----+
    |  3  |                     |  3  |  -> Page Hit        |  3  |                     |  3  |  -> Page Hit
    +-----+                     +-----+                     +-----+                     +-----+
    |  0  |                     |  0  |                     |  0  |  -> Page Hit        |  0  |  
    +-----+                     +-----+                     +-----+                     +-----+
    |  4  |                     |  4  |                     |  4  |                     |  4  |
    +-----+                     +-----+                     +-----+                     +-----+
    |  2  |  -> Page Hit        |  2  |                     |  2  |                     |  2  |  
    +-----+                     +-----+                     +-----+                     +-----+

    Case 13:                    Case 14:                    Case 15:                    Case 16:

    +-----+                     +-----+                     +-----+                     +-----+
    |  3  |                     |  3  |                     |  3  |                     |  3  |  
    +-----+                     +-----+                     +-----+                     +-----+
    |  0  |                     |  0  |                     |  0  |                     |  0  |  -> Page Fault
    +-----+                     +-----+                     +-----+                     +-----+
    |  1  |                     |  1  |  -> Page Fault      |  1  |                     |  1  |  
    +-----+                     +-----+                     +-----+                     +-----+
    |  2  |  -> Page Fault      |  2  |                     |  2  |  -> Page Fault      |  2  |  
    +-----+                     +-----+                     +-----+                     +-----+

    Case 17:                    Case 18:                    Case 19:                    Case 20:

    +-----+                     +-----+                     +-----+                     +-----+
    |  3  |                     |  7  |  -> Page Fault      |  7  |                     |  7  |  
    +-----+                     +-----+                     +-----+                     +-----+
    |  0  |                     |  0  |                     |  0  |  -> Page Hit        |  0  |  
    +-----+                     +-----+                     +-----+                     +-----+
    |  1  |  -> Page Hit        |  1  |                     |  1  |                     |  1  |  -> Page Hit
    +-----+                     +-----+                     +-----+                     +-----+
    |  2  |                     |  2  |                     |  2  |                     |  2  |  
    +-----+                     +-----+                     +-----+                     +-----+                

Therefore:

- **Cases =** 20
- **Page Faults =** 9, **Average =** $\frac{9}{20}$
- **Page Hits =** 11, **Average =** $\frac{11}{20}$

---

### Numerical Example for LRU

**Reference String:-** 7, 0, 1, 2, 0, 3, 0, 4, 2, 3, 0, 3, 2, 1, 2, 0, 1, 7, 0, 1

**Memory Block Size:-** 4

    Case 1:                     Case 2:                     Case 3:                     Case 4:

    +-----+                     +-----+                     +-----+                     +-----+
    |  7  |  -> Page Fault      |  7  |                     |  7  |                     |  7  |    
    +-----+                     +-----+                     +-----+                     +-----+
    |     |                     |  0  |  -> Page Fault      |  0  |                     |  0  |  
    +-----+                     +-----+                     +-----+                     +-----+
    |     |                     |     |                     |  1  |  -> Page Fault      |  1  |
    +-----+                     +-----+                     +-----+                     +-----+
    |     |                     |     |                     |     |                     |  2  |  -> Page Fault
    +-----+                     +-----+                     +-----+                     +-----+

    Case 5:                     Case 6:                     Case 7:                     Case 8:

    +-----+                     +-----+                     +-----+                     +-----+
    |  7  |                     |  3  |  -> Page Fault      |  3  |                     |  3  |    
    +-----+                     +-----+                     +-----+                     +-----+
    |  0  |  -> Page Hit        |  0  |                     |  0  |  -> Page Hit        |  0  |  
    +-----+                     +-----+                     +-----+                     +-----+
    |  1  |                     |  1  |                     |  1  |                     |  4  |  -> Page Fault
    +-----+                     +-----+                     +-----+                     +-----+
    |  2  |                     |  2  |                     |  2  |                     |  2  |  
    +-----+                     +-----+                     +-----+                     +-----+

    Case 9:                     Case 10:                    Case 11:                    Case 12:

    +-----+                     +-----+                     +-----+                     +-----+
    |  3  |                     |  3  |  -> Page Hit        |  3  |                     |  3  |  -> Page Hit
    +-----+                     +-----+                     +-----+                     +-----+
    |  0  |                     |  0  |                     |  0  |  -> Page Hit        |  0  |  
    +-----+                     +-----+                     +-----+                     +-----+
    |  4  |                     |  4  |                     |  4  |                     |  4  |
    +-----+                     +-----+                     +-----+                     +-----+
    |  2  |  -> Page Hit        |  2  |                     |  2  |                     |  2  |  
    +-----+                     +-----+                     +-----+                     +-----+

    Case 13:                    Case 14:                    Case 15:                    Case 16:

    +-----+                     +-----+                     +-----+                     +-----+
    |  3  |                     |  3  |                     |  3  |                     |  3  |  
    +-----+                     +-----+                     +-----+                     +-----+
    |  0  |                     |  0  |                     |  0  |                     |  0  |  -> Page Fault
    +-----+                     +-----+                     +-----+                     +-----+
    |  1  |                     |  1  |  -> Page Fault      |  1  |                     |  1  |  
    +-----+                     +-----+                     +-----+                     +-----+
    |  2  |  -> Page Fault      |  2  |                     |  2  |  -> Page Fault      |  2  |  
    +-----+                     +-----+                     +-----+                     +-----+

    Case 17:                    Case 18:                    Case 19:                    Case 20:

    +-----+                     +-----+                     +-----+                     +-----+
    |  3  |                     |  7  |  -> Page Fault      |  7  |                     |  7  |  
    +-----+                     +-----+                     +-----+                     +-----+
    |  0  |                     |  0  |                     |  0  |  -> Page Hit        |  0  |  
    +-----+                     +-----+                     +-----+                     +-----+
    |  1  |  -> Page Hit        |  1  |                     |  1  |                     |  1  |  -> Page Hit
    +-----+                     +-----+                     +-----+                     +-----+
    |  2  |                     |  2  |                     |  2  |                     |  2  |  
    +-----+                     +-----+                     +-----+                     +-----+                  

Therefore:

- **Cases =** 20
- **Page Faults =** 9, **Average =** $\frac{9}{20}$
- **Page Hits =** 11, **Average =** $\frac{11}{20}$

## Disk Structure

### 1. Magnetic Disc

Magnetic disks provide the bulk of secondary storage for modern computer systems.

<img src = "https://prepinsta.com/wp-content/uploads/2023/01/Magnetic-Disk-Structure-in-OS.webp">

<br>

When the disk is in use, a drive motor spins it at high speed. Most drives rotate 60 to 250 times per second, specified in terms of rotations per minute (RPM).

**Access time** has two major components:
1. **Seek time** is the time for the disk to move the heads to the cylinder containing the desired sector.
2. **Rotational latency** is the additional time waiting for the disk to rotate the desired sector to the disk head

**Bad Sector:** Bad Sector on a hard drive is simply a tiny cluster of storage space (a sector) of the hard drive that appears to be defective. This bad sector won’t respond to read or write requests.

Bad sectors can occur from physical damage of a hard disk (not repairable) or can be occurred from software errors(repairable)

### 2. Solid-State Disks(SSD)

<img src = "https://uwaterloo.ca/arts-computing-newsletter/sites/ca.arts-computing-newsletter/files/uploads/images/hard-drive-guide-ssd-diagram_1.jpg" height = 400>

- SSDs use memory technology as a small fast hard disk. Specific implementations may use either flash memory or DRAM chips protected by a battery to sustain the information through power cycles.

- Because SSDs have no moving parts they are much faster than traditional hard drives, and certain problems such as the scheduling of disk accesses simply do not apply.

- However SSDs also have their weaknesses: They are more expensive than hard drives, generally not as large, and may have shorter life spans.

- SSDs are also used in laptops to make them smaller, faster, and lighter.

- Because SSDs are so much faster than traditional hard disks, the throughput of the bus can become a limiting factor, causing some SSDs to be connected directly to the system PCI bus for example.

### 3. Magnetic Tapes

<img src = "https://www.clir.org/wp-content/uploads/sites/6/2017/02/figure_1.gif">

- Magnetic tapes were once used for common secondary storage before the days of hard disk drives, but today are used primarily for backups.

- Accessing a particular spot on a magnetic tape can be slow, but once reading or writing commences, access speeds are comparable to disk drives.

- Capacities of tape drives can range from 20 to 200 GB, and compression can double that capacity.

## Disk Formatting

Disk formatting is a process to configure the data-storage devices such as hard-drive, floppy disk and flash drive when we are going to use them for the very first time or we can say initial usage. Disk formatting is usually required when new operating system is going to be used by the user. It is also done when there is space issue and we require additional space for the storage of more data in the drives. When we format the disk then the existing files within the disk is also erased. We can perform disk formatting on both magnetic platter hard-drives and solid-state drives.

As we know that disk formatting deletes data and removes all the programs installed within the drive. So, it can be done with caution. We must have the backup of all the data and applications which we require. No-doubt disk formatting requires time. But the frequent formatting of the disk decreases the life of the hard-drive.

Types of Disk Formatting are:

### 1. Low-Level Formatting

Low level formatting is a type of physical formatting. This is the process of marking of cylinders and tracks of the blank hard-disk. After this there is the division of tracks into sectors with the sector markers. Nowadays low-level formatting is performed by the hard-disk manufactures themselves.

This formatting is not suggested to users.

### 2. Partitioning

As suggesting from the name, partitioning means divisions. Partitioning is the process of dividing the hard-disk into one or more regions. The regions are called as **partitions**.

It can be performed by the users and it will affect the disk performance.

### 3. High-level Formatting

High-level formatting is the process of writing. Writing on a file system, cluster size, partition label, and so on for a newly created partition or volume. It is done to erase the hard-disk and again installing the operating system on the disk-drive.

Generally, It does not harm the hard-disk. It can be done easily with the Administrator, Windows snap-in Disk Management tool, diskpart, etc.

#### Steps of High Level Formatting

- Clear data on Hard Disk
- Generate boot information
- Initialize FAT
- Label logical bad sectors

## Disc Scheduling Algorithms

One of the responsibilities of the operating system is to use the hardware efficiently. For the disk drives, meeting this responsibility entails having fast **access time** and large **disk bandwidth**.

### FCFS Scheduling

The simplest form of disk scheduling is, of course, the first-come, first-served (FCFS) algorithm. It serves the request in the same order as they are received. This algorithm is intrinsically fair, but it generally does not provide the fastest service.

<img src = "https://media.geeksforgeeks.org/wp-content/uploads/20200520231323/fcfsfcfs1.jpg" width = 600>

Advantages :
- Simple , fair to all request. 
- No starvation. 

Disadvantages :
- Not efficient because the average seek time is high.

### Shortest Seek Time First (SSTF)

<img src = "https://media.geeksforgeeks.org/wp-content/uploads/20200520231053/sstfsstf.jpg" width = 600>

- Selects the request with the minimum seek time from the current head position.
- SSTF scheduling is a form of SJF scheduling; may cause starvation of some requests.

### SCAN SCHEDULING

<img src = "https://media.geeksforgeeks.org/wp-content/uploads/20200620092728/finalFSCAN.jpg" width = 600>

- Sometimes called the **elevator algorithm**.
- The head starts at the one end of the disk and moves toward on the other end. It serves all the requests coming in the way.
- After reaching another end the direction of head movement is reversed.

### C-SCAN (Circular SCAN) Scheduling

<img src = "https://media.geeksforgeeks.org/wp-content/uploads/20200710025228/lkshdvj.jpg" width = 600>

- The circular SCAN algorithm improves upon SCAN by treating all the request in a circular queue fashion: once the head reaches the end of the disk, it returns to the other end without processing any request, and then starts again from the beginning of the disk.
-  The head moves from one end of the disk to the other. servicing requests as it goes. When it reaches the other end, however, it immediately returns to the beginning of the disk, without servicing any requests on the return trip.
-  Treats the cylinders as a circular list that wraps around from the last cylinder to the first one. 
- Illustration shows total head movement of 382 cylinders, plus return time.
-  Provides a more uniform wait time than SCAN.

### LOOK Scan

It is like SCAN scheduling, but the head doesn't go to the absolute end unnecessarily, it reverses from the last request in that particular direction.

### C-LOOK Scan

It is like a combination of Look Scan and C-Scan scheduling. The head doesn't unnecessarily travel to the ends, it serves the last request in a particular direction and goes to the next request at the other end.

## Device Management

Device management in operating system implies the management of the I/O devices such as a keyboard, magnetic tape, disk, printer, microphone, USB ports, scanner, camcorder etc.as well as the supporting units like control channels.

The basics of I/O devices can fall into 3 categories:

1. **Block device**: it stores information in fixed-size block, each one with its own address. For e.g. disks.
2. **Character device**: delivers or accepts a stream of characters. The individual characters are not addressable. For example printers, keyboards etc.
3. **Network device**: For transmitting data packets.

### Characteristics

- Keep tracks of all devices and the program which is responsible to perform this is called I/O controller.

- Monitoring the status of each device such as storage drivers, printers and other peripheral devices.

- Enforcing preset policies and taking a decision which process gets the device when and for how long.

- Allocates and Deallocates the device in an efficient way.

- De-allocating them at two levels:
    - at the process level when I/O command has been executed and the device is temporarily released
    - at the job level, when the job is finished and the device is permanently released.

- Optimizes the performance of individual devices.

### Types of devices

The OS peripheral devices can be categorized into the followings:

- **Dedicated devices:** Such type of devices in the device management in operating system are dedicated or assigned to only one job at a time until that job releases them. Devices like printers, tape drivers, plotters etc. demand such allocation scheme since it would be awkward if several users share them at the same point of time. The disadvantages of such kind of devices is the inefficiency resulting from the allocation of the device to a single user for the entire duration of job execution even though the device is not put to use 100% of the time.

- **Shared devices:** These devices can be allocated to several processes. Hard Disk can be shared among several processes at the same time by interleaving their requests. The interleaving is carefully controlled by the Device Manager and all issues must be resolved on the basis of predetermined policies.

- **Virtual Devices:** These devices are the combination of the first two types and they are dedicated devices which are transformed into shared devices. For example, a printer converted into a shareable device via spooling program which re-routes all the print requests to a disk. A print job is not sent straight to the printer, instead, it goes to the disk(spool) until it is fully prepared with all the necessary sequences and formatting, then it goes to the printers. This technique can transform one printer into several virtual printers which leads to better performance and use.

## RAID (Redundant Array of Independent Disks)

RAID works on the basis that several small-capacity disk drives are more efficient than a few large-capacity disk drives. This is because by distributing the data among several smaller disks, the system  can simultaneously access the requested  data from the multiple drives, resulting  in improved I/O performance.

A variety of disk-organization techniques, collectively called redundant arrays of independent disks (RAID), are commonly used to address the performance and reliability issues. In the past, RAIDs composed of small, cheap disks were viewed as a cost-effective alternative to large, expensive disks. Today, RAIDs are used for their higher reliability and higher data-transfer rate, rather than for economic reasons.

### Benefits

- **Improvement of Reliability via Redundancy**

  A logical disk consists of two physical disks, and every write is carried out on both disks. If one of the disks in the volume fails, the data can be read from the other.

- **Improvement in Performance via Parallelism**

  Improvement in transfer rate by striping data across the disks. Data striping generally consists of splitting the bits of each byte across multiple disks; such striping is called **bit-level striping**.

  In **block-level striping**, blocks of a file are striped across multiple disks. Other levels of striping, such as bytes of a sector or sectors of a block, also are possible. Block-level striping is the most common.

  Basically it achieves the following:

  - Increase the throughput of multiple small accesses by load balancing.
  - Reduce the response time of large accesses

### RAID Levels

Mirroring provides high reliability, but it is expensive. Striping provides high data-transfer rates, but it does not improve reliability. Numerous schemes are introduced to provide redundancy at lower cost by using disk striping combined with “parity” bits. These schemes have different cost-to-performance trade-offs and are classified according to levels called **RAID levels**.

- **RAID level 0:** Refers to disk arrays with striping at the level of blocks but without any redundancy (such as mirroring or parity bits).

  <img src = "https://miro.medium.com/v2/resize:fit:1024/0*tv5m3e5J7QAGuSRx.png" width = 400>

  Advantages
    - RAID 0 offers great performance, both in read and write operations. There is no overhead caused by parity controls.
    - All storage capacity is used, there is no overhead.
    - The technology is easy to implement.

  Disadvantages
    - RAID 0 is not fault-tolerant. If one drive fails, all data in the RAID 0 array are lost. It should not be used for mission-critical systems.

- **RAID level 1:** Refers to disk mirroring.

  <img src = "https://qph.cf2.quoracdn.net/main-qimg-52c2cee4e0f425a7920c1cef09262a56.webp" width = 400>

  Advantages
    - RAID 1 offers excellent read speed and a write-speed that is comparable to that of a single drive.
    - In case a drive fails, data do not have to be rebuilt, they just have to be copied to the replacement drive.
    - RAID 1 is a very simple technology.

  Disadvantages
    - The main disadvantage is that the effective storage capacity is only half of the total drive capacity because all data get written twice.
    - Software RAID 1 solutions do not always allow a hot swap of a failed drive. That means the failed drive can only be replaced after powering down the computer it is attached to. For servers that are used simultaneously by many people, this may not be acceptable. Such systems typically use hardware controllers that do support hot swapping.

  RAID-1 is ideal for mission critical storage, for instance for accounting systems. It is also suitable for small servers in which only two data drives will be used.

- **RAID level 2:**  It is also known as memory-style error-correcting-code (ECC)   organization.

  <img src = "https://www.sitesbay.com/os/images/raid-2.png">

  Memory systems have long detected certain errors by using parity bits. Each byte in a memory system may have a parity bit associated with it that records whether the number of bits in the byte set to 1 is even `(parity = 0)` or odd `(parity = 1)`. If one of the bits in the byte is damaged `(either a 1 becomes a 0, or a 0 becomes a 1)`, the parity of the byte changes and thus does not match the stored parity. Similarly, if the stored parity bit is damaged, it does not match the computed parity. Thus, all single-bit errors are detected by the memory system.

- **RAID level 3:** Also known as bit-interleaved parity organization.

  <img src = "https://i.stack.imgur.com/f1A3I.png" width = 500>

  It improves on level 2 by taking into account the fact that, unlike memory systems, disk controllers can detect whether a sector has been read correctly, so a single parity bit can be used for error correction as well as for detection.

- **RAID level 4:**  Also known as block-interleaved parity organization.

  <img src = "https://www.r-explorer.com/img/blog/media/0008-img04.png">

  It uses block-level striping, as in RAID 0, and in addition keeps a parity block on a separate disk for corresponding blocks from N other disks. If one of the disks fails, the parity block can be used with the corresponding blocks from the other disks to restore the blocks of the failed disk.

- **RAID level 5:** Also known as block-interleaved distributed parity.

  <img src = "https://itenterpriser.com/wp-content/uploads/2020/04/What-is-RAID-5.jpg" height = 400>

  It differs from RAID 4 in that it spreads data and parity among all N + 1 disks, rather than storing data in N disks and parity in one disk. For each block, one of the disks stores the parity and the others store data.

- **RAID level 6:** Also called the P + Q redundancy scheme

  <img src = "https://itenterpriser.com/wp-content/uploads/2020/04/What-is-RAID-6.jpg" height = 400>

  It is much like RAID level 5 but stores extra redundant information to guard against multiple disk failures. Instead of parity, error-correcting codes such as the Reed – Solomon codes are used.

- **RAID levels 0+1 and 1+0:** It refers to a combination of RAID levels 0 and 1. RAID 0 provides the performance, while RAID 1 provides the reliability. Generally, this level provides better performance than RAID 5. It is common in environments where both performance and reliability are important.

  <img src = "https://images.wondershare.com/recoverit/article/2022/07/combine-raid-0-and-1.jpg" height = 400>

  