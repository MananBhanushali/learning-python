# For and While Loops in Java

## While Loops

```python
while condition: # runs while condition is true
    {code-block}
    increment/decrement # to create a stop condition

```

Example:
```python
i = 1
while i<=5: # will run 5 times
    ...
    i++
```

>[!NOTE]
**while loops can also have an else part, which will be executed when the condition is not true.**

**Infinite while loop**
```python
while True:
    ...
    if condition:
        break # to end the program
```

### Break keyword
The break keyword is used to terminate(exit out of) a while/for loop

```python
secret_number = 9
guess_limit = 3
guess_count = 0

while guess_count < guess_limit:
    guess = int(input("Guess the number: "))
    if guess == secret_number:
        print("You won!")
        break # exits out of the while loop, and hence ends the program
    else: 
        print("Try Again.")
        guess_count+=1
else: # After 3 Guesses
    print("You have used all your guesses.")

```