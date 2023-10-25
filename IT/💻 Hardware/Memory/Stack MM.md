**LIFO**

-  **very fast** 
-  **finite and static**
-   This is where the execution data of the functions are stored as **stack frames**
-   **Multi-threaded applications** can have a **stack per thread**.
-   Memory management of the stack is **simple and straightforward** and is done by the OS.
-   Typical data that are stored on stack are **local variables**(value types or primitives, primitive constants), **pointers** and **function frames**.
-   This is where you would encounter **stack overflow errors** as the size of the stack is limited compared to the Heap.
-   There is a **limit on the size** of value that can be stored on the Stack for most languages.