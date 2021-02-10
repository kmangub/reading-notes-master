# Python Regular Expression 

Regular Expressions, often shortened as regex, are a sequence of characters used to check whether a pattern exists in a given text (string) or not.

To start, we need to `import re`, which is a python library that supports regex.

`match()` returns a match object if it matches the pattern. `r` means raw string literal.

```
pattern = r"Cookie"
sequence = "Cookie"
if re.match(pattern, sequence):
    print("Match!")
else: print("Not a match!")

# output: Match!
```

- `search()` scans through the string where it produces a match.

- `group()` returns the string matched by re.

- `.` matches single character except new line.

- `^` matches the start of the string.

- `$` matches end of the string

- `[abc]` - Matches a or b or c.
- `[a-zA-Z0-9]` - Matches any letter from (a to z) or (A to Z) or (0 to 9).

- `\` - escape character

- `\w` matches single letter, digit, underscore. 

- `\W` matches character not part of `\w` 

- `\s` matches single whitespace such as space, newline, tab, or return.

- `\S` matches character not part of `\s`

- `\d` - Lowercase d. Matches decimal digit 0-9.
- `\D` - Uppercase d. Matches any character that is not a decimal digit.

- `\t` - Lowercase t. Matches tab.
- `\n` - Lowercase n. Matches newline.
- `\r` - Lowercase r. Matches return.
- `\A` - Uppercase a. Matches only at the start of the string. Works across multiple lines as well.
- `\Z` - Uppercase z. Matches only at the end of the string.
- `\b` matches the beginning or the end of the word.

- Repitition:
    - `+` Checks if the preceding character appears one or more times starting from that position.

    - `*` Checks if the preceding character appears zero or more times starting from that position.

    - `?` Checks if the preceding character appears exactly zero or one time starting from that position.  

    - `{x}` - Repeat exactly x number of times.
    - `{x,}` - Repeat at least x times or more.
    - `{x, y}` - Repeat at least x times but no more than y times.

# Shutil

The shutil model has file operations like copying and archiving.

- `copyfile()` copies the contents of the source to the destination and raises error if it doesn't have permission

- `copy()` interprets the output name like the Unix command line tool cp. If the named destination refers to a directory instead of a file, a new file is created in the directory using the base name of the source.

- `copy2()` works like copy(), but includes the access and modification times in the metadata copied to the new file.

- `copymode()` copies the permissions from one file to another

- `copystat()` copies other metadata about the file use 

- `copytree()` recurses through the source directory tree, copying files to the destination

- `verbose_copy()` prints the names of files as they are copied then uses `copy2()`, the default copy function, to make the copies.

- `rmtree()` removes a directory and its contents

- `move()` moves a file or directory from one place to another

- `which()` scans a search path looking for a named file

- `get_archive_formats()` returns a sequence of names and descriptions for formats supported on the current system

- `make_archive()` to create a new archive file

- `get_unpack_formats()` shutil maintains a registry of formats that can be unpacked on the current system

- `unpack_archive()` Extracts the archive

- `disk_usage()` returns a tuple with the total space, the amount currently being used, and the amount remaining free
