# BUdget Converter

### (I made this program to help me calculate my allowance. I sometimes think in hours and sometimes in days, 
### so this program helps me avoid confusion and get the corrected budget per hour or per day automatically.)

```python
print("=== BUdget Calculator ===")
```

### (This is Sava, which also stands for "Sa-ving, v-irtual a-ssitance", 
### his an AI that helps you with your daily allowance, so you wouldn't go over the budget.)

```python
print("Sava: Hello my name is Sava and I'm here to help you manage your daily spending by calculating your weekly budget.")
print("Sava: Please enter your name, time you'll spend this week, and your budget per day.")
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

### (I added a input validation to prevent empty string conversion error.)
### (This also check if input is too short (less than 2 characters.))

```python
if len(time_input) < 2: 
    print("Sava: Invalid input format. Please use format like '3d' or '12h'.")
    days = 0
```

### (This gets the last character.)

```python
else:
    unit = time_input[-1]
```

### (This gets the numbers only.)

```python
try:
    value = float(time_input[:-1])

    if value < 0:
        print("Sava: Negative values are not allowed.")

    elif allowance_per_day < 0:
        print("Sava: Negative allowance is not allowed. Please input a valid number.")
```

### (This converts hours to days.)

```python
    else:
        if unit == "h":
            days = convert_to_days(value)

        elif unit == "d":
            days = value

        else:
            print("Sava: Invalid input. Use h for hours or d for days.")
            days = None
```

### (Only calculate if ALL inputs are valid.)

```python
        if unit in ["h", "d"] and allowance_per_day >= 0:

            total_allowance = compute_allowance(days, allowance_per_day)

            print("=== Calculated Results ===")
            print("Sava: Hello,", name + ", Here are the results of my calculations.")
            print("Equivalent days:", days, "d")
            print("Total allowance: ₱", total_allowance)


except ValueError:
    print("Sava: Invalid number format. Please enter a valid number followed by 'h' or 'd'.")
```
