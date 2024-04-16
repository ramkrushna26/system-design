
#### Concurrency
- Two or more task executing concurrently (not overlapping execution)
- it give sense of false impression that task are executing parallely due to lot of context switching

</br>  
 
#### Parallelism
- Two or more task executing simultenously (overlapping execution)

</br>  

- java, c, golang --- uses available CPU cores to fullest
- python use threasing which is concurrent, but not parallel

</br>  

- sub task split + delegation to multiple cores/workers

</br>  

#### Achieving concurrency
- **thread**: basic unit of CPU utilization (lightweight process)
- **process**: instance of program being executed (can be made of multiple threads)

</br>  

**When context switching happens?**  
- when process/thread perform I/O
- interrupts explicitly

</br>  

**Issues with concurrency**  
- communication between sub-components is complex (shared memory model)
  - or shared file on disk ---- use disk for communication
- number of possible execution paths -- very large
- interminate outcomes --- depending on execution path
- concurrent use of shared resources --- high db connections & same memory blocks without locks
- complicated co-ordination & data exchange

</br>  

**how to handle concurrency?**  
- make things thread safe ----- locks & locks free data structures

</br>  

**stuff to read**  
- deadlock & starvation
- parallel algorithm
- lock free data struture
- persistant data structure








