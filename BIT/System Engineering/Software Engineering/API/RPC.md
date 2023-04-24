In distributed computing, a remote procedure call (RPC) is when a computer program causes a procedure (subroutine) to execute in a different address space (commonly on another computer on a shared network), which is coded as if it were a normal (local) procedure call, without the programmer explicitly coding the details for the remote interaction. 

That is, the programmer writes essentially the same code whether the subroutine is local to the executing program, or remote. This is a form of client–server interaction (caller is client, executor is server), typically implemented via a request–response message-passing system.

In the object-oriented programming paradigm, RPCs are represented by remote method invocation (RMI). The RPC model implies a level of location transparency, namely that calling procedures are largely the same whether they are local or remote, but usually, they are not identical, so local calls can be distinguished from remote calls. Remote calls are usually orders of magnitude slower and less reliable than local calls, so distinguishing them is important.

RPCs are a form of inter-process communication (IPC), in that different processes have different address spaces: if on the same host machine, they have distinct virtual address spaces, even though the physical address space is the same; while if they are on different hosts, the physical address space is different. Many different (often incompatible) technologies have been used to implement the concept.

Sequence of events
The client calls the client stub. The call is a local procedure call, with parameters pushed on to the stack in the normal way.
The client stub packs the parameters into a message and makes a system call to send the message. Packing the parameters is called marshaling.
The client's local operating system sends the message from the client machine to the server machine.
The local operating system on the server machine passes the incoming packets to the server stub.
The server stub unpacks the parameters from the message. Unpacking the parameters is called UN-marshaling.
Finally, the server stub calls the server procedure. The reply traces the same steps in the reverse direction.