In computer science, [function composition](https://en.wikipedia.org/wiki/Function_composition_(computer_science)) is an act or mechanism to combine simple functions to build more complicated ones. 
Like the usual composition of functions in mathematics, theresult of each function is passed as the argument of the next, and the result of the last one is the result of the whole. 

Programmers frequently apply functions to results of other functions, and almost all programming languages allow it. In some cases, the composition of functions is interesting as a function in its own right, to be used later. Such a fuunction can always be defined but languages with [[First-Class-Functions]] make it easier. 

The ability to easily compose functions encourages factoring (breaking apart) functions for maintainability and code reuse. More generally, big systems might be buuilt by composing whole programs.

Narrowly speaking, function composition applies to functions that operate on a finite amount of data, each step sequentially processing it before handing it to the next. Functions that operate on potentially infinite data(a stream or other codata) are known as filters, and are instead connected in a pipeline, which is analogous to function composition and can execute concurrently.

---
[[Higher-Order-Functions]]

