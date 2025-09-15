1. While loop
```python
# List of numbers to test
numbers = [7, 12, 19, 27]
for n0 in numbers:
    print(f"\nStarting with n0 = {n0}")
    steps = 0
    temp = n0
    while temp != 1:
        print(temp, end=" -> ")
        if temp % 2 == 0:
            temp = temp // 2
        else:
            temp = 3 * temp + 1
        steps += 1
    print("1")
    print(f"Total steps: {steps}")
```
B.
```python
count = 0  # Initialize a counter
while True:
    print(f"Loop iteration {count}")
    count += 1
       # Break the loop after 10 iterations
    if count >= 10:
        break
print("Loop ended after 10 iterations.")
```
C.
```python
while True:
    # Ask the user to input two integers
    num1 = int(input("Enter the first integer: "))
    num2 = int(input("Enter the second integer: "))
    # Ask for operation choice
    print("Choose an operation:")
    print("1. Addition (+)")
    print("2. Subtraction (-)")
    print("3. Multiplication (*)")
    print("4. Division (/)")
    choice = input("Enter your choice (+, -, *, /): ")
    # Perform the operation
    if choice == '+':
        result = num1 + num2
        print(f"{num1} + {num2} = {result}")
    elif choice == '-':
        result = num1 - num2
        print(f"{num1} - {num2} = {result}")
    elif choice == '*':
        result = num1 * num2
        print(f"{num1} * {num2} = {result}")
    elif choice == '/':
        if num2 != 0:
            result = num1 / num2
            print(f"{num1} / {num2} = {result}")
        else:
            print("Error: Cannot divide by zero.")
    else:
        print("Invalid choice!")
    # Ask if they want to continue
    continue_choice = input("Do you want to continue? (Y/N): ")
    if continue_choice.lower() != 'y':
        print("Have a good day.")
        break
```
2. For Loops
```python
import string
text = "Hello my name is Tj, and my dogs name is Ash."
text = text.lower()
counts = {}
# Loop through each character in the text
for ch in text:
    if ch in string.ascii_lowercase:
        counts[ch] = counts.get(ch, 0) + 1
# Calculate total letters
total_letters = sum(counts.values())
# Print total
print("Total number of letters:", total_letters)
# Print counts for each letter
for ch in sorted(counts):
    print(f"Letter '{ch}': {counts[ch]} times")
```
