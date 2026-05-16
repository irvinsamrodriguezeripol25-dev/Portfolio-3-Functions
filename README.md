# Portfolio-3-Functions

# BUdget Converter

### (I made this program to help me calculate my allowance. I sometimes think in hours and sometimes in days, 
### so this program helps me avoid confusion and get the corrected budget per hour or per day automatically.)

### (Function to convert hours into days.)

```python
print("=== BUdget Calculator ===")
```

### (This is Sava, which also stands for "Sa-ving, v-irtual a-ssitance", 
### his an AI that helps you with your daily allowance, so you wouldn't go over the budget.)

```python
print("Sava: Hello my name is Sava and I'm here to help you manage your daily spending by calculating your weekly budget.")
print("Sava: Please enter your name, time you'll spend this week and your budget per day.")
```

### (This is the Function that converts hours to days.)

```python
def convert_to_days(hours):
    days = hours / 24
    return days
```

### (This is the Function that compute allowance.)

```python
def compute_allowance(days, allowance_per_day):
    total = days * allowance_per_day
    return total

name = input("Enter your name: ")
time_input = input("Enter time (example: 3d or 12h): ")
allowance_per_day = float(input("Enter allowance per day: "))
```

### (This gets the last character.)

```python
unit = time_input[-1]
```

### (This gets the numbers only.)

```python
value = float(time_input[:-1])
```

### (This checks for negative values.)

```python
if value < 0:
    print("Savi: Negative values are not allowed.")
```

### (Converts days and hours if needed.)

```python
if unit == "h":
    days = convert_to_days(value)
elif unit == "d":
    days = value
else:
    print("Invalid input. Use h for hours or d for days.")
    days = 0
```

### (Compute allowance.)

```python
total_allowance = compute_allowance(days, allowance_per_day)
```

### (Shows the results.)

```python
print("=== Calculated Result ===")

print("Sava: Hello,", name + ", Here are the results of my calculations.")
print("Equivalent days: Sava: ", days,"d")
print("Total allowance: Sava: ", "₱",total_allowance)
```
