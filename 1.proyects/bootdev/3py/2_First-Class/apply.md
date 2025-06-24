[apply](https://en.wikipedia.org/wiki/Apply) is a function that applies a function to arguments. 
It is central to programming languages derived from lambda calculus, 
such as LISP and Scheme, and also in functional languages. 
It has a role in the study of the denotational semantics of computer programs, 
because it is a continuous function on complete partial orders. 

Apply is also a continuous function in homotopy theory, and, indeed underpins the entire theory:
it allows a homotopy deformation to be viewed as a continuous path in the spaace of functions. 

Likewise, valid mutations (refactorings) of computer programs can be seen as those that are "continuous" in the Scott topology.

The most general setting for applly is in category theory, where it is right adjoint to currying in closed monoidal categories.
A special case of this are the Cartesian closed categories, 
whose internal language is simply typed lambda calculus.

---
#### In computer programming
appllies a function to a list of arguments. 
Eval and apply are the two interdependent components of the eval-apply cycle, 
which is the essence of evaluating Lisp, described in SICP. 
Function application corresponds to beta reduction in lambda calculus.

### Apply Function
Apply is also the name of a [[Higher-Order-Functions]] in many languages, 
which takes a function and a list, 
and uses the list as the function's own argument list, 
as if the function were called with the elements of the list as the arguments.

This is important in languages with variadic functions,
because this is the only way to call a function with an indeterminate(at compile time) number of arguments.