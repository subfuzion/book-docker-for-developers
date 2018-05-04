# Understanding Docker

To understand Docker, it helps to first understand how programs work on Linux to put things into context. To further appreciate Docker, it will also help to learn a bit about Unix and Linux history and the quest for process isolation, control over resource access and consumption, and portability.

### The Linux Kernel

When a computer starts up, the system BIOS \(Basic Input/Output System\) firmware stored in flash memory loads a program, called the _boot loader_, from a known location on a storage device. The boot loader through one or more stages then loads the operating system kernel into random-access memory \(RAM\).

The kernel's primary responsibilities are to manage system resources, control when user processes can run, and provide a means for user processes to request system services, including hardware-related services, through a standard interface known as system calls \(e.g., _open, read, write, close, exec, fork, wait, exit, kill_\).

When the kernel is loaded, it continues the boot process by going through several stages of initialization, which include probing for hardware at various I/O ports, running some kind of init process to start various housekeeping tasks, necessary background system processes, and administratively configured background processes \(_daemons_\), such as mail, DNS, and web servers, and finally starting a process to handle user login and communication through a terminal.

The Linux kernel is the core part of the operating system that is present regardless of which Linux distribution you use. Different Linux distributions, such as Debian, Ubuntu, Red Hat, CentOS, etc., may be released on different schedules for updated kernels, and may come bundled with different init systems, packages, and package managers, but they all have the Linux kernel in common. In fact, technically, Linux IS just the Linux kernel; everything else is just a particular Linux distribution. This distinction will be important to remember when we start to discuss Docker containers.

 As noted, the kernel starts a number of other processes; these processes run in _user space_, which is a region of memory that does not have access to _kernel space_. Kernel space is a protected region of memory for the kernel \(and loadable kernel modules\) that can execute code in privileged _kernel mode_. 

Only the kernel can access protected system resources, including hardware; a program running in user space can only access the kernel through the system call interface that the kernel exposes. Although this means the program is now temporarily running in kernel mode, all it was able to do before the switch from user mode is set up the arguments for the system call; it had no other means to influence any kernel space data structures; now that the request is being handled in kernel mode, the kernel will enforce any restrictions \(such as not allowing a file to be opened for which the user process does not have permission to read\).

Through the terminal, a user can interact with the kernel through a _shell_ program running as user space process. For example, using a shell a user can enter commands to read and write files. The shell process runs with the permissions of the user, no different than any other programs owned by the user, and like any other process goes through the same system call interface to access protected resources through the kernel.



