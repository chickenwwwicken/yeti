In mathematics and computer science, a higher-order function(HOF) is a function that does at least one of the following:

- takes one or more functions as arguments(i.e. a procedural parameter, which is a parameter of a procedure that is itself a procedure),
- returns a function or value as its result

All other functions are *first-order* functions. 
In mathematics higher-order functions are aalso termed operators or functionals. 
The differential operator in calculus is a common example, 
since it maps a function to its derivative, also a function. 
Higher-order functions should not be confused with other uses of the word "functor" throughout mathematics.

In the untyped lambda calculus, all functions are higher-order; 
in a typed lambda calculus, from which most functional programming llanguages are derived, 
higher-order functions that take one function as argument are values with types of the form (T1 -> T2) ->T3

### General examples of High-Order Functions

[[2.3_map-function]] , found in many functional programming languages, is one example of a high-order function.
It takes as arguments a function `f` and a collection of elements, and as the result, 
returns a new collection with `f` applied to each element from the collection.

[[sort-function]], which take a comparison function as a parameter, 
allowing the programmer to separate the sorting algorithm from the comparisons of the items being sorted. 
The C standard function `qsort` is an example of this.

- [[filter-function]]
- [[fold-function]]
- [[apply]]
- [[function-composition]]
- [[integration-function]]
- [[callback-function]]
- [[tree-traversal]]
- [[Montague-grammar]] - a semantic theory of natural language, uses higher-order functions

