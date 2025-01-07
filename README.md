# Python Guide (WIP)

-   Version: 0.0.1
-   Author:
    -   Nathan Nellans
    -   Email: me@nathannellans.com
    -   Web:
        -   https://www.nathannellans.com
        -   https://github.com/nnellans/python-guide

> [!IMPORTANT]
> This is an advanced guide and assumes you already know the basics of Python.  Think of this more like an advanced cheat sheet.  I went through various sources, captured any notes that I felt were important, and organized them into the README file you see here.

> [!WARNING]
> This is a live document.  Some of the sections are still a work in progress.  I will be continually updating it over time.

---

## Variables

```python
# creating variables and assigning values
var_name: typeHint = "value"
```

-   `: typeHint` is optional
    -   Helpful for complex types like: `var_name: dict[str, tuple[int,int,int]]`<br />
        This would be a dict with strings for keys, and tuples containing 3 integers as values
-   `= "value"` is optional
    -   You can declare a variable without a value. However, you can't use that variable until you assign a value to it

```python
# assign the same value to multiple variables at once
var_name1 = var_name2 = var_name3 = "some value"

# assign a seperate variable to each value from an iterable (unpacking)
iterable = ["value1", "value2", "value3"]
var1, var2, var3 = iterable
```

## Data Types

### String: `str`

```python
# enclosed with single or double quotes
var_name = "this is a string"
var_name = 'this is also a string'

# multi-line strings can be created with triple quotes (single or double quotes)
var_name = """
this is a
multi-line string
"""

var_name = """\
add the slash as shown above
and the initial new line will not be included
"""

# raw strings leave everything intact, and do not support escape sequences
var_name = r"This is a raw string"  # precede the string with an r or R

# formatted strings (f-string) allow interpolation as well as many other modifications (TO-DO)
var_name = f"This is {another_var} inside a string"  # precede the string with an f or F

# convert other data types to a string with str()
var_name = str(int_var)
```

### Integer Number: `int`

```python
# un-quoted whole numbers, can be positive or negative
var_name = 234

# for better readability, you can optionally use _ as a thousands separator
var_name = 1_000_000

# convert other data types to an integer with int()
var_name = int("40")
```

### Floating-Point Number: `float`

```python
# un-quoted numbers with a decimal point, can be positive or negative
var_name = 37.33

# for better readability, you can optionally use _ as a thousands separator
var_name = 3_000.25

# convert other data types to a floating-point number with float()
var_name = float(31)
```

### Boolean: `bool`

```python
# un-quoted True or False literals, capitalization required
var_name = True
var_name = False

# convert other data types to a boolean with bool()
# any value that is empty or zero will be converted to False
# anything else will be converted to True
var_name = bool(0)
```

### List: `list`

```python
# square brackets surrounding comma-separated values
var_name = ["value", 356, True, "fourth"]

# use a single value from a list by referencing its index
list_name[3]

# convert other data types to a list with list()
# TO-DO
```

### Tuple: `tuple`

```python
# parenthesis surrounding comma-separated values
var_name = ("value", 356, True, "fourth")

# use a single value form a tuple by referencing its index
tuple_name[2]

# convert other data types to a tuple with tuple()
# TO-DO
```

- The values in a Tuple can *not* be changed, added, or removed
- The parenthesis are optional, as the comma is what actually creates the Tuple
  - The exception is creating an empty tuple, where parenthesis are required: `var_name = ()`

### Set: `set`

```python
# curly brackets surrounding comma-separated values
var_name = {"value", 356, True, "fourth"}
```

- The values in a Set can *not* be duplicated, they must be unique
- The values in a Set are *not* ordered, and therefore do not have indexes
- The values in a Set can *not* be changed. However, values can be added, or removed

### Dictionary `dict`

```python
# curly brackets surrounding key/value pairs, which are separated by commas
var_name = {
    "key1": "value",
    "key2": 356,
    "key3": True,
    "key4": "fourth"
}

# use a single value form a dictionary by referencing its index
dict_name["key2"]
```

- The keys in a Dictionary can *not* be duplicated, they must be unique

### Comparison of Collection & Mapping Types

| Type | Example | Ordered | Mutable<br />Values | Add/Remove<br />Values | Duplicates |
| --- | --- | :---: | :---: | :---: | :---: |
| `list` | `['value', 'value']` | :white_check_mark:<br />(number index) | :white_check_mark: | :white_check_mark: | :white_check_mark: |
| `tuple` | `('value', 'value')` | :white_check_mark:<br />(number index) | :red_circle:* | :red_circle:* | :white_check_mark: |
| `set` | `{'value1', 'value2'}` | :red_circle: | :red_circle: | :white_check_mark: | :red_circle:* |
| `dict` | `{'key1':'value', 'key2':'value'}` | :white_check_mark:<br />(key index) | :white_check_mark: | :white_check_mark: | keys: :red_circle:<br />values: :white_check_mark: |

`*` = defining feature

---

## Functions

```python
def function_name(param1: typeHint = defaultValue, param2: typeHint, param3) -> typeHint:
    """documentation string"""
    do stuff
    return something
```

-   For naming, use `lowercase_with_underscores` for functions and methods
-   Params are optional
    -   `: typeHint` for params are optional
    -   Default values for params are optional
