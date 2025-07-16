# Lists in Python

The list can be written as a list of comma-separated values (items) between square brackets.  
Lists might contain items of different types, but usually the items all have the same type.


Like strings (and all other built-in sequence types), lists can be indexed and sliced.

```python
squares = [1, 4, 9, 16, 25]

print(squares[1]) # elements can also be changed this way
>4

print(squares[-3:])  # slicing returns a new list
>[9, 16, 25]
```

Lists also support operations like concatenation:
```python
squares + [36, 49, 64, 81, 100]
>[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

Unlike strings, which are immutable, lists are a mutable type, i.e. it is possible to change their content.

>[!IMPORTANT]
**Simple assignment in Python never copies data.**  
**When you assign a list to a variable, the variable refers to the existing list.**  
**Any changes you make to the list through one variable will be seen through all other variables that refer to it.**  
**All slice operations return a new list containing the requested elements.**

Assignment to slices is also possible, and this can even change the size of the list or clear it entirely

```python
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']

# replace some values
letters[2:5] = ['C', 'D', 'E']
>['a', 'b', 'C', 'D', 'E', 'f', 'g']

# now remove them
letters[2:5] = []
>['a', 'b', 'f', 'g']

# clear the list by replacing all the elements with an empty list
letters[:] = []
>[]
```

The built-in function len() also applies to lists
```python
letters = ['a', 'b', 'c', 'd']
len(letters)
```

Lists can also be nested    
```python
coordinates = [[0, 0], [0, 1], [1, 0], [1, 1]]
print(coordinates[2][0]) # will print 1
```

## Lists Methods

1. **list.append(x)** - Add an item to the end of the list.
2. **list.insert(index, x)** - Insert an item at a given position.

The first argument is the index of the element before which to insert, so a.insert(0, x) inserts at the front of the list, and a.insert(len(a), x) is equivalent to a.append(x).

3. **list.remove(x)** - Remove the first item from the list whose value is equal to x. It raises a ValueError if there is no such item.

4. **list.clear()** - Remove all items from the list. Similar to del a[:].

5. **list.sort()** - Sort the items of the list in place 

6. **list.pop(i)** -  Remove the item at the given position in the list, and return it. If no index is specified, a.pop() removes and returns the last item in the list. It raises an IndexError if the list is empty or the index is outside the list range.

7. **list.count(x)** - Return the number of times x appears in the list.
   
8. **list.index(x[, start[, end]])** - Return zero-based index in the list of the first item whose value is equal to x. Raises a ValueError if there is no such item.

The optional arguments start and end are interpreted as in the slice notation and are used to limit the search to a particular subsequence of the list. The returned index is computed relative to the beginning of the full sequence rather than the start argument.

9.  **list.reverse()** - Reverse the elements of the list in place.

10. **list.copy()** - Return a shallow copy of the list. Similar to a[:]. 

An example that uses most of the list methods:

```python
fruits = ['orange', 'apple', 'pear', 'banana', 'kiwi', 'apple', 'banana']
fruits.count('apple')
>2

fruits.count('tangerine')
>0

fruits.index('banana')
>3

fruits.index('banana', 4)  # Find next banana starting at position 4
>6

fruits.reverse()
fruits
>['banana', 'apple', 'kiwi', 'banana', 'pear', 'apple', 'orange']

fruits.append('grape')
fruits
>['banana', 'apple', 'kiwi', 'banana', 'pear', 'apple', 'orange', 'grape']

fruits.sort()
fruits
>['apple', 'apple', 'banana', 'banana', 'grape', 'kiwi', 'orange', 'pear']

fruits.pop()
>'pear'

```

You might have noticed that methods like insert, remove or sort that only modify the list have no return value printed – they return the default None. This is a design principle for all mutable data structures in Python.

Another thing you might notice is that not all data can be sorted or compared. For instance, [None, 'hello', 10] doesn’t sort because integers can’t be compared to strings and None can’t be compared to other types. Also, there are some types that don’t have a defined ordering relation. For example, 3+4j < 5+7j isn’t a valid comparison.