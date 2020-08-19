# Error Handling and Debugging

Debugging is a way where we can use tools to hunt for errors, where the common place to find errors are, and how to handle them. The stack is where the JavaScript interpreter reads one code at a time and it "stacks" new functions on top of the one that is currently being processed.

### Errors

There are seven types of errors:
- Error or generic error - all other errors are based off of this error
- SyntaxError - Syntax hasn't been followed
- ReferenceError - Tried to reference a variable that hasn't been declared or not within scope
- TypeError - an unexpected data type that can't be coerced
- RangeError - numbers not in range
- URIError (Uniform Resource Indentifier Error) - incorrect use of `encodeURI()`, `decodeURI`, or characters not escaped correctly.
- EvalError - incorrect use of the `eval()` function


