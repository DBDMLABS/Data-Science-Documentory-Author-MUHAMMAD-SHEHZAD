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
### Assignment 
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

### Control-flow statements allow us to:

> Make decisions\
> Repeat code\
> Skip specific statements\
> Stop loops\
> Handle different execution paths

### Controll Flow Structure
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

#### LOOPS
##### For Loop
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
##### Range Function
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


##### While Loop
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
##### Difference Between for and while
| `for` Loop                                        | `while` Loop                        |
| ------------------------------------------------- | ----------------------------------- |
| Used to iterate over an iterable                  | Used while a condition is true      |
| Usually used when repetitions are known           | Useful when repetitions are unknown |
| Automatically moves to the next item              | Requires manual condition updates   |
| Works naturally with strings, lists, ranges, etc. | Works with any Boolean condition    |
| Less likely to become infinite                    | Can easily become infinite          |

##### Break statement
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
##### Continue Statement
> The continue statement skips the remaining code in the current iteration and moves to the next iteration.
```bash
for i in range(1, 6):
    if i == 3:
        continue
    print(i)

# break stops the entire loop.
# continue skips only the current iteration.
```
##### pass statement
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

##### Nested Loop
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

##### Nested Loop pattern
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
##### Input-Based Control Flow
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
##### match-case
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
##### assert
```bash
# Checks whether a condition is true.
age = 20
assert age >= 18

If false, Python raises AssertionError.

Mainly used for debugging and testing.
```
#### Control Flow Revision
```bash
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
