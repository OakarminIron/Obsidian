Microkernel (also abbreviated μK or uK) is the term describing an approach to operating system design by which the functionality of the system is moved out of the traditional "kernel", into a set of "servers" that communicate through a "minimal" kernel, leaving as little as possible in "system space" and as much as possible in "user space"

Kernel    <--> Servers  <--> Software OS


IPC  


The microkernel approach consists of defining a simple abstraction over the hardware, with a set of primitives or [system calls](https://en.wikipedia.org/wiki/System_call "System call") to implement minimal OS services such as [memory management](https://en.wikipedia.org/wiki/Memory_management "Memory management"), [multitasking](https://en.wikipedia.org/wiki/Computer_multitasking "Computer multitasking"), and [inter-process communication](https://en.wikipedia.org/wiki/Inter-process_communication "Inter-process communication"). Other services, including those normally provided by the kernel, such as [networking](https://en.wikipedia.org/wiki/Computer_networking "Computer networking"), are implemented in user-space programs, referred to as _servers_. Microkernels are easier to maintain than monolithic kernels, but the large number of system calls and [context switches](https://en.wikipedia.org/wiki/Context_switch "Context switch") might slow down the system because they typically generate more overhead than plain function calls.

-   Larger running memory footprint that a program uses or references while running.
-   More software for interfacing is required, there is a potential for performance loss.
-   Messaging bugs can be harder to fix due to the longer trip they have to take versus the one off copy in a monolithic kernel.
-   Process management in general can be very complicated.

The disadvantages for microkernels are extremely context-based. As an example, they work well for small single-purpose (and critical) systems because if not many processes need to run, then the complications of process management are effectively mitigated.