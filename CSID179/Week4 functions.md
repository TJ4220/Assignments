## Create a unit conversion program using functions

**1a.** The user selects kilometers per liter (kpl), and the response will be provided in miles per gallon (mpg). The units must be interchangeable, so the program will ask the user whether to convert from kpl to mpg or vice versa.

The program will prompt the user for input and deliver output with the appropriate units.

Additionally, the program will include input validation. For example, it will not accept letter inputs and will provide an error message to the user when invalid input is detected.

The function will also allow multiple arguments, enabling the user to convert multiple values at once.

Research and find out the conversion factor between the units.
```python
Miles_Per_KM = 1 / 1.609344
Liters_per_Gallon = 3.785411784
KPL_to_MPG_First = Miles_Per_KM * Liters_per_Gallon
MPG_to_KPL_First = 1 / KPL_to_MPG_First
print(KPL_to_MPG_First)
print(MPG_to_KPL_First)
def KPL_to_MPG(*values):
  return [v* KPL_to_MPG_First for v in values]
def MPG_to_KPL(*values):
  return [v * MPG_to_KPL_First for v in values]
print("Choose either KPL to MPG or MPG to KPL")
print("1) KPL to MPG")
print("2) MPG to KPL")
choice = input("Enter 1 or 2: ")
if choice == "1":
  raw = input("Enter Values in KPL, seperate by commas: ")
  values = [float(v) for v in raw.split(",")]
  print(KPL_to_MPG(*values))
elif choice == "2":
  raw = input("Enter values in MPG, seperate by commas: ")
  values = [float(v) for v in raw.split(",")]
  print(MPG_to_KPL(*values))
else:
  print("invalid choice. Please run again and enter 1 or 2.")
```
**1b.** How would you write a function that could take any number of unnamed arguments and print their values out in reverse order?
```python
def reverse_args(*args):
  for value in args[::-1]:
    print(value)
```
**1c.** What would be the result of changing a list or dictionary that was passed into a function as a parameter value? Which operations would be likely to create changes that would be visible outside the function? What steps might you take to minimize that risk?

Answer 1c) If i pass a list or dictionary into a function an change it with operations like setting a dictionary key that change happens to the original object outside the function also. If i just reassigned the parameters to a new list or dictionary the original wouldnt change. To avoid this you could make a copy first and make your changes to the copy rather than the original instead. 
Explain the above statements with the help of code.
```python
def safe_change(my_list):
    copy_list = my_list.copy()  
    copy_list.append(200)
    return copy_list
nums = [1, 2, 3]
new_nums = safe_change(nums)
print("Original:", nums)       
print("Modified copy:", new_nums) 
```
**1d.** Assuming that `x = 5`, what will be the value of `x` after `funct_1()` below executes? After `funct_2()` executes?

```python
x = 5
def funct_1():
  x=3
# ANSWER x=5
def funct_2():
  global x
  x=2
# ANSWER x=2
```

## 2. Troubleshooting

Correct the following code. There might be more than one correct answers. Explain your reasoning.

```python
def my_func(a,b,**c):
  print(c)

my_func(1,2,3,4,5,6)
```
ANSWER **C is Keyword argument but its giving a positional argument, to correct it just remove one "*"
Using the following code, x should print 100 but it prints 10, why?

```python
def my_func_global():
  x = 100

global x
x = 10
my_func_global()
print(x)
```
ANSWER its printing 10 because of assignment in the function, to correct it you need to have x set to global inside of the function. 
## Challenges

Please describe the challenges you faced during the exercise.

```python
# All of my problems were with 1a, first i inproperly labled my first KPL_to_MPG an it wasnt working because of naming issues, then i had a } instead of ] in my return and i kept over looking it when i would go back to find it. most of my issues were either not [TAB]'ing correctly or just not labling each line properly, I struggle at naming and i dont like using notes mostly because i forget to add them into my lines.

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

```
