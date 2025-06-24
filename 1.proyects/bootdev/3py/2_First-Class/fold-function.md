[fold-function](https://en.wikipedia.org/wiki/Fold_(higher-order_function))
also termed 
- reduce
- accumulate
- aggregate
- compress
- inject

Refers to a family of [[Higher-Order-Functions]] that analyze a recursive data structure and through use of a given combining operation, recombine the results of recursively processing its constituent parts, building up a return value. 

Typically a fold is presented with a combining function, a top node of a data structure, and possibly some default values to be used under certain conditions. 

The fold then proceeds to combine elements of the data structure's hierarchy, using the function in a systematic way. 


Folds are in a sense dual to unfolds, which take a seed value and apply a function corecursively to decide how to progressively construct a corecursive data structure, whereas a fold recursively breaks that structure down, replacing it with the results of applying a combining function at each node on its terminal values and the revursive results (catamorphism, versus anamorphism of unfolds).


---
#### As structural transformations
Folds can be regarded as consistently replacing the structural components of a data structure with functions and values. 
Lists, for example, are built up in many functional languages from two primitives: any list is either an empty list, commonly called *nil* (`[]`), or is constructed by prefixing an element in front of another list, creating what is called a cons nnode(`Cons(x1, cons(x2, (cons(x3, cons(... cons(Xn, nil)))))))`, resulting from application of a `cons` function. One can view a fold on lists as replacing the *nil* at the end of the list with a specific value, and replacing each cons with a specific function. 
These replacements can be viewed as a diagram:

![[Pasted image 20241011182159.png]]

There's another way to perform the structural transformation in a consistent manner, with the order of the two links of each node flipped when fed into the combining function:

![[Pasted image 20241011182346.png]]

These pictures illustrate right and left fold of a list visually. 

