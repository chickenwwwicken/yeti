In computer architecture Amdahl's law or *argument* is a formula which gives the theoretical speedup in latency of the execution of a task fixed workload that can be expected of a system whose resources are improved. 

The law can be stated as:

"The overall performance improvement gained by optimizing a single part of system is limited by the fraction of time that the improved part is actually used".

It is named after a computer scientist Gene Amdahl, and was presented at the American Federation of Imformation Processing Societies (AFIPS) Spring Joint Computer Conference in 1967. 

Often used in parallel computing to predict the theoretical speedup when using multiple processors. For example, if a program needs 20 hrs to complete using a single thread, and a one-hour portion of the program cannot be parallelized, then only the remaining 19 hrs executioon time can be parallelized. Therefore, regardless of how many threads are devoted to a parallelized execution of this program, the minimum execution time is always more than 1 hr. Hence. the theoretical speedup is , at most, 20 times the single thread performance, (1/1-p =20).

### Definition
Amdahl's law can be formulated in the following way:

![[amdahls-law.svg.svg]]

where:
- `Slatency` = the theoretical speedup of the execution of the whole task`
- `s` = the speedup of the part of the task that benefits from improved system resources;
- `p` = the proportion of execution time that the part benefiting from improved ressources originally occupied. 

Furthermore, 

![[amdahls-law-2.svg.svg]]shows that the theoretical speedup of the execution of the whole task increases with the improvement of the resources of the system and that regarless of the magnitude of the improvement, the theoretical speedup is always limited by the part of the task that cannot benefit from the improvement. 

Amdhal's law applies only to the cases where the problem size is fixed. In practice, as more computing resources become available, the tend to get used on larger problems (larger datasets), and the time spent in the parallelizable part often grows much faster than the inherently serial work. In this case, [[gustafson's-law]] gives a less pessimistic and more realistic assessment of the parallel performance.