## Create a unit conversion program using functions

**1a.** The user selects kilometers per liter (kpl), and the response will be provided in miles per gallon (mpg). The units must be interchangeable, so the program will ask the user whether to convert from kpl to mpg or vice versa.

The program will prompt the user for input and deliver output with the appropriate units.

Additionally, the program will include input validation. For example, it will not accept letter inputs and will provide an error message to the user when invalid input is detected.

The function will also allow multiple arguments, enabling the user to convert multiple values at once.

Research and find out the conversion factor between the units.
```python

```
**1b.** How would you write a function that could take any number of unnamed arguments and print their values out in reverse order?

**1c.** What would be the result of changing a list or dictionary that was passed into a function as a parameter value? Which operations would be likely to create changes that would be visible outside the function? What steps might you take to minimize that risk?

Explain the above statements with the help of code.

**1d.** Assuming that `x = 5`, what will be the value of `x` after `funct_1()` below executes? After `funct_2()` executes?

```python
x = 5
def funct_1():
  x=3

def funct_2():
  global x
  x=2
```

## 2. Troubleshooting

Correct the following code. There might be more than one correct answers. Explain your reasoning.

```python
def my_func(a,b,**c):
  print(c)

my_func(1,2,3,4,5,6)
```

Using the following code, x should print 100 but it prints 10, why?

```python
def my_func_global():
  x = 100

global x
x = 10
my_func_global()
print(x)
```

## Challenges

Please describe the challenges you faced during the exercise.

```python
# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

```
