### Variable memory usage

```
var1 = 10
```

```
# Check the memory address of var1 by using the following statement
print(hex(id(var1)))
```

```
var1 = 100
# Check the memory address of var1 again
```
```python
# Write your code here

var_1 = 100
print('var _1 memory adress is: ',hex(id(var_1)))
var _1 memory adress is:  0x7ffeadcc8008
```

You should see two distinct addresses for var1. Explain why there are two different addresses and what happened to the first one.

```
var2 = 100
# Write your print statement (var _1 memory adress is:  0x7ffebb858008)
# Check the memory address of var2. Did the Python interpreter assign a new memory address or reuse the existing one?
```

```
# Write your code here
var_1 = 100
var_2 = 100
print('var _1 memory adress is: ',hex(id(var_1)))
print('var _2 memory adress is: ',hex(id(var_2)))
```
It reused the existing one

### Memory map

```
str1 = "Hello"
str2 = "World"
```

```
# Find out the memory addresses of each character in str1 and str2.
# The following is the example
```

```
print(hex(id(str1[0])), hex(id(str1[1])))  # where 0 is the first index and 1 is the second index
# Use the same method as described above to find the addresses of additional characters and complete the table below.
```

| Address in hexadecimal | Char |
| ---------------------- | ---- |
| #                      |      |
| #                      |      |
| #                      |      |
| #                      |      |
| #                      |      |
| #                      |      |
| #                      |      |
| #                      |      |
| #                      |      |
| #                      |      |

### Problem-solving

Let the variable `x` be `dog` and the variable `y` be `cat`. Write the values returned by the following operations: **Try solving without writing in Python.**

- x + y
- "the " + x + " chases the " + y
- x * 4

Write your answer here

If `x = 50`. Use an assignment statement to increment the value of `x` by 1.

```
# Write your code here
```

### Troubleshooting

Please troubleshoot the following issue **without using Python**, and explain your reasoning.

a. `hello = "hello"`
b. `_var = 100`
c. `!var_1 = 200`
d. `print = "print me"`
e. `False = 0`



Write your answer here
