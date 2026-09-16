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




### Variables
#### Dynamic Variables
> Python variables do not have a fixed type. The same variable can refer to different types of objects.

    x = 10
    x = "Python"
    x = 3.14
#### Parallel & Chained Assignments or Multiple Assignment
```bash
x, y = 10, 20 # Assign multiple values
a = b = c = 0 # Give same value to multiple variables
```
#### Variable Naming
```bash
# use `letters, underscore, numbers` Don't use number in the begning of var name.
# Start with a letter or _
# No spaces or special characters
# Cannot use Python keywords
# Python is case-sensitive
```
#### Reassignment
```bash
x = 10
x = 70
print(x) # 70 - last assignment will be considered
```

#### Compund assignment
```bash
x += 5    # x = x + 5
x -= 5    # x = x - 5
x *= 5    # x = x * 5
x /= 5    # x = x / 5
x //= 5   # x = x // 5
x %= 5    # x = x % 5
x **= 2   # x = x ** 2
print(x)  # 0 - last assignment will be considered
```
#### Augmented assignment
```bash
counter += 1
numbers += [4, 5]
permissions |= write
```
---


### Strings

```bash
# Creating strings
name = "Python"

# Indexing
print(name[0])

# Slicing
print(name[1:4])

# Length
print(len(name))

# Concatenation
print("Hello " + name)

# Repetition
print("Hi " * 3)

# Remove whitespace
clean_text = text.strip()

# Case conversion
print(clean_text.upper())
print(clean_text.lower())
print(clean_text.title())

# Searching
print(name.find("t"))
print(clean_text.find("Programming"))

# Splitting
print("a,b,c".split(","))

# Joining
print("-".join(["a", "b", "c"]))

# Validation
print("123".isdigit())

# Formatting
age = 20
print(f"I am {age} years old.")

# Replacing
print(clean_text.replace("Python", "Java"))

# Reverse
print(name[::-1])
```





---
### Numbers and Math in Python
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
```
##### calculate average
```bash
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
```
##### Modular Exponention
```bash
print(pow(2,10,1000)) 
# 2 powe 10 mod 1000 =1024 mod 1000=24
```

##### Quotient and Remainder divmod()
```bash
result(17,5)
print(result)  # (3,2)
```

#### python Math Module
```bash
import math
```
##### Square Root
```bash
print(math.squrt(16)) # 4
print(math.squrt(2))  # 1.4142...
# Square Root of negative number
print(cmath.sqrt(-1))
```
```bash
| Module  | Purpose                                    |
| ------- | ------------------------------------------ |
| `math`  | Mathematical functions for real numbers    |
| `cmath` | Mathematical functions for complex numbers |
```

##### calculate hypotenuse
```bash
a=2 
b=3
c= math.squr(a**2 + b**2)
```
##### constants
```bash
print(math.pi)
print(math.e)

circle area = math.pi * r**2
circumference = 2 * math.pi * r**2
```
##### Ceiling and floor
```bash
Ceiling Returns smallest int >= the number
print(math.ceil(3.2)) # 4
print(math.ceil(-3.2)) # -3

floor returns greatest int <= the number
print(math.floor(3.2)) # 3
print(math.floor(-3.2)) # -4
```
##### Factorial
```bash
factorial of non negative no. `n` is:
n! = n*(n-1)(n-2).........
print(math.factorial(5)) #120
```
##### GCD and LCM
```bash
greatest common divisor and least common multiple
print(math.gcd(38,78))
print(math.lcm(4.6))
```
##### Exponential func.
```bash
print(math.exp(2))
```
##### Natural Logrithm
```bash
print(log(math.e))
print(math.log(100))
```
##### Logarithm with base
```bash
print(math.log(100,10))
```
##### Base 2 Logarithm
print(math.log2(1000))
```
##### Base 10 Logarithm
```bash
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
```
##### math.atan2
```bash
# atan2(y,x) 
calculate angle of a point from + x-axis  while correctly handling quadrents.
x=1
y=1
angle = math.atan2(y,x)
```
#### Floating Point Percision
> Floating-point numbers are stored using binary representation. Some decimal values cannot be represented exactly.

