# python-guide

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

# else statements can optionally be used by for loops that use break
for iterator in sequence:
    if condition:
        break
    do stuff
else:
    do stuff after all iterations were successful and no break occurred

# else can optionally be used by while loops that use break
while condition:
    if condition:
        break
    do stuff
else:
    do stuff after all iterations were successful, no break occurred, and the while condition is now false
```
