1. The core components of Linux (kernel, user space, init/systemd) 

### Kernel  
* The kernel is the core of Linux.  
* It manages hardware resources like CPU, memory, disks, and devices.  
* Handles process scheduling, memory management, device drivers, and system calls.  
* Runs in privileged mode (kernel space).  

### User Space  
* Where user applications and utilities run (shells, editors, browsers, servers).  
* Programs cannot directly access hardware; they interact with the kernel via system calls.  
* Includes system libraries (e.g., glibc) and user commands (`ls`, `ps`, `grep`, etc.).  

### init / systemd  
* The first process started by the kernel (PID 1).
* Responsible for starting, stopping, and managing system services.
* Modern Linux systems mostly use **systemd** instead of older init systems.

---

2. How Processes Are Created and Managed  
* A new process is created using `fork()`, which duplicates an existing process.  
* The new process usually calls `exec()` to replace its memory with a new program.  
* Each process has:  

  * A unique PID  
  * Its own memory space  
  * File descriptors  
  * A priority and state (running, sleeping, stopped, zombie)  
* The kernel scheduler decides which process gets CPU time.  
* Processes can communicate using signals, pipes, shared memory, and sockets.  

3. What systemd Does and Why It Matters  

* **systemd** is the system and service manager for Linux.  
* It:  

  * Starts services in parallel (faster boot times)  
  * Restarts failed services automatically  
  * Manages dependencies between services  
  * Handles logging (`journald`)  
  * Manages timers, mounts, and user sessions  
* Services are defined using **unit files** (`.service`, `.socket`, `.timer`).  
* It matters because it makes systems **faster, more reliable, and easier to manage**, especially at scale.  

