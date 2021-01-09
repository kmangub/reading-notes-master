# List Comprehensions

List comprehensions is a way to create lists using brackets. It always returns a results list.

The old way is shown below:
```
new_list = []
for i in old_list:
    if filter(i):
        new_list.append(expressions(i))
```

List comprehension is shown here:

```
new_list = [expression(i) for i in old_list if filter(i)]
```

Here is the syntax for list comprehension:

```
[ expression for item in list if conditional ]
```

Example: 
```
x = [i for i in range(10)]
print x

# This will give the output:
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

We can also parse files:

```
# Then create the filter by using list comprehension:

fh = open("test.txt", "r")

result = [i for i in fh if "line3" in i]

print result

# This will give the output [‘this is line3
‘]
```

This is how it's done in functions:

```
def double(x):
  return x*2

[double(x) for x in range(10)]

print double

# [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]

```
We can also add conditionals:
```
[double(x) for x in range(10) if x%2==0]
# [0, 4, 8, 12, 16]
```

Lastly, we can add more arguments:

```
[x+y for x in [10,30,50] for y in [20,40,60]]
[30, 50, 70, 50, 70, 90, 70, 90, 110]
```

# Dunder Methods

Dunder methods, or double underscore methods, let us emulate behavior of built-in methods.

- `__len__` offers length support to our class

- `__getitem__` allows us to use python's slicing method `obj[start:stop]`

- `__init__` is used as an object initializer and where we create our constructor for our class

- `__str__` is the informal string representation of the object

- `__repr__` is the string representation of the object. 

- `__reversed__` iterates in the reversed order

- `__eq__` is equals

- `__lt__` is less than

- `__add__` is add

- `__call__` makes it so that we are able to call objects

- `__enter__` is the start of the context manager

- `__exit__` is the end of the context manager

# Statistics and Probability
Probability is the chance of something happening. We calculate probability by considering all possible events, or outcome of interest. For example, flipping a coin gives us two events, head or tails.

The bell curve is a visualization of how likely an event will occur where the x-axis is the event and the y-axis is the probability. 

Three sigma, or the 68-95-99 rule is the expression of how our observations fall from within the average. The z-score tells us how many standard deviations away from the mean. 