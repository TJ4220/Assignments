# OOP in Python

## Objective

- Understand the foundations of OOP
- Differentiate functional vs OOP
- Properties and methods in OOP

## Prerequisite

- Functions
- Exceptions

## What do you need to complete this exercise?

- Please follow my video tutorial [installing Python and PyCharm CE on Windows](https://youtu.be/nFN0JW43GKY). Note: The version you see may differ slightly from what is shown in the video.
- Use the PyCharm IDE to write and compile your code. Submit your responses in a Markdown file on GitHub. Ensure that all code included in the Markdown file runs without errors. Refer to [Submitting Your Assignment Using GitHub](https://sdccd-edu.zoom.us/rec/share/F4rK6ZABMXlRn4aGlZ9P005e-iRKwq8rr9KuawDoJ77TdkybKU2tpf4l4QSe113g.ut4jpVaqaPY0oI7b?startTime=1725121532000) for detailed instructions.

## 1. Extending Stack class behavior

I've showed you recently how to extend Stack possibilities by defining a new class (i.e., a subclass) which retains all inherited traits and adds some new ones.

Your task is to extend the Stack class behavior in such a way so that the class is able to count all the elements that are pushed and popped (we assume that counting pops is enough). Use the Stack class I've provided in the code below.

Follow the hints:

- introduce a property designed to count pop operations and name it in a way which guarantees hiding it;
- initialize it to zero inside the constructor;
- provide a method which returns the value currently assigned to the counter (name it get_counter()). Complete the code in the editor. Run it to check whether your code outputs 100.

```
class Stack:
    def __init__(self):
        self.__stk = []

    def push(self, val):
        self.__stk.append(val)

    def pop(self):
        val = self.__stk[-1]
        del self.__stk[-1]
        return val


class CountingStack(Stack):
    def __init__(self):
    #
    # Fill the constructor with appropriate actions.
    #

    def get_counter(self):
    #
    # Present the counter's current value to the world.
    #

    def pop(self):
    #
    # Do pop and update the counter.
    #


stk = CountingStack()
for i in range(100):
    stk.push(i)
    stk.pop()
print(stk.get_counter())
```
## Answer
```python
class stack:
  def_init_(self):
    self._stk+[] #keeps the list private
  def push(self, val):
    self._stk.append(val)
  def pop(self):
    val = self._stk[-1]
    del self._stk[-1]
    return val
class countingstack(stack):
  def_init_(self):
    super()._init_() #base storage
    self._counter #private counter for pop
  def get_counter(self):
      return self._counter
  def pop(self):
      val = super().pop()
      self._counter += 1
      return val
stk + CountingStack()
for i in range(100):
    stk.push(i)
    stk.pop()
print(stk.get_counter())
```
## 2a. Implementing a queue class from scratch (intermediate difficulty)

As you already know, a stack is a data structure realizing the LIFO (Last In – First Out) model. It's easy and you've already grown perfectly accustomed to it.

Let's try something new now. A queue is a data model characterized by the term FIFO: First In – First Out. Note: a regular queue (line) you know from shops or post offices works exactly in the same way – a customer who came first is served first too.

Your task is to implement the Queue class with two basic operations:

`put(element)`, which puts an element at end of the queue; `get()`, which takes an element from the front of the queue and returns it as the result (the queue cannot be empty to successfully perform it.) Follow the hints:

use a list as your storage (just like we did with the stack) `put()` should append elements to the beginning of the list, while `get()` should remove the elements from the end of the list; define a new exception named QueueError (choose an exception to derive it from) and raise it when `get()` tries to operate on an empty list. Complete the code we've provided in the editor. Run it to check whether its output is similar to ours.

**Expected output**

```
1
dog
False
Queue error
```

```
class QueueError(???):  # Choose base class for the new exception.
    #
    #  Write code here
    #


class Queue:
    def __init__(self):
        #
        # Write code here
        #

    def put(self, elem):
        #
        # Write code here
        #

    def get(self):
        #
        # Write code here
        #


que = Queue()
que.put(1)
que.put("dog")
que.put(False)
try:
    for i in range(4):
        print(que.get())
except:
    print("Queue error")
```
## Answer
```python
class QueueError(Exception):
    pass
class Queue:
    def __init__(self):
        self.__data = []
    def put(self, elem):    # append to the beginning (front of internal list)
        self.__data.insert(0, elem)
    def get(self):
        if not self.__data:
            raise QueueError("Queue is empty")    # remove from the end (oldest element)
        return self.__data.pop()
que = Queue()
que.put(1)
que.put("dog")
que.put(False)
try:
    for i in range(4):
        print(que.get())
except QueueError:
    print("Queue error")
```
## Outcome
```python
1
dog
False
Queue error
```
## 2b. Extending a Queue class capability in part 2a (intermediate difficulty)

Your task is to slightly extend the Queue class' capabilities. We want it to have a parameterless method that returns True if the queue is empty and False otherwise.

Complete the code we've provided in the editor. Run it to check whether it outputs a similar result to ours.

Below you can copy the code you used in the previous lab:

```
class QueueError(???):
    pass


class Queue:
    #
    # Code from the previous lab.
    #


class SuperQueue(Queue):
    #
    # Write new code here.
    #


que = SuperQueue()
que.put(1)
que.put("dog")
que.put(False)
for i in range(4):
    if not que.isempty():
        print(que.get())
    else:
        print("Queue empty")
```

## 3. Timer class

We need a class able to count seconds. Easy? Not as much as you may think as we're going to have some specific expectations.

Read them carefully as the class you're about write will be used to launch rockets carrying international missions to Mars. It's a great responsibility.

Your class will be called `Timer`. Its constructor accepts three arguments representing **hours** (a value from range [0..23] - we will be using the military time), **minutes** (from range [0..59]) and **seconds** (from range [0..59]).

Zero is the default value for all of the above parameters. There is no need to perform any validation checks.

The class itself should provide the following facilities:

- objects of the class should be "printable", i.e. they should be able to implicitly convert themselves into strings of the following form: "hh:mm:ss", with leading zeros added when any of the values is less than 10;
- the class should be equipped with parameterless methods called `next_second()` and `previous_second()`, incrementing the time stored inside objects by +1/-1 second respectively.

Use the following hints:

- all object's properties should be private;
- consider writing a separate function (not method!) to format the time string.

Complete the template I've provided in the editor. Run your code and check whether the output looks the same as ours.

**Expected output**

```
23:59:59
00:00:00
23:59:59
```

```
class Timer:
    def __init__( ??? ):
        #
        # Write code here
        #

    def __str__(self):
        #
        # Write code here
        #

    def next_second(self):
        #
        # Write code here
        #

    def prev_second(self):
        #
        # Write code here
        #


timer = Timer(23, 59, 59)
print(timer)
timer.next_second()
print(timer)
timer.prev_second()
print(timer)
```
## Answer
```python
def _format_hms(h, m, s):
    return f"{h:02d}:{m:02d}:{s:02d}"
class Timer:
    def __init__(self, hours=0, minutes=0, seconds=0):
        self.__h = hours
        self.__m = minutes
        self.__s = seconds
    def __str__(self):
        return _format_hms(self.__h, self.__m, self.__s)
    def next_second(self):
        self.__s += 1
        if self.__s == 60:
            self.__s = 0
            self.__m += 1
            if self.__m == 60:
                self.__m = 0
                self.__h = (self.__h + 1) % 24
    def prev_second(self):
        self.__s -= 1
        if self.__s == -1:
            self.__s = 59
            self.__m -= 1
            if self.__m == -1:
                self.__m = 59
                self.__h = (self.__h - 1) % 24
# demo
timer = Timer(23, 59, 59)
print(timer)
timer.next_second()
print(timer)
timer.prev_second()
print(timer)
```
### Outcome
```Python
23:59:59
00:00:00
23:59:59
```
## 4. Weeker class

Your task is to implement a class called `Weeker`. Yes, your eyes don't deceive you – this name comes from the fact that objects of that class will be able to store and to manipulate the days of the week.

The class constructor accepts one argument – a string. The string represents the name of the day of the week and the only acceptable values must come from the following set:

```
Mon Tue Wed Thu Fri Sat Sun
```

Invoking the constructor with an argument from outside this set should raise the `WeekDayError` exception. The class should provide the following facilities:

objects of the class should be "printable", i.e. they should be able to implicitly convert themselves into strings of the same form as the constructor arguments; the class should be equipped with one-parameter methods called `add_days(n)` and `subtract_days(n)`, with `n` being an integer number and updating the day of week stored inside the object in the way reflecting the change of date by the indicated number of days, forward or backward. all object's properties should be private;

Complete the following template and run your code and check whether your output looks the same as mine.

```
class WeekDayError(Exception):
    pass


class Weeker:
    #
    # Write code here.
    #

    def __init__(self, day):
        #
        # Write code here.
        #

    def __str__(self):
        #
        # Write code here.
        #

    def add_days(self, n):
        #
        # Write code here.
        #

    def subtract_days(self, n):
        #
        # Write code here.
        #


try:
    weekday = Weeker('Mon')
    print(weekday)
    weekday.add_days(15)
    print(weekday)
    weekday.subtract_days(23)
    print(weekday)
    weekday = Weeker('Monday')
except WeekDayError:
    print("Sorry, I can't serve your request.")
```

**Expected output**

```
Mon
Tue
Sun
Sorry, I can't serve your request.
```
## Answer
```python
class WeekDayError(Exception):
    pass
class Weeker:
    __DAYS = ('Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun')
    def __init__(self, day):
        if day not in Weeker.__DAYS:
            raise WeekDayError(f"Invalid day: {day}")
        self.__idx = Weeker.__DAYS.index(day)
    def __str__(self):
        return Weeker.__DAYS[self.__idx]
    def add_days(self, n):
        self.__idx = (self.__idx + n) % 7
    def subtract_days(self, n):
        self.__idx = (self.__idx - n) % 7
# demo
try:
    weekday = Weeker('Mon')
    print(weekday)
    weekday.add_days(15)
    print(weekday)
    weekday.subtract_days(23)
    print(weekday)
    weekday = Weeker('Monday')
except WeekDayError:
    print("Sorry, I can't serve your request.")
```
## Outcome
```python
Mon
Tue
Sun
Sorry, I can't serve your request.
```
## Challenges

Please describe the challenges you faced during the exercise.

```python
# One challange I had was understanding name mangling and how the "private" variables actually work.
# Another challenge I messed up on was the wraparound logic in the Timer and Weeker class. First time through i missed the 24% an 7% and it messed up my str formatting. 
```

**End of exercise**
