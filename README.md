# Inter-Process-Commmunication
Linux supports a number of Inter-Process Communication (IPC) mechanisms so that processes communicate with each other and with the kernel to coordinate their activities.
The IPC mechanisms can be classified into the following categories as given below:
1. Pipes
2. Fifos
3. Shared memory
4. Mapped memory
5. Message queues
6. Sockets

PIPES : A pipe is a communication device that permits unidirectional communication i.e they are half-duplex. Data written to the “write end” of the pipe is read back from the “read end.” Pipes are serial devices; the data is always read from the pipe in the same order it was written.Typically, a pipe is used to communicate between two threads in a single process or between parent and child processes.
A call to the pipe() function returns a pair of file descriptors. One of these descriptors is connected to the write end of the pipe, and the other is connected to the read end. Anything can be written to the pipe, and read from the other end in the order it came in.
pipe() takes an array of two ints as an argument. Assuming no errors, it connects two file descriptors and returns them in the array. The first element of the array is the reading-end of the pipe, the second is the writing end.

MESSAGE QUEUES : Message queues provide an asynchronous communications protocol, meaning that the sender and receiver of the message do not need to interact with the message queue at the same time. Messages placed onto the queue are stored until the recipient retrieves them. Message queues have implicit or explicit limits on the size of data that may be transmitted in a single message and the number of messages that may remain outstanding on the queue.
UNIX implements message passing by keeping an array of linked lists as message queues. Each message queue is identified by its index in the array, and has a unique descriptor. A given index can have multiple possible descriptors.
