# python-guide

---

Data Types

### String `str`

-   To use, enclose your text with double-quotes or single-quotes, for example:
    - `"This is a string"`
    - `'This is also a string'`
-   You can also use triple quotes to enclose your string (either double-quotes or single-quotes)
    -   This is most often used to store multi-line strings
    -   This is commonly used when defining docstrings for functions, methods, etc.
    -   ```python
        """this is an example
        of a multi-line string"""
        ```
-   Raw Strings are exactly like they sound, and do not support escape sequences at all
    -   To use raw strings, precede the string with an `r` or `R`, for example:
        -   `r"This is a raw string \n where escape sequences are \\ ignored"`
-   Formatted Strings, or f-strings, let you interpolate values into your strings, as well as other modifications
    -   To use f-strings, precede the string with an `f` or `F`, for example:
        -   `f"This is a {varName1} formatted {varName2} string"`
    -   f-strings support many different types of string manipulations (TO-DO)
-   Convert other data types to a string with `str()`

### Integer `int`

-   Whole numbers with no decimal places. Can be positive or negative
-   To use, just type the unquoted number, for example:
    -   `varName = 250`
    -   `varName = -30`
-   Optionally, to make a number more readable, you can use underscores as a thousands separate, for example:
    -   `1_000_000`
-   Convert other data types to an integer with `int()`

### Floating-Point Numbers `float`

-   Numbers that have a decimal place. Can be positive or negative.
-   To use, just type the unquoted number, for example:
    -   `varName = 7.9`
    -   `varName = -34.8`
-   Optionally, to make a number more readable, you can use underscores as a thousands separator, for example:
    -   `3_000.25`
-   Convert other data types to a floating-point number with `float()`

### Boolean `bool`

-   A value that represents either true (1) or false (0)
-   To use, just type the unquoted literal, capitalization required, for example:
    -   `varName = True`
    -   `varName = False`
-   Convert other data types to a boolean with `bool()`
    -   Anything that is empty or zero will be converted to `False`
    -   Everything else will be converted to `True`

### List `list`

### Tuple

### Set

### Dictionary `dict`

---

Functions

```python
def function_name(param1: typeHint = value1, param2: typeHint, param3) -> typeHint:
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

# TO-DO: documentation strings

# TO-DO: lambda functions

---

`if` Statement

```python
if condition:
    do stuff
elif condition:
    do stuff
else:
    do stuff
```

- The `elif` and `else` sections are optional

`match` Statement

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

`for` Loops

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

`while` Loops

```python
# continues as long as condition is true
while condition:
    do stuff
```

Special Loop Statements

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

Packages

-   Popular package registry: PyPI
    -   `Py`thon `P`ackage `I`ndex
    -   https://pypi.org
-   Popular package manager: pip
    -   The latest versions of Python will also come with pip
    -   Install a package: `pip install packageName`
        -   By default, pip fetches packages from PyPI
        -   After install, you can `import` the package into your program (see below)

Modules (aka Libraries)

-   Python comes with many modules, but not all are loaded by default
-   Note: It is customary to place all `import` statements at the beginning of a script
-   `import random`
    -   How to use a function from the module: `random.choice()`
-   `import random as alias`
    -   Makes the `random` module available under an alias
    -   How to use a function from the module's alias: `alias.choice()`
-   `from random import choice, randint`
    -   Imports only specific function(s) from the `random` module into the current namespace
    -   How to use functions without the `random.` namespace: `choice()` or `randint()`
    -   `from random import *`
        -   Imports all functions from the `random` module into the current namespace
-   `from random import choice as alias`
    -   Imports only specific function(s) from the `random` module into the current namespace, but make them available under an alias
    -   How to use the aliased functions without the `random.` namespace: `somethingElse()`
