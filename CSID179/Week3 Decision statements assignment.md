1) I did the research to find ASCII and resulted in finding this line to run
```python
fir i in range (32, 127): # ASCII range for printable character
pring(f"{chr(i)}:{i}")
```
1) This was the resulting answer I recived when input into python
```Python
 : 32
!: 33
": 34
#: 35
$: 36
%: 37
&: 38
': 39
(: 40
): 41
*: 42
+: 43
,: 44
-: 45
.: 46
/: 47
0: 48
1: 49
2: 50
3: 51
4: 52
5: 53
6: 54
7: 55
8: 56
9: 57
:: 58
;: 59
<: 60
=: 61
>: 62
?: 63
@: 64
A: 65
B: 66
C: 67
D: 68
E: 69
F: 70
G: 71
H: 72
I: 73
J: 74
K: 75
L: 76
M: 77
N: 78
O: 79
P: 80
Q: 81
R: 82
S: 83
T: 84
U: 85
V: 86
W: 87
X: 88
Y: 89
Z: 90
[: 91
\: 92
]: 93
^: 94
_: 95
`: 96
a: 97
b: 98
c: 99
d: 100
e: 101
f: 102
g: 103
h: 104
i: 105
j: 106
k: 107
l: 108
m: 109
n: 110
o: 111
p: 112
q: 113
r: 114
s: 115
t: 116
u: 117
v: 118
w: 119
x: 120
y: 121
z: 122
{: 123
|: 124
}: 125
~: 126
```

2) Logical operations (I was a little confused as to what you were asking me to do so I just made my own examples)

Using and 
```python
print(7 > 4 and 45 < 50) 
print(7 > 10 and 45 < 50) 
print(7 > 4 and 45 > 50) 
```
Using or
```python
print(7 > 15 or 15 < 20) 
print(7 > 15 or 15 > 20)
```
Using not
```python
print(not(10 > 5)) 
print(not(10 < 5)) 
```
2 Answer) When using `and` its treated as just a true or false nothing else if both are correct than it is true but if even one is incorrect it becomes false. When using `or` it is just asking if one of the statements are true if one is than it is true. When using `not` its reverse if it is correct than it is false but if it is false it is true.

3) Bitwise logical operators (and, or, not, xor)
AND (`&`)

It compairs each bit of two numbers resulting in 1 only if both of the bits are 1 if not it is 0
```python
x= 0b1101
y= 0b1011
result = x & y
print("AND result (decimal):",result)
print("AND result (binary):", bin(result))
```
OR(`I`)

It compairs each bit resulting in 1 if either bit is 1
```python
x = 0b1101
y = 0b1011
result = x | y
print("OR result (decimal):", result)
print("OR result (binary):", bin(result))
```
NOT(`~`) 

It flops everything if it is a 1 it becomes a 0 and if it is a 0 it becomes a 1, and in python ~ gives a negative number.  
```python
x = 0b1101
result = ~x
print("NOT result (decimal):", result)
print("NOT result (binary):", bin(result))
```
XOR(`^`)

It compairs each bit 1 if the bits are different and 0 if they are the same 
```python
x = 0b1101
y = 0b1011
result = x ^ y
print("XOR result (decimal):", result)
print("XOR result (binary):", bin(result))
```
4) Decision statments finding the largest number 
```python
number1 = int(input("Enter the first number: "))
number2 = int(input("Enter the second number: "))
if number1 > number2:
  Larger_number = number1
else:
  Larger_number = number2
print("the larger number is:", Larger_number)
```
Nested conditional statments 
```python
x = 15
if x > 10:
    if x == 20:
        print("nested: x == 20")
    elif x == 15:
        print("nested: x == 15")
    else:
        print("nested: else")
```
5) Problem solving

A)
```python
num1 = int(input("Enter first integer: "))
num2 = int(input("Enter second integer: "))
num3 = int(input("Enter third integer: "))
if num1 >= num2 and num1 >= num3:
    largest = num1
```
B)
```python

# Approach 1
#######################
num = int(input("Enter an integer: "))
if num % 2 == 0:
    print("Even")
else:
    print("Odd")
    
# Approach 2
#######################
num = int(input("Enter an integer: "))
if (num & 1) == 0:
    print("Even")
else:
    print("Odd")
    
# Approach 3
#######################
num = int(input("Enter an integer: "))
if (num / 2) == int(num / 2):
    print("Even")
else:
    print("Odd")
```
C)
```python
# Ask the the user to input a percentage score as an integer
percentage = int(input("Enter the percentage score: "))

# Calculate the grade based on the percentage
if percentage > 90:
    print("Grade: A - Work of genuinely superior quality.")
elif 80 <= percentage <= 89:
    print("Grade: B - Passing performance falls approximately in the upper distribution of passing grades.")
elif 71 <= percentage <= 79:
    print("Grade: C - Passing performance falls approximately in the center of the distribution of all passing grades.")
elif 65 <= percentage <= 70:
    print("Grade: D - Passing performance falls approximately in the lower distribution of passing grades.")
else:
    print("Grade: F - Failing performance that does not satisfy the basic requirements of the course.")
```

D)
```python
# Ask user for inputs
A_input = input("Enter value for A (True/False): ").strip().capitalize()
B_input = input("Enter value for B (True/False): ").strip().capitalize()

A = True if A_input == 'True' else False
B = True if B_input == 'True' else False

# Calculate expressions
A_and_B = A and B
A_or_B = A or B
Not_A = not A

# Display the truth table
print("\nTruth Table:")
print("A\tB\tA and B\tA or B\tNot A")
print(f"{A}\t{B}\t{A_and_B}\t{A_or_B}\t{Not_A}")
```
I think of a truth table as a punnett square like what we learned in biology class for genes you have two inputs and their are 4 possable outcomes.

E)
```python
# Ask the user to input an integer
num = int(input("Enter an integer: "))

# Use bitwise AND with 1 to check the last bit
if (num & 1) == 0:
    print(f"{num} is Even.")
else:
    print(f"{num} is Odd.")
```

6) Revising code
```python
name = input("What's your name? ")
time = int(input("What time is it (in Military time)? "))

# looking to see if it's morning
if time < 1200:
    print("Hi " + name + ", good morning!")
# Checking it's afternoon, you would use `elif` here because if you are only using `if` you can get different outcomes 
elif time < 1800:
    print("Hi " + name + ", good afternoon!")
# Or else it's evening
else:
    print("Hi " + name + ", good evening!")
print("Good Bye")
```
7)

My answer with out plugging into python : I belive it would be 1 

After python it came out to 
```python
one
two
```
