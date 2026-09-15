# Python For Data Science
## Pyhton Fundamentals
### Introduction
> Created by Guido Van Russam, Released in 1991.

### Data Types
> Mutable vs Immutable Data Types

Mutable: Can be changed after creation: `list`, `set`, `dict`, `bytearray`

Immutable: Cannot be changed after creation: `int`, `float`, `complex`, `bool`, `str`, `tuple`, `range`, `frozenset`, `bytes`, `None`


#### PYTHON DATA TYPES Map
```bash
PYTHON DATA TYPES
│
├── NUMERIC
│   ├── int
│   ├── float
│   └── complex
│
├── BOOLEAN
│   └── bool
│
├── TEXT
│   └── str
│
├── SEQUENCE
│   ├── list
│   ├── tuple
│   └── range
│
├── SET
│   ├── set
│   └── frozenset
│
├── MAPPING
│   └── dict
│
├── BINARY
│   ├── bytes
│   ├── bytearray
│   └── memoryview
│
└── NONE
    └── NoneType
```

#### Checking data type
    print(type(`value or variable name`))
```bash
print(type(10))                    # int
print(type(3.14))                  # float
print(type(2 + 3j))                #complex

print(type(True))                  # bool
print(type(False))                 # bool

print(type('Python'))              # string
# Use single cotation for single line string
# Use double cotation for single line string
# Use triple single cotation for multi line string

print(type([1, 2, 3]))             # list
print(type((1, 2, 3)))             # tupple
print(type(range(5)))              # range

print(type({1, 2, 3}))            # set
print(type(frozenset({1, 2, 3}))) # frozenset

print(type({"name": "Shehzad", "age": 20})) # dictionary

print(type(b"Python"))            # byte
print(type(bytearray(5)))         # bytearray
print(type(memoryview(bytes(5)))) # memoryview
# Use b before string for bytes
# Use bytearray() for byte array
# Use memoryview() for memory view

print(type(None))                 # None
```

#### Data Type Conversion
```bash
int("10")       # str → int
float("10.5")   # str → float
str(100)        # int → str
float(10)       # int → float
int(10.5)       # float → int
list("ABC")     # str → list
tuple([1, 2])   # list → tuple
set([1, 2, 2])  # list → set
bool(1)         # → True

# To view the results, use print command like print(type(int("10"))) or print(float("10.5")) etc.
```
#### variable of data type with instance func

```bash
x = 10
isinstance(x, int)   # True
```
#### variable of class with issubclass func.
```bash
issubclass(int, object) # True - everything inherits from object
```
---
