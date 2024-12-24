# python-guide

---

Data Types



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

```python
continue  # end the current loop iteration, start the next iteration
break     # end the loop altogether
else      # see below

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
