# Reading and Writing Files in Python

A file is a composed of bytes and it's used to store data. These files are translated to binary for easier computer computations.

To read files:

```
reader = open('dog_breeds.txt')
try:
    # Further file processing goes here
finally:
    reader.close()
```

Another way to read files:

```
with open('dog_breeds.txt') as reader:
    # Further file processing goes here
```

`open` takes in a second argument, which is mode. These are some of the modes:

- `r`	Open for reading (default)
- `w`	Open for writing, truncating (overwriting) the file first
- `rb` or `wb`	Open in binary mode (read/write using byte data)

Reading files methods:

- `.read(size=-1)`	This reads from the file based on the number of size bytes. If no argument is passed or None or -1 is passed, then the entire file is read.
- `.readline(size=-1)`	This reads at most size number of characters from the line. This continues to the end of the line and then wraps back around. If no argument is passed or None or -1 is passed, then the entire line (or rest of the line) is read.
- `.readlines()`	This reads the remaining lines from the file object and returns them as a list.

Writing files methods:

- `.write(string)`	This writes the string to the file.
- `.writelines(seq)`	This writes the sequence to the file. No line endings are appended to each sequence item. It’s up to you to add the appropriate line ending(s).

# Python Exceptions

A program will stop when it encounters an error; exceptions will allow programs to run.

Python comes with various built-in exceptions as well as the possibility to create self-defined exceptions.

We can raise exceptions using the keyword `raise`. Here is an example of raise:

```
x = 10
if x > 5:
    raise Exception('x should not exceed 5. The value of x was: {}'.format(x))
```

Assertions are a way to alert the user if the condition runs false using `assert`.

Try and except blocks will also make the program run and it will throw an error in the except block.