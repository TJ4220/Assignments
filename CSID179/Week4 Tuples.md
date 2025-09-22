## 1. Exercising tuples

**1a)** Take five inputs from an user and save it in a tuple called `my_tuple`

```python
my_tuple = tuple(input(f"Enter value {i+1}: ") for i in range(5))
print("Your tuple is:", my_tuple)
```

**1b.** How do you assign a single element in a tuple?

Tuples cannot be changed once created so you cannot change or add a new element, so for a single element it would be:
```python
my_tuple = (1,)
print(my_tuple)
print(type(my_tuple))
```

**1c.** `my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)` Count the repeated integers and print the result on the console.

```python
from collections import Counter
my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)
counts = Counter(my_tuple)
print(counts)
```
```python
Counter({2: 4, 3: 4, 1: 3, 4: 2, 5: 1})
```

**1d.** `my_tuple = my_tuple + my_tuple`

Proof that `my_tuple` in part c is different than the `my_tuple` in part d.

```python
tuple_c = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)
tuple_d = tuple_c + tuple_c
print(id(tuple_c))   
print(id(tuple_d))
print(tuple_c == tuple_d)  
print(tuple_c is tuple_d)  
```

**1e.** Explain why the following operations aren’t legal for the tuple. Answer without using the Python.

x.append(1) is not legal because it is a list method not for tuples.x[1]= "hello" is wrong because tuples do not allow you to change anything after it has been created it cannot be reassigned. Tuples are concrete non changable
and same thing for del x[2]. you cannot change anything once a tuple has been made. 
```
x = (1,2,3,4)
x.append(1)
x[1] = "hello"
del x[2]
```

## 2. Packing and unpacking tuples

Python permits tuples to appear on the left side of an assignment operator, in which case variables in the tuple receive the corresponding values from the tuple on the right side of the assignment operator. Here’s a simple example:

```
(one, two, three, four) =  (1, 2, 3, 4)
```

**2a.** What is the data type of each variable?

2a answer) all four varables (one,two,three,four) are of type int

**2b.** Python has an extended unpacking feature, allowing an element marked with * to absorb any number of elements not matching the other elements. For example,

```
x = (1, 2, 3, 4)
a, b, *c = x
a, b, c
```

```
(1, 2, [3, 4])
```
2b answer) 
```
a is int(1)
b is int(2)
c is a list containing [3,4]
```
**2c.** What will be the result of `a, *b, c = x`?

```python
a = 1
b = [2,3]
c = 4
print(a, b, c)
```
```python
1 [2, 3] 4
```
## 3. Memory management

```
my_x = [100,200,300,400]
my_y = (200,300,400,500)
```

Discuss how memory addresses are assigned to each index of the list and the tuple. Pay attention to new addresses & re-used addresses.
```python
print("my_x[0]:", my_x[0], "address:", id(my_x[0]))
print("my_y[0]:", my_y[0], "address:", id(my_y[0]))
print("my_x[1]:", my_x[1], "address:", id(my_x[1]))
print("my_y[1]:", my_y[1], "address:", id(my_y[1]))
```
```
| Index | my_x | my_y | (im guessing you didnt want both my_x and my_x you wanted my_x and my_ y) 
| ----- | ---- | ---- |
| 0     | 100  | 200  |  100 & 200 can be reused because they are small
| 1     | 200  | 300  |  200 can be the same object in both of the structures because small integers (-5,256) are stored in the memory once and then reused to save memory.
| 2     | 300  | 400  |  larger ints of 256 + are new objects so in this case they are 300+ 
| 3     | 400  | 500  |  larger ints of 256 + are new objects so in this case they are 400+
```
## Challenges

Please describe the challenges you faced during the exercise.

```python
# 1d. I kept getting confused between the first tuple and the second. 
  My first time through I didnt lable the tuples and got confused as to when I was meant to.
  I would enter print(id(my_tuple)) and then again on a didderent line and was getting the same id adress. it took me way too long it find my mistake  
# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

```

**End of exercise**
