### 1. User input
a. Write a program that prompts the user to enter the weight of a person in kilograms and outputs the equivalent weight in pounds. (Note that 1 kilogram = 2.2 pounds).
```python
# prompt the user to enter weight in kilograms
weight_kg = float(input("enter weight in kilograms: "))

#convert kilograms to pounds
weight_1lb = weight_kg * 2.2

#display the equivalent weight in pounds
print("Equivalent weight in pounds: {:.2f} lbs".format(weight_1lb))
```
I struggled with this topic, this is the link to the youtube video I used to assist me https://www.youtube.com/watch?v=nMCOB8KElwo

b. Interest on a credit card's unpaid balance is calculated using the average daily balance. Suppose that $netBalance$ is the balance shown in the bill, $payment$ is the payment made, $d1$ is the number of days in the billing cycle, and $d2$ is the number of days payment is made before biling cycle. Then, the average daily balance is: $$averageDailybalance = (netBalance \times d1 - payment \times d2)/d1$$.

If the interest rate per month is, say, 0.0152, then the interest on the unpaid balance is: $interest = averageDailyBalance \times 0.0152$

Write a program that accepts as input $netBalance$, $payment$, $d1$, $d2$, and $interest rate per month$. The program outputs the interest.
```python
# prompt the user to enter netbalance
netbalance = float(input("enter netbalance: "))

# prompt the user to enter payment
payment = float(input("enter payment: "))

# prompt the user to enter number of days in the billing cycle
numberofdaysinthebillingcycle = float(input("enter number of days in the billing cycle: "))

# prompt the user to enter number of days payment is made before billing cycle
numberofdayspaymentismadebeforebillingcycle = float(input("enter number of days payment is made before billing cycle: "))

#convert to avrage daily value
avragedailyvalue = (netbalance * numberofdaysinthebillingcycle - payment * numberofdayspaymentismadebeforebillingcycle) / numberofdaysinthebillingcycle

#convert with intrest included
intrest = ( avragedailyvalue * 0.0152)
#display the equivalent averagedailybalance with intrest
print("Equivalent average daily value with intrest: {:3.2f} $".format(0.0152))
```
I think i did it correctly, because the print the avrage daily value with intrest is being multiplied by 0.0152 after all else was inputed but the numbers are a bit strange so maybe my math is incorrect. 


c. Two cars A and B leave an intersection at the same time. Car A travels west at an average speed of x miles per hour and car B travels south at an average speed of y miles per hour. Write a program that prompts the user to enter the average speed of both the cars and the elapsed time (in hours and minutes) and outputs the (shortest) distance between the cars.

### 2. Troubleshooting

Please troubleshoot the following issue without using Python, and explain your reasoning.

```python
a. hello = "hello"
b. _var = 100
c. !var_1 = 200
d. print = "print me"
e. False = 0
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

**End of exercise**
