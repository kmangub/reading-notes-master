# The Call Stack and Debugging

A call stack is a tool for the interpreter for a website that keeps track of its place in a script that calls several functions, what functions are being run, and what functions are called within the function.

When the script calls for a function, the interpreters calls it to the stack and performs that function, adding more to the stack where the calls are reached and taking it off once the function is done. 

> If the stack takes up more than it can handle, it will result in a **stack overflow**.

<!-- Exampole taken from https://developer.mozilla.org/en-US/docs/Glossary/Call_stack -->

## Example

```
function greeting() {
   // [1] Some codes here
   sayHi();
   // [2] Some codes here
}
function sayHi() {
   return "Hi!";
}

// Invoke the `greeting` function
greeting();

// [3] Some codes here
```

1. It goes through the code until it reaches where the function is invoked.

2. Greeting gets put in the stack list.

3. It goes through each line of code inside of the greeting function.

4. Goes to the `sayHi()` invocation.

5. Adds `sayHi()` to the call stack.

6. Goes through all the lines of code in the `sayHi()` function.

7. Goes back to the `sayHi()` (line 3).

8. `sayHi()` is finished, so it gets taken out of the stack list.

9. Once it goes through all the lines of code in the `greeting()` function, it goes back to the executing line (line 11).

10. `greeting()` gets deleted from the call stack.

The call stack starts empty and whenever we invoke the function, it gets added to the list. Once the function exhausted all lines of code, it gets removed from the call stack.

# Error Messages and Debugging 

Error messages are something that developers will expect when building their own application. The more times you run into errors and solve them, the more experience you get and saves you time.

- `Console.log()` is your best bet to figure out what is wrong.

- **Try and Catch** is a method that we learned when working with our project.

- Utilize tools such as **quokka** and **eslint** to aid with finding errors in your code.

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)