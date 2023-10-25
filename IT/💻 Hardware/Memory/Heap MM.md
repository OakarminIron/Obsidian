Heap is used for **dynamic memory allocation** and unlike stack, the program needs to look up the data in heap using **pointers**

- Heap is **shared** among threads of an application.
- Slower
- Typical data that are stored on the heap are **global variables**, **reference types** like objects, strings, maps, and other complex data structures.
- This is where you would encounter **out of memory errors** if your application tries to use more memory than the allocated heap
- Generally, there is **no limit** on the size of the value that can be stored on the heap. Of course, there is the upper limit of how much memory is allocated to the application.