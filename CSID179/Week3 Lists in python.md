1. Lists

A. (I struggled with this here is the link from reddit I used to help find the answer https://www.reddit.com/r/learnpython/wiki/faq/)
```python
my_list = list(range(100))
print("Data type of my_list:", type(my_list))
my_list.append(100)
print("After append:", my_list[-5:])  
my_list.remove(50)
print("After remove 50:", my_list[45:55]) 
my_list.reverse()
print("After reverse, first 5 elements:", my_list[:5])
my_list.sort()
print("First 5 elements after sort:", my_list[:5])
```
B. I used slicing
```python
my_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
last_three = my_list[-3:]
my_list = my_list[:-3]
new_list = last_three + my_list
print(new_list)
```
C. breaking this down [1,2] is a list and *3 is repeats the entire list 3 times so it would look kinda like [1,2][1,2],[1,2], and len is the length of the list and their are 3 elements the 1 the 2 and finally the 3 so i would say the answer is 3.

When input into python i get 3 
```python
>>> print(len([[1, 2]] * 3))
3
```
D.
```python
# Create the list with duplicates
my_list_ten = [10, 40, 80, 50, 40, 10, 50, 10, 40, 10]
# Generate the list of memory addresses of each item
my_list_ten_mem = [id(item) for item in my_list_ten]
# Print the original list
print("my_list_ten:", my_list_ten)
# Print the list of memory addresses
print("my_list_ten_mem:", my_list_ten_mem)
```
```python
#memory adress:
my_list_ten_mem: [140718718940360, 140718718941320, 140718718942600, 140718718941640, 140718718941320, 140718718940360, 140718718941640, 140718718940360, 140718718941320, 140718718940360]
```
E. Delete the list above ^
```python
del my_list_ten_mem
```
F. It generated the same memory adresses and kept gettign NameError see below:
```python
#Generating new list & new memory adress and comparing
my_new_list = [10, 40, 80, 50, 40, 10, 50, 10, 40, 10]
my_new_list_mem = [id(item) for item in my_new_list]
print("Memory addresses in my_new_list:", my_new_list_mem)
print("Corresponding addresses in my_list_ten_mem:", my_list_ten_mem)
for i in range(len(my_new_list)):
    same = my_new_list_mem[i] == my_list_ten_mem[i]
    print(f"Item {my_new_list[i]} at position {i}: Same address? {same}")
```
```python
Memory addresses in my_new_list: [140718718940360, 140718718941320, 140718718942600, 140718718941640, 140718718941320, 140718718940360, 140718718941640, 140718718940360, 140718718941320, 140718718940360]
Traceback (most recent call last):
  File "<python-input-129>", line 5, in <module>
    print("Corresponding addresses in my_list_ten_mem:", my_list_ten_mem)
                                                         ^^^^^^^^^^^^^^^
NameError: name 'my_list_ten_mem' is not defined. Did you mean: 'my_list_ten'?
```
G.
```python
import copy
x = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
y = copy.deepcopy(x)
y[0][0] = 999
print("x:", x)
print("y:", y)
```
H. Yes because you can have lists that contain more than one value for each iteration
I.
```python
sentence = "To be, or not to be, this is the question"
space_count = sum([1 for ch in sentence if ch == ' '])
print("Number of spaces in the sentence:", space_count)
```
J.
1.
```python
# Return the number of times s appears in the list
list.count(x)
```
2.
```python
# Sort the items of the list in place (the arguments can be used for sort customization
list.sort(*, key=None, reverse=False)
```
3.
```python
# Add an item to the end of the list
list.append(x)
```
4.
```python
# Reverse the elements of the list in place.
list.reverse()
```
5.
```python
# Remove the first item from the list whose value is equal to x
list.remove(x)
```
