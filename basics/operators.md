# If Statements, Logical and Comparative Operators

## If, elif, and else 

Example:

```python
x = int(input("Please enter an integer: "))

if x < 0: # Read ':' as 'is true'  
    print('Negative') # When (x<0) is True
elif x == 0: # elif stands for elseif
    print('Zero')
else:
    print('Positive')
```

>[!IMPORTANT]
**Indentation indicates if a line of code is part of the statement/loop.**
**Incase of Nesting Loops, use multiple indentations as necessary.**

## Logical AND, OR and NOT Operators

```python
if has_high_income and has_good_credit: # Both Conditions should be True
    print('Eligible for Loan')

if has_high_income or has_good_credit: # Any One Condition should be True
    print('Eligible for Loan')

if has_high_income and not has_criminal_record: # First Should be True and Second should be False
    print('Eligible for Loan')
```

## Comparative Operators

```python
if temp>30:
    print('Its a Hot Day.')
elif temp<0:
    print('Its a Cold Day')
elif temp == 25: # Double equals to check if values are equal
    print('Its a Good Day')
```

>[!IMPORTANT]
Single Equals ( = ) - Used to Assign Values
Double Equals ( == ) - Used to Check/Compare Values