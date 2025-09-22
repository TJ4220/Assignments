```python
patient = {} #Making a dictionary 
def insert():
  while True: # loop incase they want to add another patient 
    record = len(patient) + 1 # record number 
    first_name = input("First name: ") # asking the user to enter the first name 
    last_name = input("Last Name: ") # asking the user to enter the last name 
    month = int(input("Birth month (number): ")) # asking the user to enter the birth month as a number
    patient[record] = {"first_name": first_name, "last_name": last_name, "birth_month": month} # storing into the nested dictionary
    print("patient record:", patient) 
    more = input ("Add Another? (y/n): ").lower()
    if more == "n": # stopping in typed "n"
      break
insert() 
print(patient)
```
Output:
```python
>>> patient = {} #Making a dictionary
... def insert():
...   while True: # loop incase they want to add another patient
...     record = len(patient) + 1 # record number
...     first_name = input("First name: ") # asking the user to enter the first name
...     last_name = input("Last Name: ") # asking the user to enter the last name
...     month = int(input("Birth month (number): ")) # asking the user to enter the birth month as a number
...     patient[record] = {"first_name": first_name, "last_name": last_name, "birth_month": month} # storing into the nested dictionary
...     print("patient record:", patient)
...     more = input ("Add Another? (y/n): ").lower()
...     if more == "n": # stopping in typed "n"
...       break
... insert()
... print(patient)
...
First name: William
Last Name: Johnson
Birth month (number): 12
patient record: {1: {'first_name': 'William', 'last_name': 'Johnson', 'birth_month': 12}}
Add Another? (y/n): y
First name: Nick
Last Name: Johnson
Birth month (number): 6
patient record: {1: {'first_name': 'William', 'last_name': 'Johnson', 'birth_month': 12}, 2: {'first_name': 'Nick', 'last_name': 'Johnson', 'birth_month': 6}}
Add Another? (y/n): y
First name: Zack
Last Name: Johnson
Birth month (number): 6
patient record: {1: {'first_name': 'William', 'last_name': 'Johnson', 'birth_month': 12}, 2: {'first_name': 'Nick', 'last_name': 'Johnson', 'birth_month': 6}, 3: {'first_name': 'Zack', 'last_name': 'Johnson', 'birth_month': 6}}
Add Another? (y/n): n
{1: {'first_name': 'William', 'last_name': 'Johnson', 'birth_month': 12}, 2: {'first_name': 'Nick', 'last_name': 'Johnson', 'birth_month': 6}, 3: {'first_name': 'Zack', 'last_name': 'Johnson', 'birth_month': 6}}
```
