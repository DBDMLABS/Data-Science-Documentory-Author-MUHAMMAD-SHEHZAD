# 7.1: Python For Data Science
__Basic to Advance__\
Including `Data Types`, `Variable`, `Numbers and Math`, `Controll Flow`, `Functions and Comprehensions`, `Classes and objects`, `Collections`, `Exceptions`, `File Handing` , `Imports and modules`, `Pakages`, `Virtual Environments`.


- [7.1: Python For Data Science](#71-python-for-data-science)
  - [Pyhton Fundamentals](#pyhton-fundamentals)
    - [Introduction](#introduction)
    - [Data Types](#data-types)
      - [PYTHON DATA TYPES Map](#python-data-types-map)
      - [Checking data type](#checking-data-type)
      - [Data Type Conversion](#data-type-conversion)
      - [variable of data type with instance func](#variable-of-data-type-with-instance-func)
      - [variable of class with issubclass func.](#variable-of-class-with-issubclass-func)
    - [Variables](#variables)
      - [Dynamic Variables](#dynamic-variables)
      - [Parallel \& Chained Assignments or Multiple Assignment](#parallel--chained-assignments-or-multiple-assignment)
      - [Variable Naming](#variable-naming)
      - [Reassignment](#reassignment)
      - [Compund assignment](#compund-assignment)
      - [Augmented assignment](#augmented-assignment)
    - [Strings](#strings)
      - [Creating strings](#creating-strings)
      - [Indexing](#indexing)
      - [Slicing](#slicing)
      - [Length](#length)
      - [Concatenation](#concatenation)
      - [Repetition](#repetition)
      - [Remove whitespace](#remove-whitespace)
      - [Case conversion](#case-conversion)
      - [Searching](#searching)
      - [Splitting](#splitting)
      - [Joining](#joining)
      - [Validation](#validation)
      - [Formatting](#formatting)
      - [Replacing](#replacing)
      - [Reverse](#reverse)
    - [Numbers and Math in Python](#numbers-and-math-in-python)
    - [Mathematics](#mathematics)
      - [Basic Mathematical Operators](#basic-mathematical-operators)
      - [Order of Operations](#order-of-operations)
      - [Assignment Operators](#assignment-operators)
      - [Comparing Operator](#comparing-operator)
      - [Type conversion](#type-conversion)
      - [Taking Input](#taking-input)
      - [Usefull Built-in Mathematical Func.](#usefull-built-in-mathematical-func)
        - [Modular Exponention](#modular-exponention)
        - [Quotient and Remainder divmod()](#quotient-and-remainder-divmod)
        - [Python Math Module](#python-math-module)
        - [Square Root](#square-root)
        - [calculate hypotenuse](#calculate-hypotenuse)
        - [constants](#constants)
        - [Factorial](#factorial)
        - [GCD and LCM](#gcd-and-lcm)
        - [Exponential func.](#exponential-func)
        - [Natural Logrithm](#natural-logrithm)
        - [Logarithm with base](#logarithm-with-base)
        - [Base 2 Logarithm](#base-2-logarithm)
        - [Base 10 Logarithm](#base-10-logarithm)
      - [Trignometric Functions](#trignometric-functions)
        - [Angles Conversion](#angles-conversion)
        - [math.atan2](#mathatan2)
      - [Floating Point Percision](#floating-point-percision)
      - [using tolerance](#using-tolerance)
      - [Rounding and Formatting of a number](#rounding-and-formatting-of-a-number)
        - [Rounding of number](#rounding-of-number)
        - [Formating with f-string](#formating-with-f-string)
        - [Percentage formating](#percentage-formating)
        - [comma formating](#comma-formating)
        - [currency formating](#currency-formating)
      - [Decimal numb and accurate calculations](#decimal-numb-and-accurate-calculations)
      - [Fractions](#fractions)
      - [Random numbers](#random-numbers)
      - [Random choice](#random-choice)
      - [Random Sample](#random-sample)
      - [Random seed](#random-seed)
    - [Statistics](#statistics)
      - [mean](#mean)
      - [mode](#mode)
      - [median](#median)
      - [standart deviation](#standart-deviation)
      - [population and standard deviation](#population-and-standard-deviation)
      - [Bitwise Operations on Integers](#bitwise-operations-on-integers)
      - [Practice](#practice)
  - [Controll Flow](#controll-flow)
    - [Control-flow statements](#control-flow-statements)
      - [Controll Flow Structure](#controll-flow-structure)
      - [Conditional Statements](#conditional-statements)
        - [If statement](#if-statement)
        - [If else statement](#if-else-statement)
        - [If-elif-else statement](#if-elif-else-statement)
        - [Nested if statement](#nested-if-statement)
        - [Conditional Expression](#conditional-expression)
    - [LOOPS](#loops)
      - [For Loop](#for-loop)
      - [Range Function](#range-function)
      - [While Loop](#while-loop)
      - [Difference Between for and while](#difference-between-for-and-while)
      - [Break statement](#break-statement)
      - [Continue Statement](#continue-statement)
      - [pass statement](#pass-statement)
      - [Nested Loop](#nested-loop)
      - [Nested Loop pattern](#nested-loop-pattern)
      - [Input-Based Control Flow](#input-based-control-flow)
      - [match-case](#match-case)
      - [assert](#assert)
      - [Control Flow Revision](#control-flow-revision)
  - [Python Functions](#python-functions)
    - [Functions](#functions)
      - [BASIC FUNCTION](#basic-function)
      - [FUNCTION WITH PARAMETER](#function-with-parameter)
      - [MULTIPLE PARAMETERS](#multiple-parameters)
      - [RETURN](#return)
      - [DEFAULT PARAMETER](#default-parameter)
      - [KEYWORD ARGUMENT](#keyword-argument)
      - [\*args](#args)
      - [\*\*kwargs](#kwargs)
      - [LOCAL VARIABLE](#local-variable)
      - [GLOBAL VARIABLE](#global-variable)
      - [global KEYWORD](#global-keyword)
      - [LAMBDA FUNCTION](#lambda-function)
      - [RECURSION](#recursion)
      - [DOCSTRING](#docstring)
      - [TYPE HINTS](#type-hints)
      - [FUNCTION + LOOP](#function--loop)
      - [Usefull buid in functions](#usefull-buid-in-functions)
      - [FUNCTION QUICK REVISION](#function-quick-revision)
    - [COMPREHENSIONS](#comprehensions)
      - [LIST COMPREHENSION](#list-comprehension)
      - [LIST COMPREHENSION WITH EXPRESSION](#list-comprehension-with-expression)
      - [LIST COMPREHENSION WITH IF](#list-comprehension-with-if)
      - [IF-ELSE IN LIST COMPREHENSION](#if-else-in-list-comprehension)
      - [STRING + LIST COMPREHENSION](#string--list-comprehension)
      - [NESTED LIST COMPREHENSION](#nested-list-comprehension)
      - [SET COMPREHENSION](#set-comprehension)
      - [DICTIONARY COMPREHENSION](#dictionary-comprehension)
      - [DICTIONARY WITH CONDITION](#dictionary-with-condition)
      - [GENERATOR EXPRESSION](#generator-expression)
      - [NORMAL LOOP VS COMPREHENSION](#normal-loop-vs-comprehension)
      - [COMPREHENSION QUICK REVISION](#comprehension-quick-revision)
  - [Classes and Objects](#classes-and-objects)
    - [Python Classes](#python-classes)
      - [CLASS](#class)
      - [OBJECT](#object)
      - [CONSTRUCTOR __init__()](#constructor-init)
      - [self](#self)
      - [ATTRIBUTE](#attribute)
      - [METHOD](#method)
      - [CLASS VARIABLE](#class-variable)
      - [INHERITANCE](#inheritance)
      - [METHOD OVERRIDING](#method-overriding)
      - [super()](#super)
      - [CLASS METHOD](#class-method)
      - [STATIC METHOD](#static-method)
  - [Collections](#collections)
    - [Python Collections](#python-collections)
      - [Lists](#lists)
      - [Tupple](#tupple)
      - [Set](#set)
      - [Dictionary](#dictionary)
  - [Exceptions](#exceptions)
    - [Python Exceptionss](#python-exceptionss)
      - [EXCEPTION?](#exception)
      - [try](#try)
      - [except](#except)
      - [try + except](#try--except)
      - [else](#else)
      - [finally](#finally)
      - [as e](#as-e)
      - [raise](#raise)
      - [CUSTOM EXCEPTION](#custom-exception)
  - [FILE HANDLING](#file-handling)
    - [PYTHON FILE HANDLING](#python-file-handling)
      - [OPEN A FILE](#open-a-file)
      - [CLOSE A FILE](#close-a-file)
      - [READ ENTIRE FILE](#read-entire-file)
      - [READ ONE LINE](#read-one-line)
      - [READ ALL LINES](#read-all-lines)
      - [LOOP THROUGH FILE](#loop-through-file)
      - [WRITE TO FILE](#write-to-file)
      - [WRITE MULTIPLE LINES](#write-multiple-lines)
      - [writelines()](#writelines)
      - [APPEND](#append)
      - [CREATE NEW FILE](#create-new-file)
      - [FILE ENCODING](#file-encoding)
      - [FILE POSITION — tell()](#file-position--tell)
      - [FILE POSITION — seek()](#file-position--seek)
      - [FILE ERROR HANDLING](#file-error-handling)
      - [pathlib](#pathlib)
      - [BINARY FILES](#binary-files)
      - [COPY BINARY FILE](#copy-binary-file)
      - [CSV FILE](#csv-file)
      - [WRITE CSV](#write-csv)
      - [JSON FILE](#json-file)
      - [FILE MODE QUICK REVISION](#file-mode-quick-revision)
  - [IMPORTS \& MODULES](#imports--modules)
  - [PIP](#pip)
  - [VIRTUAL ENVIRONMENT](#virtual-environment)

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

#### Creating strings
```bash
name = "Python"
```
#### Indexing
```bash
print(name[0])
```
#### Slicing
```bash
print(name[1:4])
```
#### Length
```bash
print(len(name))
```
#### Concatenation
```bash
print("Hello " + name)
```
#### Repetition
```bash
print("Hi " * 3)
```
#### Remove whitespace
```bash
clean_text = text.strip()
```
#### Case conversion
```bash
print(clean_text.upper())
print(clean_text.lower())
print(clean_text.title())
```
#### Searching
```bash
print(name.find("t"))
print(clean_text.find("Programming"))
```
#### Splitting
```bash
print("abc".split(","))
```
#### Joining
```bash
print("-".join(["a", "b", "c"]))
```
#### Validation
```bash
print("123".isdigit())
```
#### Formatting
```bash
age = 20
print(f"I am {age} years old.")
```
#### Replacing
```bash
print(clean_text.replace("Python", "Java"))
```
#### Reverse
```bash
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
> `PEMDAS` or `BODMAS`\
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

##### Python Math Module
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
circumference = 2 * math.pi * r
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
print(math.lcm(4,6))
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
```bash
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

##### Angles Conversion
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

#### using tolerance
> Tolerance = the maximum acceptable difference between two values.
```bash
## rel_tol: Relative tolerance.
# Tolerance based on the size of the numbers.
print(math.isclose(1.000001, 1.000002, rel_tol=1e-5))

## abs_tol: Absolute tolerance.
# A fixed amount of difference that is acceptable.
print(math.isclose(0.0000001, 0, abs_tol=1e-6))

# Both together
a = 0.000001
b = 0.0000011

print(math.isclose(
    a,
    b,
    rel_tol=0.01,
    abs_tol=0.0000001
))
```
| Parameter | Meaning            | Example |
| --------- | ------------------ | ------- |
| `a`       | First number       | `10.0`  |
| `b`       | Second number      | `10.01` |
| `rel_tol` | Relative tolerance | `0.001` |
| `abs_tol` | Absolute tolerance | `0.01`  |

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
colors = ["red", "green", "blue"]
print(random.choice(colors))
```
#### Random Sample
```bash
numbers = [1, 2, 3, 4, 5]
print(random.sample(numbers, 2))
```
#### Random seed
```bash
random.seed(10)
print(random.randint(1, 100))
print(random.randfloat(1, 100))
```
### Statistics
    import statistics
#### mean
```bash
numbers = [10, 20, 30, 40, 50]
print(statistics.mean(numbers))
```
#### mode
```bash
print(statistics.mode(numbers))
```
#### median
```bash
print(statistics.median(numbers))
```
#### standart deviation
```bash
print(statistics.stdev(numbers))
```
#### population and standard deviation
```bash
print(statistics.pstdev(numbers))
```
#### Bitwise Operations on Integers
> Bitwise operators work on the binary representation of integers.
```bash
| Operator | Name        |
| -------- | ----------- |
| `&`      | AND         |   
| `|`      | OR          |
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

age = 25
has_id = True
print(age >= 18 and has_id) # True
```

| A     | B     | A and B |
| ----- | ----- | ------- |
| True  | True  | True    |
| True  | False | False   |
| False | True  | False   |
| False | False | False   |

> In python these values or treated as falsy values
```bash
False
None
0
0.0
""
[]
()
{}
set()
```
#### Practice 
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


## Controll Flow
> Control flow means the order in which Python executes statements in a program.

> By default, Python executes code from top to bottom:

### Control-flow statements
> allow us to:

> Make decisions\
> Repeat code\
> Skip specific statements\
> Stop loops\
> Handle different execution paths

#### Controll Flow Structure
```bash
Control Flow
│
├── Conditional Statements
│   ├── if
│   ├── if-else
│   ├── if-elif-else
│   └── Nested if
│
├── Looping Statements
│   ├── for loop
│   ├── while loop
│   └── Nested loops
│
├── Loop Control Statements
│   ├── break
│   ├── continue
│   └── pass
│
└── Other Control-Flow Features
    ├── match-case
    ├── Exception handling
    └── Conditional expressions
```
#### Conditional Statements
##### If statement
```bash
if condition:
    statement

# E.g: 
if age >= 18:
    print("You are an adult")
```
##### If else statement
```bash
if condition:
    statement_if_condition_true
else
    statement_if_conditon_false
# e.g:
if number % 2 == 0:
    print("Even number")
else:
    print("Odd number")
```
##### If-elif-else statement
```bash
if condition1:
    statement1
elif condition2:
    statement2
elif condition3:
    statement3
else
    default_statement

# e.g:
if marks >= 80:
    grade = "A+"
elif marks >= 70:
    grade = "A"
elif marks >= 60:
    grade = "B"
elif marks >= 50:
    grade = "C"
elif marks >= 40:
    grade = "D"
else:
    grade = "F"

print(grade)

# If the first condition is true, its block runs.
# The remaining conditions are skipped.
# If none is true, the else block runs.
```
##### Nested if statement
An if statement inside another if statement is called a nested if.
```bash
if condition1:
    if condition2:
        statement_true
    else:
        statement_false
else:
    statement2


# e.g: 
age = 25
has_license = True
if age >= 18:
    if has_license:
        print("You can drive")
    else:
        print("You need a license")
else:
    print("You are underage")


# Better Alternative
if age >= 18 and has_license:
    print("You can drive")
else:
    print("You cannot drive")


# Multiple conditions
age = 22
income = 50000
if age >= 18 and income >= 30000:
    print("Eligible")
else:
    print("Not eligible")

# or
day = "Friday"
if day == "Friday" or day == "Saturday":
    print("Weekend is near")


```
##### Conditional Expression
```bash
# A conditional expression is a short form of if-else.
value_if_true if condition else value_if_false
# e.g:
status = "Adult" if age >= 18 else "Minor"
```

### LOOPS
#### For Loop
A for loop repeats a block of code for each item in an iterable.

An iterable can be:
```
String
List
Tuple
Set
Dictionary
Range
File
Other iterable objects
```
```bash
# Syntax
for variable in iterable:
    statement

# e.g:
for number in [1, 2, 3, 4, 5]:
    print(number)

or
for character in "Python":
    print(character)
```
#### Range Function
A range func is commonly used with for loop
```bash
# One Argument
range(stop)

for i in range(5):
    print(i)

# Two argument
range(start, stop)

# three argument
range(start, stop, step)

# Decreasing Range
for i in range(10, 0, -1):
    print(i)

# for loop with else condition
for i in range(5):
    print(i)
else:
    print("Loop completed")
```


#### While Loop
A while loop repeats code as long as a condition is true.
```bash
while condition:
    statement

# e.g:
count = 1

while count <= 5:
    print(count)
    count += 1

# Check the condition.
# If true, execute the body.
# Update the loop variable.
# Check the condition again.
# Stop when the condition becomes false.

# Avoid infinite loop
Infinite loop never ends because its condition remains true

# e.g:

count = 1
while count <= 5:
    print(count)
# While Loop with else cond.
count = 1

while count <= 3:
    print(count)
    count += 1
else:
    print("Loop completed")
```
#### Difference Between for and while
| `for` Loop                                        | `while` Loop                        |
| ------------------------------------------------- | ----------------------------------- |
| Used to iterate over an iterable                  | Used while a condition is true      |
| Usually used when repetitions are known           | Useful when repetitions are unknown |
| Automatically moves to the next item              | Requires manual condition updates   |
| Works naturally with strings, lists, ranges, etc. | Works with any Boolean condition    |
| Less likely to become infinite                    | Can easily become infinite          |

#### Break statement
> break Statement immediately terminates the nearest loop.
```bash
for i in range(1, 10):
    if i == 5:
        break
    print(i)

# search for a numb
numbers = [4, 8, 12, 16, 20]

for number in numbers:
    if number == 12:
        print("Number found")
        break
```
#### Continue Statement
> The continue statement skips the remaining code in the current iteration and moves to the next iteration.
```bash
for i in range(1, 6):
    if i == 3:
        continue
    print(i)

# break stops the entire loop.
# continue skips only the current iteration.
```
#### pass statement
> The pass statement does nothing.

> It is used as a placeholder when Python requires a statement but you do not want to execute anything yet.

```bash
if True:
    pass

# empty func
def future_function():
    pass

# empty class
def future_function():
    pass

# in a loop
for i in range(5):
    pass 
```

#### Nested Loop
> A loop inside another loop is called a nested loop.
```bash
for i in range(1, 4):
    for j in range(1, 4):
        print(i, j)

# Multiplication table
number = 5
for i in range(1, 11):
    print(number, "x", i, "=", number * i)

# Table
for number in range(1, 6):
    print(f"\nTable of {number}")

    for i in range(1, 11):
        print(f"{number} x {i} = {number * i}")
```

#### Nested Loop pattern
```bash
# Square:
for i in range(4):
    for j in range(4):
        print("*", end=" ")
    print()


# Triangle:
for i in range(1, 6):
    for j in range(i):
        print("*", end=" ")
    print()

# break in Nested Loops
# break exits only the nearest/inner loop.
for i in range(3):
    for j in range(3):
        if j == 1:
            break


# continue in Nested Loops
# continue skips the current iteration of the nearest loop.
for i in range(3):
    for j in range(3):
        if j == 1:
            continue
        print(i, j)
```
```bash
# Looping Through Lists
fruits = ["apple", "banana", "mango"]
for fruit in fruits:
    print(fruit)
With index:
for index, fruit in enumerate(fruits):
    print(index, fruit)
# enumerate() gives both index and value.


# Looping Through Dictionaries
#  Keys:
for key in student:
    print(key)


# Values:
for value in student.values():
    print(value)

Key + value:

for key, value in student.items():
    print(key, value)


# Looping Through Tuples and Sets
for item in my_tuple:
    print(item)
for item in my_set:
    print(item)
# A set has no guaranteed iteration order.


# Looping Through Strings
# Strings can be iterated character by character.
for ch in "Python":
    print(ch)
```
Useful for:

> Counting characters\
> Finding vowels\
> Checking characters\
> Building reversed strings
#### Input-Based Control Flow
```bash
# Use input() with conditions to create interactive programs.
age = int(input("Enter age: "))

if age >= 18:
    print("Adult")
else:
    print("Minor")
#  input() returns a string, so convert it when necessary.


# Input Validation with Loops
# Use a loop to repeatedly ask until valid input is provided.
while True:
    age = int(input("Enter age: "))

    if 1 <= age <= 100:
        break

    print("Invalid age")
```
#### match-case
```bash
# Used for matching a value against different patterns.
match choice:
    case 1:
        print("Add")
    case 2:
        print("Subtract")
    case _:
        print("Invalid")
_ = default case
Available from Python 3.10+

# match-case with Multiple Values
match day:
    case "Saturday" | "Sunday":
        print("Weekend")
    case _:
        print("Weekday or invalid")
# | means OR between patterns.

# Exception Handling
# Used to control what happens when an error occurs.
try:
    number = int(input("Enter number: "))
except ValueError:
    print("Invalid input")
```
> Main keywords:
```
try → code that may cause an error
except → handles the error
else → runs if no error occurs
finally → runs regardless of error
```
#### assert
```bash
# Checks whether a condition is true.
age = 20
assert age >= 18

If false, Python raises AssertionError.

Mainly used for debugging and testing.
```
#### Control Flow Revision
```bash
# Concept---Purpose
# if---Make a decision
# elif---Check another condition
# else---Default alternative
# for---Iterate over an iterable
# while---Repeat while condition is true
# break---Exit loop
# continue---Skip current iteration
# pass---Do nothing/place-holder
# Nested loop---Loop inside another loop
# match-case---Pattern/value matching
# try-except---Handle errors
# assert---Test a condition
# enumerate()---Get index + value
```

## Python Functions
### Functions
> A function is a reusable block of code that performs a specific task.

> Instead of writing the same code again and again, we define it once and call it whenever needed.


#### BASIC FUNCTION
```bash
def greet():
    print("Hello!")

greet()

# Purpose:
# Define code once and reuse it by calling the function.
#
# Important:
# def = defines a function
# () = parameters go here
# Indentation = function body
```

#### FUNCTION WITH PARAMETER
```bash
def greet(name):
    print("Hello", name)

greet("Ali")

# Purpose:
# Pass data into a function.
#
# Important:
# name = parameter
# "Ali" = argument
```

#### MULTIPLE PARAMETERS
```bash
def add(a, b):
    return a + b

result = add(10, 20)
print(result)

# Purpose:
# Function can accept multiple inputs.
#
# Important:
# Arguments are matched to parameters by position
# unless keyword arguments are used.
```

#### RETURN
```bash
def square(x):
    return x * x

answer = square(5)
print(answer)

# Purpose:
# return sends a value back to the caller.
#
# IMPORTANT:
# return also immediately ends the function.
#
# print()  -> displays something
# return   -> gives a value back
```

#### DEFAULT PARAMETER
```bash
def greet(name="Guest"):
    print("Hello", name)

greet()
greet("Ali")

# Purpose:
# Give a parameter a default value.
#
# If no argument is provided:
# name = "Guest"
```

#### KEYWORD ARGUMENT
```bash
def student(name, age):
    print(name, age)

student(age=20, name="Ali")

# Purpose:
# Pass arguments using parameter names.
#
# Important:
# Order doesn't matter for keyword arguments.
```

#### *args
```bash
def add(*numbers):
    return sum(numbers)

print(add(10, 20, 30))

# Purpose:
# Accept any number of positional arguments.
#
# IMPORTANT:
# *args stores arguments in a TUPLE.
```

#### **kwargs
```bash
def student(**info):
    print(info)

student(name="Ali", age=20, city="Lahore")

# Purpose:
# Accept any number of keyword arguments.
#
# IMPORTANT:
# **kwargs stores arguments in a DICTIONARY.
```

#### LOCAL VARIABLE
```bash
def test():
    x = 10
    print(x)

test()

# Purpose:
# x exists only inside the function.
#
# IMPORTANT:
# Local variables normally cannot be accessed
# directly outside their function.
```

#### GLOBAL VARIABLE
```bash
x = 100

def show():
    print(x)

show()

# Purpose:
# A variable outside the function can be read inside it.
```

#### global KEYWORD
```bash
x = 10

def change():
    global x
    x = 20

change()
print(x)

# Purpose:
# Modify a global variable from inside a function.
#
# IMPORTANT:
# Avoid unnecessary global variables.
```

#### LAMBDA FUNCTION
```bash
square = lambda x: x * x

print(square(5))

# Purpose:
# Create a small anonymous function.
#
# Syntax:
# lambda arguments: expression
#
# IMPORTANT:
# Best for short/simple operations.
```

#### RECURSION
```bash
def countdown(n):

    if n == 0:       # Base case: stops recursion
        return

    print(n)
    countdown(n - 1)

countdown(5)

# Purpose:
# A function calls itself.
#
# IMPORTANT:
# Every recursive function needs a BASE CASE.
# Otherwise recursion may continue until an error occurs.
```

#### DOCSTRING
```bash
def add(a, b):
    """Return the sum of two numbers."""
    return a + b

print(add.__doc__)

# Purpose:
# Explain/document what a function does.
#
# IMPORTANT:
# Usually written as the first statement in the function.
```

#### TYPE HINTS
```bash
def add(a: int, b: int) -> int:
    return a + b

# Purpose:
# Communicate expected input and output types.
#
# IMPORTANT:
# Type hints generally do NOT enforce types automatically.
```

#### FUNCTION + LOOP
```bash
def print_numbers(numbers):

    for number in numbers:
        print(number)

print_numbers([10, 20, 30])

# Purpose:
# Functions can contain loops, conditions, etc.
```
#### Usefull buid in functions
```bash
> callable() # Checks if an object can be called as a function
> dir() # Lists attributes and methods
> globals() # Get a dictionary of the current global symbol table
> hash() # Get the hash value
> id() # Get the unique identifier
> locals() # Get a dictionary of the current local symbol table
> repr() # Get a string representation for debugging
```
#### FUNCTION QUICK REVISION
```bash
# def        -> define function
# ()         -> parameters
# argument   -> value passed to function
# return     -> send result back
# *args      -> multiple positional arguments -> tuple
# **kwargs   -> multiple keyword arguments -> dictionary
# lambda     -> small anonymous function
# recursion  -> function calls itself
# local      -> variable inside function
# global     -> variable outside function
# docstring  -> documentation
# type hint  -> indicates expected types
```


### COMPREHENSIONS
> Purpose: Create collections using compact syntax


#### LIST COMPREHENSION
```bash
numbers = [x for x in range(5)]

print(numbers)

# Output:
# [0, 1, 2, 3, 4]
#
# Purpose:
# Quickly create a LIST.
#
# Basic syntax:
# [expression for item in iterable]
```

#### LIST COMPREHENSION WITH EXPRESSION
```bash
squares = [x * x for x in range(1, 6)]

print(squares)

# Output:
# [1, 4, 9, 16, 25]
#
# Purpose:
# Transform each item before adding it to the list.
```

#### LIST COMPREHENSION WITH IF
```bash
even = [x for x in range(10) if x % 2 == 0]

print(even)

# Output:
# [0, 2, 4, 6, 8]
#
# Purpose:
# Filter values.
#
# Syntax:
# [expression for item in iterable if condition]
```

#### IF-ELSE IN LIST COMPREHENSION
```bash
result = [
    "Even" if x % 2 == 0 else "Odd"
    for x in range(5)
]

print(result)

# Output:
# ['Even', 'Odd', 'Even', 'Odd', 'Even']
#
# IMPORTANT:
# With if-else:
#
# [value_if_true if condition else value_if_false
#  for item in iterable]
```

#### STRING + LIST COMPREHENSION
```bash
word = "Python"

letters = [ch.upper() for ch in word]

print(letters)

# Output:
# ['P', 'Y', 'T', 'H', 'O', 'N']
#
# Purpose:
# Iterate through characters of a string.
```

#### NESTED LIST COMPREHENSION
```bash
matrix = [[1, 2], [3, 4], [5, 6]]

result = [x for row in matrix for x in row]

print(result)

# Output:
# [1, 2, 3, 4, 5, 6]
#
# Purpose:
# Flatten nested lists.
#
# Read it from left to right:
#
# for row in matrix
#     for x in row
#         add x
```

#### SET COMPREHENSION
```bash
numbers = [1, 2, 2, 3, 3, 4]

squares = {x * x for x in numbers}

print(squares)

# Purpose:
# Create a SET.
#
# IMPORTANT:
# Sets automatically remove duplicates.
#
# Syntax:
# {expression for item in iterable}
```

#### DICTIONARY COMPREHENSION
```bash
squares = {
    x: x * x
    for x in range(1, 6)
}

print(squares)

# Output:
# {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
#
# Purpose:
# Create a dictionary quickly.
#
# Syntax:
# {key: value for item in iterable}
```

#### DICTIONARY WITH CONDITION
```bash
even_squares = {
    x: x * x
    for x in range(10)
    if x % 2 == 0
}

print(even_squares)

# Purpose:
# Create dictionary while filtering values.
```

#### GENERATOR EXPRESSION
```bash
numbers = (x * x for x in range(5))

for number in numbers:
    print(number)

# Purpose:
# Generate values when needed.
#
# IMPORTANT:
# Generator does not create the whole collection at once.
# This can save memory for large data.
```

#### NORMAL LOOP VS COMPREHENSION
```bash
# Normal:

squares = []

for x in range(5):
    squares.append(x * x)


# Comprehension:

squares = [x * x for x in range(5)]

# Both produce the same type of result.
#
# IMPORTANT:
# Use comprehension when it makes the code clearer.
# Don't make complicated comprehensions just to save lines.
```

#### COMPREHENSION QUICK REVISION
```bash
# []             -> List comprehension
# {}             -> Set comprehension
# {key: value}   -> Dictionary comprehension
# ()             -> Generator expression
#
# if at END:
# [x for x in data if condition]
# -> FILTER
#
# if/else BEFORE for:
# [A if condition else B for x in data]
# -> CHOOSE VALUE
```
## Classes and Objects
### Python Classes
#### CLASS

Purpose: Blueprint/template for creating objects
```bash
class Student:
    pass
```

#### OBJECT

Purpose: Create an instance/object from a class
```bash
s1 = Student()
```

#### CONSTRUCTOR __init__()

Purpose: Initialize object data
> __init__() runs automatically when object is created
```bash
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

s1 = Student("Ali", 20)
```

#### self

self = current object
```bash
print(s1.name)
print(s1.age)
```

#### ATTRIBUTE

Attribute = data belonging to an object
```bash
self.name
self.age
```

#### METHOD

Method = function inside a class
```bash
class Student:
    def introduce(self):
        print("Hello")

s1 = Student()
s1.introduce()
```

#### CLASS VARIABLE

Shared class-level data
```bash
class Student:
    university = "ABC University"

print(Student.university)
```

#### INHERITANCE

Purpose: Child class reuses parent functionality
```bash
class Animal:
    def speak(self):
        print("Sound")

class Dog(Animal):
    pass

d = Dog()
d.speak()
```

#### METHOD OVERRIDING

> Child class provides its own version of a method
```bash
class Animal:
    def speak(self):
        print("Animal sound")

class Dog(Animal):
    def speak(self):
        print("Bark")

d = Dog()
d.speak()
```

#### super()

Purpose: Access parent-class functionality
```bash
class Animal:
    def __init__(self, name):
        self.name = name

class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name)     # Call parent constructor
        self.breed = breed
```

#### CLASS METHOD

Purpose: Work with class-level data
> cls = current class
```bash
class Student:
    school = "ABC"

    @classmethod
    def change_school(cls, name):
        cls.school = name
```


#### STATIC METHOD

Purpose: Utility method
> Does not need self or cls
```bash
class Math:
    @staticmethod
    def add(a, b):
        return a + b

print(Math.add(5, 3))
```

## Collections
### Python Collections
#### Lists
```bash
# Purpose: Ordered + changeable collection

numbers = [10, 20, 30]

numbers.append(40)       # Add at end
numbers.insert(1, 15)    # Add at position
numbers.remove(20)       # Remove value
numbers.pop()            # Remove last item
numbers.sort()           # Sort
numbers.reverse()        # Reverse
numbers.clear()          # Remove all items

print(numbers[0])        # Indexing


# Properties:
# Ordered      → Yes
# Mutable      → Yes
# Duplicates   → Yes
# Indexing     → Yes
```
#### Tupple
```bash
# Purpose: Ordered + unchangeable collection

numbers = (10, 20, 30)

print(numbers[0])        # Indexing

# numbers[0] = 100       # ❌ Cannot modify tuple


# Properties:
# Ordered      → Yes
# Mutable      → No
# Duplicates   → Yes
# Indexing     → Yes
```
#### Set
```bash

# Purpose: Store unique values

numbers = {10, 20, 30, 20}

print(numbers)           # Duplicate 20 is not kept as a separate element

numbers.add(40)          # Add item
numbers.remove(20)       # Remove item
numbers.discard(30)      # Remove if present


# Properties:
# Unique       → Yes
# Mutable      → Yes
# Duplicates   → No
# Indexing     → No

# operations
a = {1, 2, 3}
b = {3, 4, 5}

a | b      # Union
a & b      # Intersection
a - b      # Difference
a ^ b      # Symmetric difference
```

#### Dictionary
```bash

# Purpose: Store KEY → VALUE pairs

student = {
    "name": "Ali",
    "age": 20,
    "grade": "A"
}


# Access
print(student["name"])


# Add / Update
student["age"] = 21
student["city"] = "Multan"


# Delete
student.pop("age")

del student["city"]


# Important Methods
student.keys()           # Get keys
student.values()         # Get values
student.items()          # Get key-value pairs
student.get("name")      # Get value
student.update(...)      # Add/update data
student.pop("age")       # Remove item
student.clear()          # Empty dictionary
```

## Exceptions
### Python Exceptionss
#### EXCEPTION?
```bash
# Purpose:
# An exception is an error/problem that occurs
# while the program is running.

x = 10 / 0

#  ZeroDivisionError
```
#### try
```bash
# Purpose:
# Put risky code inside the try block.

try:
    x = 10 / 0
```
#### except
```bash
# Purpose:
# Handle the exception/error.

try:
    x = 10 / 0

except ZeroDivisionError:
    print("Cannot divide by zero")
```
#### try + except
```bash
try:
    number = int(input("Enter a number: "))
    result = 10 / number

except ValueError:
    # Runs if input cannot be converted to int
    print("Please enter a valid number")

except ZeroDivisionError:
    # Runs if user enters 0
    print("Cannot divide by zero")
```
#### else
```bash
# Purpose:
# else runs ONLY when no exception occurs.

try:
    number = int(input("Enter number: "))

except ValueError:
    print("Invalid input")

else:
    print("Valid number:", number)
```
#### finally
```bash
# Purpose:
# finally ALWAYS runs,
# whether an exception occurs or not.

try:
    print("Running program")

except Exception:
    print("Error occurred")

finally:
    print("Program finished")

#### COMPLETE EXCEPTION STRUCTURE

try:
    # Risky code
    number = int(input("Enter number: "))

except ValueError:
    # Handle error
    print("Invalid input")

else:
    # Runs if there is NO error
    print("Input is valid")

finally:
    # Always runs
    print("Finished")
```
#### as e
```bash
# Purpose:
# Store the exception information in a variable.

try:
    number = int("abc")

except ValueError as e:
    print(e)
```
#### raise
```bash
# Purpose:
# Manually create/trigger an exception.

age = -5

if age < 0:
    raise ValueError("Age cannot be negative")

#### raise

# Purpose:
# Manually create/trigger an exception.

age = -5

if age < 0:
    raise ValueError("Age cannot be negative")
```
#### CUSTOM EXCEPTION
```bash
# Purpose:
# Create your own exception type.

class MyError(Exception):
    pass

raise MyError("Something went wrong")
```



## FILE HANDLING
### PYTHON FILE HANDLING
> Purpose: Store and retrieve data permanently


#### OPEN A FILE
```bash
file = open("data.txt", "r")

# Purpose:
# Open a file for reading.
#
# Syntax:
# open(filename, mode)
```

#### CLOSE A FILE

```bash
file.close()

# Purpose:
# Close the file after using it.
#
# IMPORTANT:
# Prefer using "with open()" so Python handles closing.
```


#### READ ENTIRE FILE
```bash
with open("data.txt", "r") as file:
    data = file.read()

print(data)

# Purpose:
# Read the complete file as one string.
#
# read() -> entire content
```


#### READ ONE LINE
```bash
with open("data.txt", "r") as file:
    line = file.readline()

print(line)

# Purpose:
# Read one line at a time.
```

#### READ ALL LINES
```bash
with open("data.txt", "r") as file:
    lines = file.readlines()

print(lines)

# Purpose:
# Read all lines into a LIST.
#
# IMPORTANT:
# Newline characters (\n) may be included.
```

#### LOOP THROUGH FILE
```bash
with open("data.txt", "r") as file:

    for line in file:
        print(line)

# Purpose:
# Process a file line by line.
#
# Useful for large files because you can process
# one line at a time.
```


#### WRITE TO FILE
```bash
with open("data.txt", "w") as file:
    file.write("Hello Python")

# Purpose:
# Write data to a file.
#
# IMPORTANT:
# "w" OVERWRITES existing content.
```


#### WRITE MULTIPLE LINES
```bash
with open("data.txt", "w") as file:
    file.write("Python\n")
    file.write("Java\n")
    file.write("C++\n")

# \n = new line
```


#### writelines()
```bash
lines = [
    "Python\n",
    "Java\n",
    "C++\n"
]

with open("data.txt", "w") as file:
    file.writelines(lines)

# Purpose:
# Write multiple strings.
#
# IMPORTANT:
# writelines() does NOT automatically add \n.
```

#### APPEND
```bash
with open("data.txt", "a") as file:
    file.write("\nNew data")

# Purpose:
# Add data to the END of the file.
#
# IMPORTANT:
# "a" keeps old content.
```

#### CREATE NEW FILE
```bash
with open("new.txt", "x") as file:
    file.write("Hello")

# Purpose:
# Create a new file.
#
# IMPORTANT:
# "x" raises FileExistsError if file already exists.
```


#### FILE ENCODING
```bash
with open("data.txt", "r", encoding="utf-8") as file:
    data = file.read()

# Specify how text is encoded/decoded.
# UTF-8 allows Python to correctly understand many different characters and languages.
# UTF-8 is a common choice for text files.
```


#### FILE POSITION — tell()
```bash
with open("data.txt", "r") as file:
    print(file.tell())

# Purpose:
# Shows current position in the file.
```


#### FILE POSITION — seek()
```bash
with open("data.txt", "r") as file:

    file.seek(0)

    data = file.read()

# Purpose:
# Move to a particular position.
#
# seek(0) -> beginning of file
```


#### FILE ERROR HANDLING
```bash
try:

    with open("missing.txt", "r") as file:
        data = file.read()

except FileNotFoundError:
    print("File does not exist")

# Purpose:
# Prevent the program from crashing when the file
# cannot be found.
```


#### pathlib
```bash
from pathlib import Path

path = Path("data.txt")

print(path.exists())

# Purpose:
# Modern and convenient way to work with paths/files.


# Read:

data = path.read_text(encoding="utf-8")

# Write:

path.write_text("Hello", encoding="utf-8")
```


#### BINARY FILES
```bash
with open("image.jpg", "rb") as file:
    data = file.read()

# rb = read binary
#
# Used for:
# Images
# Audio
# Videos
# PDFs
# Other binary data
```

#### COPY BINARY FILE
```bash
with open("image.jpg", "rb") as source:
    data = source.read()

with open("copy.jpg", "wb") as destination:
    destination.write(data)

# Purpose:
# Copy binary data from one file to another.
```

#### CSV FILE
```bash
import csv

with open(
    "students.csv",
    "r",
    newline="",
    encoding="utf-8"
) as file:

    reader = csv.reader(file)

    for row in reader:
        print(row)

# Purpose:
# Work with CSV/tabular data.
#
# IMPORTANT:
# Use csv module instead of manually splitting CSV
# when proper CSV handling is needed.
```

#### WRITE CSV
```bash
import csv

with open(
    "students.csv",
    "w",
    newline="",
    encoding="utf-8"
) as file:

    writer = csv.writer(file)

    writer.writerow(["Name", "Age"])
    writer.writerow(["Ali", 20])
    writer.writerow(["Ahmed", 22])

```
#### JSON FILE
```bash
import json

data = {
    "name": "Ali",
    "age": 20
}

with open("data.json", "w", encoding="utf-8") as file:
    json.dump(data, file, indent=4)

# Purpose:
# Store structured Python data in JSON format.


# Read JSON:

with open("data.json", "r", encoding="utf-8") as file:
    data = json.load(file)

print(data)
```

#### FILE MODE QUICK REVISION
```bash
# "r"  -> READ
# "w"  -> WRITE / OVERWRITE
# "a"  -> APPEND
# "x"  -> CREATE
#
# "rb" -> READ BINARY
# "wb" -> WRITE BINARY
#
# IMPORTANT:
#
# r -> file normally must already exist
# w -> creates file if needed, but overwrites existing data
# a -> creates file if needed and adds to the end
# x -> creates only if it doesn't already exist
```


## IMPORTS & MODULES
```bash
# Module = A Python file (.py) containing reusable code.

# Import complete module
import math
print(math.sqrt(25))

# Import a specific item
from math import sqrt
print(sqrt(25))

# Import multiple items
from math import sqrt, pi

# Create an alias (short name)
import math as m
print(m.sqrt(25))

# Import with an alias
from math import sqrt as s
print(s(25))

# Own/custom module
# calculator.py
def add(a, b):
    return a + b

# main.py
import calculator
print(calculator.add(5, 3))

# Check if the file is run directly
if __name__ == "__main__":
    print("Program started")

# IMPORTANT:
# __name__ == "__main__" runs when the file is
# executed directly, not normally when imported.
```

## PIP
```bash
# pip = Python package installer

# Install a package
pip install requests

# Install a specific version
pip install requests==2.32.0

# Upgrade a package
pip install --upgrade requests

# Uninstall a package
pip uninstall requests

# Show all installed packages
pip list

# Show information about a package
pip show requests

# Check outdated packages
pip list --outdated

# Install packages from requirements.txt
pip install -r requirements.txt
```

## VIRTUAL ENVIRONMENT
```bash
# Create
python -m venv venv

# Windows activation
venv\Scripts\activate


# Exit environment
deactivate
```

