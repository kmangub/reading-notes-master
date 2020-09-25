# Loop Notes

- loop
- while true - loop over code
- for - for a certain number of times
- iterate - each time it loops
- condition - think of conditional statements. while (true && true) || false)
- increment - increase (possibly by 1)
- decrement - decrease (possibly by 1)

- `i++` shorthand meaning i = 1 + 1 or i += 1 var b = 42 += 4242


### Comparison Operators

- `==` - Is equal to
- `!=` - Is not equal to 
- `===` - Strict equal to 
- `!==` - strict not equal to
- `>` greater than
- `<` - less than
- `>=` - greater than or equal to
- `<=` - less than or equal to

# Logical Operators

Comparing results of more than one comparison operator.

- `&&` - Logical And
- `||` - logical or
- `!` - Logical not

### Looping

Loops checks the condition and runs a code. Then, the condition will continue to run until the return is false.

There are three common loop types:

- For - If you need to run the code a certain amount of times. 
- While - It will continue to run as long as the condition is true.
- Do while - it will run the code at least once, even if the condition is false.

Three statements:

- Initialization. variable `i` is the counter
- Condition - Condition will continue to run until it reaches a specified number
- Update - Every time the code runs, it adds a counter

#### For loop Example

```
for (var i = 0; i < 10; i++){
    console.log(i);
}
```

#### While loop example

``` 
var preference;

while(preference !== 'house'){
    var response = prompt("would you like a house or a hotel?");
}

var catLover;

while (catLover !== 'yes'){
    var catLover = prompt("do you love cats? Please say yes!")
}
```

> If the response is not  "yes", continue to run the code.

evaluates false because one false ejects from the conditional

`((500 *2 === 1000) && (false && true) && true)`