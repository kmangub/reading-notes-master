# Classes and Objects
Objects contain variables and functions and are stored all in one place. Classes are templates that create objects.

Example:

```
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

myobjectx.function()
```

When we run the code above, we get this as the output:

```
Out[1]: 'blah'

In [1]: 
```

or for `print(myobjectx.variable)` will yeild

```
blah

In [1]: 
```

We can create multiple objects with the same class, but they must have different variables. So,
```
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()
myobjecty = MyClass()

myobjecty.variable = "yackity"

# Then print out both values
print(myobjectx.variable)
print(myobjecty.variable)
```
Will give us

```
blah
yackity

In [1]: 
```
as our output.

> Accessing functions inside of an object is similar to JavaScript's dot notation.

# Thinking Recursively
Thinking recursively means that we are able to break a problem down into small pieces, small enough for us to solve individually. For an iterative algorithm:

```
houses = ["Eric's house", "Kenny's house", "Kyle's house", "Stan's house"]

def deliver_presents_iteratively():
    for house in houses:
        print("Delivering presents to", house)
```
Breaking this algorithm to chunks will give us this:

```
houses = ["Eric's house", "Kenny's house", "Kyle's house", "Stan's house"]

# Each function call represents an elf doing his work 
def deliver_presents_recursively(houses):
    # Worker elf doing his work
    if len(houses) == 1:
        house = houses[0]
        print("Delivering presents to", house)

    # Manager elf doing his work
    else:
        mid = len(houses) // 2
        first_half = houses[:mid]
        second_half = houses[mid:]

        # Divides his work among two elves
        deliver_presents_recursively(first_half)
        deliver_presents_recursively(second_half)
```


# Pytest Fixtures and Coverage

When writing out tests, we write out tests to cover different paths, which is called parameterized tests. **Fixtures** are tests that contain the same objects that are relative to our tests. Here is an example of accessing tests using fixtures:

```
@pytest.fixture
def simple_file():
   return StringIO('\n'.join(['abc', 'def', 'ghi', 'jkl']))
```

Coverage is the idea that tests need to be run so that it covers all code paths. We can use a package called `pytest-cov` and invoke using the `--cov` option with an argument. From here, we can use an HTML file to display the output. Finally, we create more tests so that we can bump up our coverage to 100%.