```bash
print(0.1+0.2) # 0.300000000000
# We expect 0.3 but computer stores approximation

# Comparing float safely
a= 0.1 + 0.2
if a==0.3:
    print("Equal")

# Use math.isclose():
if math.inclose(a,0.3):
    print("apprximately equal")
```

# using tolerance
```bash
## rel_tol: Relative tolerance.
print(math.isclose(1.000001, 1.000002, rel_tol=1e-5))
## abs_tol: Absolute tolerance.
print(math.isclose(0.0000001, 0, abs_tol=1e-6))
```

#### Rounding and Formatting of a number
##### Rounding of number
```bash
number = 3.14153487
print(round(number,2)) # 2 decimals 3.14
```
##### Formating with f-string
```bash
price = 123.456789
print(f"{price:.2f}") # 123.45
# .2f means formating till 2 digits
```
##### Percentage formating
```bash
score = 0.875
print(f"{score:.2%}") # 87.50%
```
##### comma formating
```bash
population = 123456789
print(f"{population:,}") # 123,456,789
```
##### currency formating
```bash
price = 1250.5
print(f"${price:,.2f}") #$1,250.50
```
#### Decimal numb and accurate calculations
    from decimal import Decimal
```bash
price = Decimal("19.99")
quantity = Decimal("3")
total = price * quantity # 59.97

# Why we use 19.99 instead of "19.99"
# Because 19.99 as a float has already been approximated.
```
#### Fractions
```bash
from fractions import Fraction

a = Fraction(1, 3)
b = Fraction(1, 6)

print(a + b)
```
#### Random numbers
```bash
import random

print(random.randint(1, 10))
print(random.random()) # print(random.random())
print(random.uniform(1, 10)) # random float b/w 1 and 10
```
#### Random choice
```bash
# Random choice
colors = ["red", "green", "blue"]
print(random.choice(colors))

# Random Sample
numbers = [1, 2, 3, 4, 5]
print(random.sample(numbers, 2))

# Random seed
random.seed(10)
print(random.randint(1, 100))
print(random.randint(1, 100))
```
### Statistics
    import statistics
#### Basic statistics
```bash
# mean
numbers = [10, 20, 30, 40, 50]
print(statistics.mean(numbers))

# mode
print(statistics.mode(numbers))

# median
print(statistics.median(numbers))

# standart deviation
print(statistics.stdev(numbers))

# population and standard deviation
print(statistics.pstdev(numbers))
```
### Bitwise Operations on Integers
> Bitwise operators work on the binary representation of integers.
```bash
| Operator | Name        |
| -------- | ----------- |
| `&`      | AND         |   
| `|`       | OR         |
| `^`      | XOR         |  
| `~`      | NOT         |  
| `<<`     | Left shift  |  
| `>>`     | Right shift | 
```
```bash
# Example
a = 5
b = 3

print(a & b)
print(a | b)
print(a ^ b)
```
#### Assignment 
> solve following by taking input using input command
```bash
# Calculate are of rectangle
# calculate area of circle
# calculate circumference

# calculate interest rate
Formula: simple_interest = (principal * rate * time) / 100

# Calculate compound interst
amount = principal * (1 + rate / (100 * n)) ** (n * time)
compound_interest = amount - principal

# Calculate distance/hypotenuse

# celcius to farenheit
fahrenheit = (9 / 5) * celsius + 32
print(f"Fahrenheit = {fahrenheit:.2f}")

# calulate VMI
bmi = weight / height ** 2

# reverse a number using while loop
reverse = 0
while number > 0:
    digit = number % 10
    reverse = reverse * 10 + digit
    number //= 10
print("Reversed number:", reverse)



# check prime number
number = int(input("Enter a number: "))

if number < 2:
    print("Not prime")
else:
    is_prime = True

    for i in range(2, math.isqrt(number) + 1):
        if number % i == 0:
            is_prime = False
            break

    if is_prime:
        print("Prime")
    else:
        print("Not prime")

# Mixing string and numbers
age = 20
# print("Age: " + 20) # type error
# print("Age: " + 20)
or
print("Age:", 20)
or
print("Age: " + str(20))
```

