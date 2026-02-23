# Operating System Basics

An Operating System (OS) is system software that manages computer hardware, software resources, and provides common services for computer programs. It acts as an intermediary between users and computer hardware.

---

## 1. What is an Operating System?
The OS is the most important program that runs on a computer. Every general-purpose computer must have an OS to run other programs.

### Main Functions
- **Process Management**: Create, schedule, terminate processes
- **Memory Management**: Allocate and free memory
- **File System Management**: Organize and access files
- **Device Management**: Control input/output devices
- **Security & Protection**: User authentication, access control
- **User Interface**: CLI, GUI, shell

---

## 2. Types of Operating Systems
- **Batch OS**: Processes jobs in batches
- **Time-Sharing OS**: Multiple users share CPU time
- **Distributed OS**: Manages multiple connected machines
- **Real-Time OS**: Responds within fixed time constraints
- **Mobile OS**: Android, iOS
- **Desktop OS**: Windows, macOS, Linux

---

## 3. Process Management
### 3.1 What is a Process?
A process is a program in execution.

### Process States
- **New**: Being created
- **Ready**: Waiting for CPU
- **Running**: Instructions being executed
- **Waiting**: Waiting for an event
- **Terminated**: Finished execution

### Process Control Block (PCB)
Stores process information:
- Process ID
- Program counter
- CPU registers
- Memory limits
- Open files

---

## 4. Threads
A thread is a lightweight process. Multiple threads share the same process resources.

### Benefits
- Faster creation and termination
- Lower context-switch cost
- Shared memory space
- Better responsiveness

---

## 5. CPU Scheduling
The OS selects processes from the ready queue and allocates the CPU to them.

### Common Scheduling Algorithms
- **FCFS** (First Come First Served)
- **SJF** (Shortest Job First)
- **Priority Scheduling**
- **Round Robin**
- **Multilevel Queue Scheduling**

---

## 6. Memory Management
### Main Goals
- **Efficiency**: Use memory optimally
- **Protection**: Prevent processes from interfering
- **Sharing**: Allow processes to share memory

### Techniques
- **Paging**
- **Segmentation**
- **Virtual Memory**

### Virtual Memory
Allows execution of processes not completely in memory.
- Uses disk space as an extension of RAM
- Enables larger programs than physical memory
- Uses demand paging

---

## 7. Deadlock
A situation where multiple processes are blocked forever, each holding a resource and waiting for another.

### Four Necessary Conditions
1. **Mutual Exclusion**
2. **Hold and Wait**
3. **No Preemption**
4. **Circular Wait**

### Handling Methods
- Prevention
- Avoidance
- Detection and recovery
- Ignorance (Ostrich algorithm)

---

## 8. File System
Organizes data on storage devices.

### Common Operations
- Create
- Read
- Write
- Delete
- Rename
- Permissions

### File Structure
- Sequential access
- Direct access
- Indexed

---

## 9. I/O Management
The OS controls all input/output devices:
- Keyboard
- Mouse
- Monitor
- Disk
- Printer
- Network cards

### I/O Modes
- Programmed I/O
- Interrupt-driven I/O
- Direct Memory Access (DMA)

---

## 10. Common OS Interview Questions
1. Explain process vs thread
2. What is a deadlock? How to prevent it?
3. What is virtual memory?
4. Explain CPU scheduling algorithms
5. What is paging?
6. Difference between user mode and kernel mode
7. What is a semaphore?
8. Explain critical section problem
