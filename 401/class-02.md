# In Tests we Trust

- Writing out the code for tests is the ideal first step for applications that are test driven. 

- Test names should be very specific about what the expected out is going to be. 

- The file name for the test should be the same as the name of the module. 

Here is an example of what the files should look like:

```
mymodule/
 — module.py
 — another_folder/
 — — another_module.py
tests/
 — test_module.py
 — another_folder/
 — — test_another_module.py
 ```

The structure is produced using the Arrange, Act, and Assert, or AAA.

- Arrange: you need to organize the data needed to execute that piece of code (input);

- Act: here you will execute the code being tested (exercise the behaviour);

- Assert: after executing the code, you will check if the result (output) is the same as you were expecting.

The cycle:

1. Write the test and make it fail.

1. Write the feature and make it pass.

1. Refactor the code.

# Recursion 

**Recursion** is where the function calls itself directly or indirectly. It is a very efficient tool for programmers to use for coding problems. We set base conditions to stop the recursions.

> If the base case is not reached or not defined, then the stack overflow might occurr.

There are two types of recursion: 
- **Direct Recursion** is where a function calls itself inside of the function.

- **Indirect Recursion** is where a function calls another function inside of itself.

```
// An example of direct recursion
void directRecFun()
{
    // Some code....

    directRecFun();

    // Some code...
}

// An example of indirect recursion
void indirectRecFun1()
{
    // Some code...

    indirectRecFun2();

    // Some code...
}
void indirectRecFun2()
{
    // Some code...

    indirectRecFun1();

    // Some code...
}

```

The difference between recursive and iterative programming is that recursive has greater space and time requirements while iterative doesn't. Recursive code also looks more simple than iterative code. 





