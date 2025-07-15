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

## For Loops

The for statement in Python differs a bit from what you may be used to in C. Rather than giving the user the ability to define both the iteration step and halting condition (as C), Python’s for statement iterates over the items of any sequence (a list or a string), in the order that they appear in the sequence.

```python
# Measure some strings:
words = ['cat', 'window', 'defenestrate']
for w in words:
    print(w, len(w))

>cat 3
>window 6
>defenestrate 12
```

### The range() Function

For iterating over a sequence of numbers, the built-in function range() comes in handy. It generates arithmetic progressions:

```python
for i in range(5):
    print(i)

>0
>1
>2
>3
>4
```

The given end point is never part of the generated sequence; range(10) generates 10 values, the legal indices for items of a sequence of length 10. 

**It is possible to let the range start at another number, or to specify a different increment (even negative; sometimes this is called the ‘step’)**

```python
# range(start, end, steps)

list(range(5, 10))
>[5, 6, 7, 8, 9]

list(range(0, 10, 3))
>[0, 3, 6, 9]

list(range(-10, -100, -30))
>[-10, -40, -70]

```

To iterate over the indices of a sequence, range() and len() can be combined as follows:

```python
a = ['Mary', 'had', 'a', 'little', 'lamb']
for i in range(len(a)):
    print(i, a[i])

>0 Mary
>1 had
>2 a
>3 little
>4 lamb

```

>[!IMPORTANT]
In many ways the object returned by range() behaves as if it is a list, but in fact it isn’t. It is an object which returns the successive items of the desired sequence when you iterate over it, but it doesn’t really make the list, thus saving space. Such an object is called an iterable.

An example of a function that takes an iterable is sum():
```python
sum(range(4)) # 0 + 1 + 2 + 3
>6
```

>[!NOTE]
**for loops can also have an else part, which will be executed when the loop finishes its final iteration, that is, if no break occured.**

```python
for n in range(2, 10):
    for x in range(2, n):
        if n % x == 0: # x is a factor of n
            print(f"{n} equals {x}*{n//x}")
            break # breaks out of the second for loop, that is, jumps to the next value of n
    else:
        # no factor of n
        print(f"{n} is prime")

>2 is a prime number
>3 is a prime number
>4 equals 2 * 2
>5 is a prime number
>6 equals 2 * 3
>7 is a prime number
>8 equals 2 * 4
>9 equals 3 * 3

```
