
# Python Indexing and Mutability

## Overview
This document covers the fundamental concepts of indexing in Python, memory allocation, and the differences between mutable and immutable data types. We will explore various indexing operations, including positive and negative indexing, and understand how Python manages memory for lists, tuples, and strings.

---

## Indexing in Python
Indexing refers to accessing individual elements within a sequence (e.g., strings, lists, tuples) using their position or index number.

### How Indexing Works
- **Python uses zero-based indexing**, meaning the first element has an index of `0`.
- Indexes are assigned sequentially in the order elements appear in the collection.

Example:
```python
my_list = ['a', 'b', 'c', 'd']
print(my_list[0])  # Output: 'a'
print(my_list[2])  # Output: 'c'
```

### Memory Allocation for Indexed Data
- Python stores objects in memory, and variables point to these objects.
- Mutable objects (like lists) store references to memory locations, while immutable objects (like tuples) store fixed values.

Example:
```python
x = [10, 20, 30]
y = x
x[0] = 100
print(y)  # Output: [100, 20, 30] (both reference the same memory)
```

---

## Indexing Operations
### Positive Indexing
- Starts from `0` and goes up.
- Example:
  ```python
  my_tuple = (10, 20, 30, 40)
  print(my_tuple[1])  # Output: 20
  ```

### Negative Indexing
- Starts from `-1` and goes backward.
- Example:
  ```python
  my_string = "python"
  print(my_string[-1])  # Output: 'n'
  ```

### Why Endpoint +1 in Indexing?
Python slicing follows the `start:stop:step` convention, and the endpoint is **exclusive**, meaning it stops before the provided index.

Example:
```python
my_list = [1, 2, 3, 4, 5]
print(my_list[1:4])  # Output: [2, 3, 4] (index 4 is excluded)
```

---

## Mutability and Immutability
### Mutable Data Types
Mutable objects can be changed after creation. Examples include:
1. **Lists**
   ```python
   my_list = [1, 2, 3]
   my_list[0] = 10  # Allowed
   print(my_list)  # Output: [10, 2, 3]
   ```

2. **Dictionaries** (not covered in detail here)

### Immutable Data Types
Immutable objects cannot be modified after creation. Examples include:
1. **Strings**
   ```python
   my_string = "hello"
   # my_string[0] = 'H'  # Error: Strings are immutable
   print(my_string[1:4])  # Output: 'ell'
   print(my_string[-4:-1])  # Output: 'ell'
   ```

2. **Tuples**
   ```python
   my_tuple = (1, 2, 3)
   # my_tuple[1] = 20  # Error: Tuples are immutable
   print(my_tuple[0:2])  # Output: (1, 2)
   print(my_tuple[-3:-1])  # Output: (1, 2)
   ```

---

## Complex Indexing
For multi-dimensional lists and nested data structures, indexing requires multiple steps.

Example:
```python
nested_list = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
print(nested_list[1][2])  # Output: 6
```

### Address Mapping in Mutable and Immutable Objects
- In **lists**, modifications update the referenced memory location.
- In **tuples**, changes require creating a new object with updated values.

Example:
```python
my_tuple = ([1, 2], [3, 4])
my_tuple[0][1] = 20  # Allowed because the inner list is mutable
print(my_tuple)  # Output: ([1, 20], [3, 4])
```

Additional Examples:
```python
# List Indexing Examples
numbers = [10, 20, 30, 40, 50]
print(numbers[0])  # Output: 10
print(numbers[-1])  # Output: 50
print(numbers[1:4])  # Output: [20, 30, 40]
```

```python
# Tuple Indexing Examples
tuple_data = (100, 200, 300, 400)
print(tuple_data[0])  # Output: 100
print(tuple_data[-2])  # Output: 300
print(tuple_data[1:3])  # Output: (200, 300)
```

---

## Summary
1. Indexing starts from 0 and can use positive or negative values.
2. Lists are mutable, whereas tuples and strings are immutable.
3. Slicing operations exclude the endpoint.
4. Nested structures require multi-level indexing.
5. Memory references play a key role in mutability behavior.

This document serves as a comprehensive guide for understanding indexing and mutability in Python.
