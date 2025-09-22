## 1. Creating and accessing dictionary

**1a)** Create dictionary of your choice of keys and values. Create dictionary size of 10 elements.
```python
Dogs = {
101: "Siberian Husky",
102: "Australian Shepard",
103: "Dachshound",
104: "Pug",
105: "Golden Retriever",
106: "German Shepard",
107: "Poodle",
108: "Great Dane",
109: "Pitbull",
110: "Labrador Retriever"
}
print(Dogs)
print("size of dictionary:", len(Dogs))
```

**1b.** Take inputs from a user and add them in a dictionary called `my_user_dict`

Here is the example of an user input:

SSN: 111-222-3333

Name: Steve Hawkins

The code continue to take user input and provide an option at the end of the user input; "Do you want to continue (Y/N)"

Identify how many keys you need to create a dictionary. ANSWER (If the dictionary is for one user you need 2 keys the ssn and the name)

**Restrictions: Do not use functions and/or exceptions in this exercise**

```python
my_user_dict = {}
while True:
    ssn = input("Enter SSN: ")
    name = input("Enter Name: ")
    my_user_dict[ssn] = name
    choice = input("Do you want to continue (Y/N): ")
    if choice.upper() == "N":
        break
print("User dictionary:", my_user_dict)
```

**Converting tuples into a dictionary**

```
# List of tuples where each tuple represents a key-value pair

a = [("a", 1), ("b", 2), ("c", 3)]

# Convert the list of tuples into a dictionary

res = dict(a)

print(res)
```

```
{'a': 1, 'b': 2, 'c': 3}
```

**1c.** Based on the given tuple, create a code which checks for valid key & value pairs, and check for key duplication.

The code should provide assistance to a user to correct the error. For key duplication, ask user to change the key

**Restrictions: Do not use functions and/or exceptions in this exercise**

```
[('Name', 'Sarah Connor'),
 ('Date of birth', '1 Jan 1980'),
 ('Address', '1000 Black Mountain Drive', 92126),
 ('Name', 'Jim Hawkins')]
```
Answer
```python
data = [
    ('Name', 'Sarah Connor'),
    ('Date of birth', '1 Jan 1980'),
    ('Address', '1000 Black Mountain Drive', 92126),
    ('Name', 'Jim Hawkins')
]
my_user_dict = {}
for pair in data:
    if len(pair) != 2:
        print(f"Invalid pair found: {pair}")
        new_value = input("Please enter a correct value: ")
        key = pair[0]
        value = new_value
    else:
        key, value = pair
  if key in my_user_dict:
        print(f"Duplicate key found: {key}")
        new_key = input(f"Please enter a new key for {value}: ")
        my_user_dict[new_key] = value
    else:
        my_user_dict[key] = value
print("Final dictionary:", my_user_dict)
```

**1d.** Convert the following list into a dictionary. Automate the process by using the loop.

**Restrictions: Do not use functions and/or exceptions in this exercise**
```python
data = [("a", 1), ("b", 2), ("c", 3)]
my_dict = {}  
for pair in data:        
    key = pair[0]        
    value = pair[1]       
    my_dict[key] = value 
print("Resulting dictionary:", my_dict)
```

**1e.** Use the following text and count the number of words using dictionary. Remember The or the counts as 2.

**The tiger (Panthera tigris) is a large cat and a member of the genus Panthera native to Asia. It has a powerful, muscular body with a large head and paws, a long tail and orange fur with black, mostly vertical stripes. It is traditionally classified into nine recent subspecies, though some recognise only two subspecies, mainland Asian tigers and the island tigers of the Sunda Islands.**
```python
text = ("The tiger (Panthera tigris) is a large cat and a member of the genus Panthera native to Asia. "
        "It has a powerful, muscular body with a large head and paws, a long tail and orange fur with black, mostly vertical stripes. "
        "It is traditionally classified into nine recent subspecies, though some recognise only two subspecies, mainland Asian tigers and the island tigers of the Sunda Islands.")


words = text.split()
word_count = {}
for word in words:
    word = word.strip(".,()")
    if word in word_count:
        word_count[word] += 1
    else:
        word_count[word] = 1
print("Word counts:", word_count)
```
## 2. Troubleshooting

```
d_orig = {123:"Coconut"}
d_copy = d_orig
print(d_orig)
print(d_copy)
```

```
{123: 'Coconut'}
{123: 'Coconut'}
```

**2a.** Change the content of `d_copy` and make sure the content does not affect the `d_orig` dictionary. Verify using the code.

```python
d_orig = {123: "Coconut"}
d_copy = d_orig.copy()   
d_copy[123] = "Pineapple"
print("Original dictionary:", d_orig)
print("Copy dictionary:", d_copy)
```
Output:
```python
Original dictionary: {123: 'Coconut'}
Copy dictionary: {123: 'Pineapple'}
```
**2b.** If it changes the content of the original dictionary, then propose how can you solve this problem.

```python
d_orig = {123: "Coconut"}
d_copy = d_orig.copy()   
d_copy[123] = "Pineapple"
print("Original dictionary:", d_orig)
print("Copy dictionary:", d_copy)
```
Output
```python
Original dictionary: {123: 'Coconut'}
Copy dictionary: {123: 'Pineapple'}
```

**2c.** Write a code that generates the following error and explain why there is such an error.

```
TypeError: unhashable type: 'list'
```

```Python
d = {[1, 2, 3]: "numbers"}
Traceback (most recent call last):
  File "<python-input-50>", line 1, in <module>
    d = {[1, 2, 3]: "numbers"}
TypeError: unhashable type: 'list'
```

## Challenges

Please describe the challenges you faced during the exercise.

```python
# I was confused as to why d_copy = d+orig caused changes in both.

# I didnt properly indent [if key my_user_dict] and it was outside my loop 

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

# _________________________________________________________________________________________________

```