-   `-> typeHint` for the function is optional
    -   `typeHint` can be `None` if the function returns nothing
-   docstring is optional

```python
def function_name(*args):
    do stuff using args[2]
```

- `*args` represents any number of positional parameters
- all values will be stored in a tuple named `args`
- `args` is convention, but any name can be used here

```python
def function_name(**kwargs):
    do stuff using kwargs["key"]
```

- `**kwargs` represents any number of named arugments (keywords)
- all keys & values will be stored in a dict named `kwargs`
- `kwargs` is convention, but any name can be used here

## TO-DO: documentation strings

## TO-DO: lambda functions

---

## Comparison Operators

```python
a == b  # equal to
a != b  # not equal to
a > b   # greater than
a >= b  # greater than or equal to
a < b   # less than
a <= b  # less than or equal to

# and, or, not
a == b and c == d  # both statements must be true
a == b or c == d   # at least one of the statements must be true
not a == b         # the statement must not be true

# comparison operators can be chained together
a < b <= c  # this is equivalent to: a < b and b <= c
```

---

## Conditional Logic

### `if` Statement

```python
if condition:
    do stuff
elif condition:
    do stuff
else:
    do stuff

# shortened, single-line if statement
if condition: do one command

# condensed if/else statement, aka ternary operator
"trueValue" if condition else "falseValue"
```

- The `elif` and `else` sections are optional

### `match` Statement

```python
match expression:
    case pattern:
        do stuff
    case patternA | patternB | patternC:
        do stuff
    case pattern if condition:
        do stuff
    case _:
        catch-all, wildcard case
```

---

## Loops

### `for` Loops

```python
# loop through a list, dict, or str
for iterator in sequence:
    do stuff using iterator

# loop 10 times
for iterator in range(10):
    do stuff using iterator

# loop through a list with index and value
for index, value in enumerate(listVariable):
    do stuff using index/value

# loop through a dict with key and value
for key, value in dictVariable.items():
    do stuff using key/value
```

### `while` Loops

```python
# continues as long as condition is true
while condition:
    do stuff
```

### Special Loop Statements

- `continue`   end the current loop iteration, start the next iteration
- `break`      end the loop altogether
- `else`       see below

```python
# 'else' statements can optionally be used in 'for' loops that use break
for iterator in sequence:
    if condition:
        break
    do stuff
# when all iterations are successful, and no break occurred
else:
    do stuff

# 'else' can optionally be used in 'while' loops that use break
while condition:
    if condition:
        break
    do stuff
# when all iterations are successful, no break occurred, and the while condition is now false
else:
    do stuff
```

---

## Imports, Modules, Packages

### Packages

-   Popular package registry: PyPI
    -   `Py`thon `P`ackage `I`ndex
    -   https://pypi.org
-   Popular package manager: pip
    -   The latest versions of Python come with pip
    -   Install a package: `pip install packageName`
        -   By default, pip fetches packages from PyPI
        -   After install, you can `import` the package into your program (see below)

### Modules (aka Libraries)

-   Python comes with many modules, but not all are loaded by default
-   Note: It is customary to place all `import` statements at the beginning of a script
-   `import random`
    -   Use a function from the module: `random.choice()`
-   `import random as alias`
    -   Makes the `random` module available under an alias
    -   Use a function from the module's alias: `alias.choice()`
-   `from random import choice, randint`
    -   Imports only specific function(s) from the `random` module into the current namespace
    -   No longer requires the use of the `random.` namespace
    -   Use the imported functions: `choice()` or `randint()`
    -   `from random import *`
        -   Imports all functions from the `random` module into the current namespace
        -   In general, [don't do this](https://docs.python.org/3/faq/programming.html#what-are-the-best-practices-for-using-import-in-a-module)
-   `from random import choice as alias`
    -   Imports a specific function from the `random` module into the current namespace, but makes it available under an alias
    -   No longer requires the use of the `random.` namespace
    -   Use the aliased function: `alias()`

---

## Classes

```python
class some_name:

    # instance method
    # used when creating a new instance/object of the class
    def __init__(self, parameter1, parameter2, parameter3=default):
        # assigning parameter values to instance variables (self._xxx)
        if not parameter1:
            raise ValueError(“parameter1 is undefined”)
        if parameter2 not in [“value1”, “value2”]:
            raise ValueError(“invalid value for parameter2”)
        self._parameter1 = parameter1
        self._parameter2 = parameter2
        self._parameter3 = parameter3
        # or, if you are using "setters"
        parameter1(parameter1)
        parameter2(parameter2)
    
    # instance method
    # used when printing an instance/object of the class
    def __str__(self):
        return f”{self._parameter1} and also {self._parameter2}”

    # custom instance method
    def yourCustomMethod(self, parameter1):
        commands
        return ...

    # “getter” for parameter1
    @property
    def parameter1(self):
        return self._parameter1

    # “setter” for parameter1
    @parameter1.setter
    def parameter1(self, parameter1):
        if parameter1 not in [“one”, “two”, “three”]:
            raise ValueError(“invalid value for parameter1”)
        self._parameter1 = parameter1

    # class variables
    class_var1 = "value"
    class_var2 = "value"

    # class methods
    @classmethod
    def method_name(cls, parameter1):
        commands
        return ...
```
