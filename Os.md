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

It is a type of resource management applied to the computer memory. The requirement of memory management is to provide the ways of dynamically portioning of memory to program and free-ing on request if it is not used anymore.

**Importances:**

- Allocation and Deallocation of memory before and after process execution
- Minimize the fragmentation issues
- Proper utilization of Main Memory

<br>

---

>**Frames:** Partitions of the main memory

>**Pages:** Partitions of the secondary memory

---

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

### 1. **Contiguous memory management**

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

<br>

### 2. **Non-Contiguous memory management**

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
    - Uses variabele partitioning
    - Details of each segment is stored in **Segment table**
    - Closer to the User
    - Suffers from external fragmentation
    - Visible to the User

            Let us ave these Segments with their base addresses:

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

## Virtualization
        
It is a technique that allows the execution of process that are not completely in memory.

Virutal memory simpley appears to be present but it is not present physically.

- Programmer should not worry about the size of process and available physical memory
- Large sized programs can easily execute
- It reduces external fragmentation
- Degree of multi-programming is increased