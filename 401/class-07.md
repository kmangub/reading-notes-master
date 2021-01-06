# Global and Non-Local Keywords
Scope is how variables and names are found in our code and is dependant on where that variable is created. This is shown through the **LEGB** rule, which stands for:

- **Local** - Names created inside of the function call, even after calling the function recursively. 
- **Enclosing** - A scope for nested functions.
- **Global** - Names that are visible anywhere in the code. 
- **Built-in** - Keywords that are automatically loaded in Python

LEGB is primarily used for better code management and to avoid name collisions. 

## Scope 

Scope defines the area of the program where we have access to that name, functions, classes, and objects. There are two types of scopes:

1. **Global Scope** - The names that are available throughout our code. 
2. **Local Scope** - The names are only available within the scope.

## Non-Local Scopes

Otherwise known as Enclosing, Non-Local scope is when we have nested functions inside of a function.
We cannot change the names in the enclosing scope unless we declare them as `nonlocal`.

## Global Scope 
When we start a Python Program, we are already in the Global Scope. 

# More Big O
- We need to know what the worst case scenario is when considering Big O.
