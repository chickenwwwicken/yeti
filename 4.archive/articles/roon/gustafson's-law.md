in computer architecture, Gustafson's law gives the speedup in the execution time of a task that theretically gains from parallel computing a using a hypothetical run of the task on a single-core machine as the baseline. To put it another way, it is the theoretical "slowdown" of an already parallelized task if running on a serial machine. It is named after cooomputer scientist John L. Gustafson and his colleague Edwin H. Barsis, and was presented in the article *Reevaluating [[amdahl's-law]]* in 1988.

![[gustafson's-law.png]]

### Definition
Gustafson estimated the speedup S of a program gained by using parallel computing as follows: 

![[gustafson's-law.svg]]

where

`S` = theoretical speedup of the program with parallelism (scaled speedup);
`N` = number of processors;
`s` and `p` = fractions of time spent executing the serial parts and the parallel parts oof the program, respectively, on the parallel syystem, where `s + p = 1`

Alternatively, `S` can be expressed using `p`:
![[gustafson's-law2.svg]]

Gustafson's law addresses the shortcomings of Amdahl's law, which is based on the assumption of a fixed problem size, that is of an execution workload that does not change with respect to the improvement of the  resources. Gustafson's law instead proposes that programmers tend to increase the size of problems to fully exploit the computing power that becomes available as the resources improve. 

Gustafson and his colleagues further observed from their workloads that time for the serial part typically does not grow as the problem and the system scale, that is, *s* is fixed. This gives a linear model between the processor count *N* and the speedup *S* with slope `1 - s`, as shown in the figure above (which uses different notations: *P* for *N* and *a* for *s*). Also, *S* scales linearly with *s* rather than exponentially in the Amdahl's Law. With these observations, Gustafson 'expected to extend their success on parallel computing to a broader range of applications and even larger values for *N*'.

The impact of Gustafson's law was too shift research gals to select or reformulate problems so that solving a larger problem in the same amount of time would be possible. In a way the law redefines efficiency, due to the possibility that limitations imposed by the sequential part of a program may be countered by increasing the total amount of computation.

---
#### Other links
[[amdahl's-law]]
[[agi-futures]]