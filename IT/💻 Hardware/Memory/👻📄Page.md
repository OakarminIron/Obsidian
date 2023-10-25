A page, memory page, or virtual page is a fixed-length contiguous block of virtual memory, described by a single entry in the page table.
Since every access to memory must be mapped from virtual to physical address, reading the page table every time can be quite costly. Therefore, a very fast kind of cache, [[Translation Look aside Buffer (TLB) ]], is often used. [[🐿📄Page Cache]]. 


A page table is the data structure used by a virtual memory system in a computer operating system to store the mapping between [[👻Virtual-Addresses]] and Physical Addresses. 