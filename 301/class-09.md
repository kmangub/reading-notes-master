  # Functional Programing

**Pure Functions** returns the same result ig given the same arguments, or deterministic and it does not cause any observable side effects.

Functions where it reads external files and uses a random number generator are not pure functions. Another example of non-pure functions are if they cause observable side effects. This includes altering the global variables a certain way or if the parameters are passed by reference. 

**Immutable data** is when something cannot be changed after it's created.

**Referential Transparency** is when we have pure functions and immutable data to create memoize functions, or simplified functions.

Functions as first-class entities can refer to it from constants and variables, pass it as a parameter to other functions, and return it as result from other functions.

**Higher-order functions** takes one or more functions as arguments, or returns function as its result.

**Reduce** receives a function and returns the value created by the items. W