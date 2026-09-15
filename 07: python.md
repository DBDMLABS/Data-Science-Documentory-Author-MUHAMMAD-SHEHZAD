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




















---
## Numbers and Math in Python
### Mathematics
#### Basic Mathematical Operators
| Operator | Meaning        |   Example |     Result |
| -------- | -------------- | --------: | ---------: |
| `+`      | Addition       |  `10 + 3` |       `13` |
| `-`      | Subtraction    |  `10 - 3` |        `7` |
| `*`      | Multiplication |  `10 * 3` |       `30` |
| `/`      | Division       |  `10 / 3` | `3.333...` |
| `//`     | Floor division | `10 // 3` |        `3` |
| `%`      | Remainder      |  `10 % 3` |        `1` |
| `**`     | Power          | `10 ** 3` |     `1000` |

> Floor division gives the result rounded down toward negative infinity.\
> e.g: floor of `-2.5` is `-3` and floor of `+2.5` is `+2`

#### Order of Operations
> `PEMDAS` or `DOSMAS`
> Parentheses → Powers → Multiplication/Division → Addition/Subtraction

#### Assignment Operators
| Operator | Meaning        |   Example |     Result |
| -------- | -------------- | --------: | ---------: |
| `=`      | Assignment     |     `x=2` |         `2` |
| `+=`     | add and assign |    `x+=2` |       `x+2` |
| `-=`     | subtract and assign|`x-=2` |       `x-2` |
| `*=`     | multiply and assign|`x*=2` |       `x*2` |
| `/=`     | divide and assign|  `x/=2` |       `x/2` |
| `//=`    |floor divide and assign|`x//=2`|   `x//2` |
| `%=`     | modoulus and assign | `x%=2` |     `x%2` |
| `**=`    | Power and assign| `x**=2`  |  `x power 2`|

#### Comparing Operator
| Operator | Meaning        |
| -------- | -------------- |
|`==`      |   Equal to      |
|`!=`      |   Not equal     |
|`>`       |     greater than|
|`<`       |      less than  |
|`>=`      | greater than or equal to|
|`<=`      | less than or equal to|

#### Type conversion
```bash
print(int(32.5)) #32
print(float(3))  #3.0

or
x =23
float(x)        #23.0

print(complex(3))   # 3+0j
print(complex(x))   #23+0j

```

#### Taking Input
```bash
age = input("Enter your age")
print(type(age))

# add 2 number taking input
x = int(input("Enter Your age"))
y = int(input("Enter your DS experience age))
sum = x+y

# calculate average
average = (x+y)/2
```
#### Usefull Built-in Mathematical Func.

| Function | Purpose    |
| -------- | ---------- |
|`abs()`   | absolute value |
|`round()` | round a number|
|`pow()`   | power of number|
|`divmod()`  | Return Quotient and remainder|
|`min()`     | find minimum|
|`max()`     | find maximum|
|`sum()`     | adding numbers|

> absolute is mod `|-4| = 4`\
> rounding to negative decimals\
> python uses"round half to even"\
> This is called bankers rounding\
> `pow(2,3)` means `2 power 3 = 2*2*2 =8`
```bash
print(round(2.5))  # 2
print(round(3.5))  # 4

# Modular Exponention
print(pow(2,10,1000)) 
# 2 powe 10 mod 1000 =1024 mod 1000=24

# Quotient and Remainder divmod()
result(17,5)
print(result)  # (3,2)
```

#### python Math Module
```bash
import math

# Square Root
print(math.squrt(16)) # 4
print(math.squrt(2))  # 1.4142...
# calculate hypotenuse
a=2 
b=3
c= math.squr(a**2 + b**2)

# constants
print(math.pi)
print(math.e)

circle area = math.pi * r**2
circumference = 2 * math.pi * r**2

# Ceiling and floor
Ceiling Returns smallest int >= the number
print(math.ceil(3.2)) # 4
print(math.ceil(-3.2)) # -3

floor returns greatest int <= the number
print(math.floor(3.2)) # 3
print(math.floor(-3.2)) # -4

# Factorial
factorial of non negative no. `n` is:
n! = n*(n-1)(n-2).........
print(math.factorial(5)) #120

# GCD and LCM
greatest common divisor and least common multiple
print(math.gcd(38,78))
print(math.lcm(4.6))

# Exponential func.
print(math.exp(2))

# Natural Logrithm
print(log(math.e))
print(math.log(100))

# Logarithm with base
print(math.log(100,10))

# Base 2 Logarithm
print(math.log2(1000))

# Base 10 Logarithm
print(math.log10(1000))
```

#### Trignometric Functions
| Function | Purpose    |
| -------- | ---------- |
|`math.sin()`| sine|
|`math.cos()`| cosine|
|`math.tan()`| tangent|
|`math.asin()`| inverse of sine|
|`math.acos()`| inverse of cosine|
|`math.atan()`| inverse of tangent|

#### Python math module par 2
```bash
# convert degree to radian
angle_degree = 90
angle_radians=
math.radians(angle_degree)
print(angle_radians) #1.57
angle_radians = math.pi/2

# Examples
math.radians(90)
math.degrees(90)
math.sin(30)

# math.atan2
# atan2(y,x) 
calculate angle of a point from + x-axis  while correctly handling quadrents.
x=1
y=1
angle = math.atan2(y,x)

p13
