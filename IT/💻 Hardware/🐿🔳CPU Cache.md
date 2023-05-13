
First thing first. CPU Cache is a fast memory that is used to improve the latency of fetching information from Main memory ([[👻Memory RAM]]) to CPU registers. So CPU Cache sits between Main memory and CPU. And this cache stores information temporarily so that the next access to the same information is faster. 


I-Cache ---> A CPU cache which used to store executable instructions, it’s called Instruction Cache 
D-Cache --> A CPU cache is used to store data, it’s called Data Cache 
	L1,L2,L3
In its most basic terms, the data flows from the RAM to the L3 cache, then the L2, and finally, L1. When the processor is looking for data to carry out an operation, it first tries to find it in the L1 cache. If the CPU finds it, the condition is called a cache hit. It then proceeds to find it in L2 and then L3.

[[Translation Look aside Buffer (TLB) ]]is required only if Virtual Memory is used by a processor. In short, TLB speeds up the translation of virtual addresses to a physical address by storing page-table in faster memory. In fact, TLB also sits between CPU and Main memory. 