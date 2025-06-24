#### [Synchronous](https://en.wikipedia.org/wiki/Synchronization_(computer_science)) or Blocking
In computer science, synchronization is the task of coordinating multiple processes to join up or handshake at a certain point, in order to reach an agreement or commit to a certain sequence of action. 

---
### Motivation
The need for synchronization does not arise merely in multi-processor systems but for any kind of concurrent processes; even in single processor systems. Mentioned below are some of the main needs for synchronization:

*Forks and Joins* - When a job arrives at a fork point, it is split into N sub-jobs which are then serviced by n tasks. After being serviced, each sub-job waits until all other sub-jobs are done processing. Then, they are joined again and leave the system. Thus, parallel programming requires synchronization as all the parallel processes wait for several other processes to occur.

*Producer-Consumer* - In a producer-consumer relationship, the consumer process is dependent on the producer process until the necessary data has been produced.

*Exclusive use resources*: When multiple processes are dependent on a resource and they need to access it at the same time, the operating system needs to ensure that only one processor accesses it at a given point in time. This reduces concurrency.


---
[[Higher-Order-Functions]]