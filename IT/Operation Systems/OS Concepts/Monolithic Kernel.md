- All OS Service  run with the main kernel [[Thread]].  thus also residing in the same memory area. 
- This approach provides rich and powerful hardware access.
- Since there is less software involved it is faster.
- As it is one single piece of software it should be smaller both in source and compiled forms.
- Less code generally means fewer bugs which can translate to fewer security problems.


-   Bugs in one part of the kernel have strong side effects; since every function in the kernel has all the privileges, a bug in one function can corrupt data structure of another, totally unrelated part of the kernel, or of any running program.
-   Kernels often become very large and difficult to maintain.
-   Even if the modules servicing these operations are separate from the whole, the code integration is tight and difficult to do correctly.
-   Since the modules run in the same [[👻📄Page]], a bug can bring down the entire system.
-   Monolithic kernels are not portable; therefore, they must be rewritten for each new architecture that the operating system is to be used on.

[[Linux]]

![[LinuxOperatingSystems.png]]
![[LinuxApplicationEnvironment.png]]