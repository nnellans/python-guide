# python-guide

## Data Types

### String: `str`

```python
# enclosed with single or double quotes
var_name = "this is a string"
var_name = 'this is also a string'

# multi-line strings can be created with triple quotes (single or double quotes)
var_name = """this is a
multi-line string"""

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

- The values in a List can be of different types, if you wish
- The values in a List can be duplicated
- The values in a List are ordered, using a zero-based index
- The values in a List can be changed, added, or removed

### Tuple: `tuple`

```python
# parenthesis surrounding comma-separated values
var_name = ("value", 356, True, "fourth")

# use a single value form a tuple by referencing its index
tuple_name[2]

# convert other data types to a tuple with tuple()
# TO-DO
```

- The values in a Tuple can be of different types, if you wish
- The values in a Tuple can be duplicated
- The values in a Tuple are ordered, using a zero-based index
- The values in a Tuple can not be changed, added, or removed
- The parenthesis are optional, as it is the comma that actually creates the Tuple
  - The exception is creating an empty tuple, where parenthesis are required: `var_name = ()`

### Set

```python
# curly brackets surrounding comma-separated values
var_name = {"value", 356, True, "fourth"}
```

- The values in a Set can be of different types, if you wish
- The values in a Set can not be duplicated, they must be unique
- The values in a Set are not ordered, they do not have indexes
- The values in a Set can not be changed. However, values can be added, or removed

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

- The keys in a Dictionary can not be duplicated, they must be unique
- The values in a Dictionary can be of different types, if you wish
- The values in a Dictionary are ordered, using a key-based index
- The key/value pairs in a Dictonary can be changed, added, or removed

### Comparison of Collection & Mapping Types

| Type | Example | Ordered | Mutable<br />Values | Add/Remove<br />Values | Duplicates |
| --- | --- | :---: | :---: | :---: | :---: |
| `list` | `['value', 'value', 'value']` | :white_check_mark: (number index) | :white_check_mark: | :white_check_mark: | :white_check_mark: |
| `tuple` | `('value', 'value', 'value')` | :white_check_mark: (number index) | :red_circle: | :red_circle: | :white_check_mark: |
| `set` | `{'value1', 'value2', 'value3'}` | :red_circle: | :red_circle: | :white_check_mark: | :red_circle: |
| `dict` | `{'key1':'value', 'key2':'value'}` | :white_check_mark: (key index) | :white_check_mark: | :white_check_mark: | keys: :red_circle:, values: :white_check_mark: |

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
    -   No longer requires the use of the `random.` namespace
    -   How to use the imported functions: `choice()` or `randint()`
    -   `from random import *`
        -   Imports all functions from the `random` module into the current namespace
-   `from random import choice as alias`
    -   Imports a specific function from the `random` module into the current namespace, but makes it available under an alias
    -   No longer requires the use of the `random.` namespace
    -   How to use the aliased function: `alias()`
