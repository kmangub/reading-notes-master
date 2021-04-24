# Dunder Methods

Source: https://dbader.org/blog/python-dunder-methods

Dunder methods are predefined methods to enrich our classes.

`__len__` returns a length for the class. Here's an example

```
class LenSupport:
    def __len__(self):
        return 42

>>> obj = LenSupport()
>>> len(obj)
42
```

`__init__` is the method that lets us build constructors inside of a class. 

```
class Account:
    """A simple account class"""

    def __init__(self, owner, amount=0):
        """
        This is the constructor that lets us create
        objects from this class
        """
        self.owner = owner
        self.amount = amount
        self._transactions = []
```

`__str__` formats the string neatly for the enduser.

`__repr__` is the official string representation of an object and the goal of it is to be ambiguous.

```
class Account:
    # ... (see above)

    def __repr__(self):
        return 'Account({!r}, {!r})'.format(self.owner, self.amount)

    def __str__(self):
        return 'Account of {} with starting amount: {}'.format(
            self.owner, self.amount)
```

`__getitem__` iterates through the object.

`__eq__` means equal.
`__lt__` means less than.

```
from functools import total_ordering

@total_ordering
class Account:
    # ... (see above)

    def __eq__(self, other):
        return self.balance == other.balance

    def __lt__(self, other):
        return self.balance < other.balance
```

and now we can compare other objects:

```
>>> acc2 > acc
True

>>> acc2 < acc
False

>>> acc == acc2
False
```

`__add__` merges two objects together.


`__call__` makes the object callable.

`__enter__` and `__exit__` are context managers.

# Iterators

Source: https://dbader.org/blog/python-iterators
- Iterators provide a sequence interface to Python objects that’s memory efficient and considered Pythonic. Behold the beauty of the for-in loop!
- To support iteration an object needs to implement the iterator protocol by providing the __iter__ and __next__ dunder methods.
- Class-based iterators are only one way to write iterable objects in Python. Also consider generators and generator expressions.

# Generators

Generators use yield statements instead of return. Local variables and the execution state of the generator function are only stashed away temporarily and not thrown out completely. Generators start raising StopIteration exceptions after control flow leaves the generator function by any means other than a yield statement.