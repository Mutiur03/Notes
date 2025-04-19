
## 1. **List**

A list is an ordered, mutable (changeable) collection that allows duplicate elements.

### Characteristics:

- Ordered (maintains insertion order)
- Mutable (can be modified after creation)
- Allows duplicate elements
- Indexable

### Syntax:

```python
my_list = [1, 2, 3, 4, 5]
```
```python
my_list = [1, "Hello", 3.14, True]
```
### Common List Methods:

```python
my_list.append(6)        # Adds an element to the end
my_list.insert(2, 99)    # Inserts 99 at index 2
my_list.remove(3)        # Removes the first occurrence of 3
my_list.pop()            # Removes and returns the last element
my_list.reverse()        # Reverses the list
my_list.sort()           # Sorts the list in ascending order
```

---

## 2. **Tuple**

A tuple is an ordered, immutable collection that allows duplicate elements.

### Characteristics:

- Ordered
- Immutable (cannot be modified after creation)
- Allows duplicate elements
- Indexable

### Syntax:

```python
my_tuple = (1, 2, 3, 4, 5)
```
```python
my_tuple = (1, "Hello", 3.14, True)
```
### Tuple Operations:

```python
val = my_tuple[2]    # Access element at index 2
length = len(my_tuple)  # Get tuple length
```

**Note:** Since tuples are immutable, they do not support methods like `append()` or `remove()`.

---

## 3. **Set**

A set is an unordered, mutable collection that does not allow duplicate elements.

### Characteristics:

- Unordered (does not maintain insertion order)
- Mutable
- No duplicate elements allowed
- Not indexable (cannot access elements using indexes)

### Syntax:

```python
my_set = {1, 2, 3, 4, 5}
```
```python
my_set = {1, "Hello", 3.14, True}
```
### Common Set Methods:

```python
my_set.add(6)          # Adds an element
my_set.remove(3)       # Removes an element
my_set.discard(10)     # Removes an element if present, no error if absent
my_set.pop()           # Removes a random element
union_set = my_set.union({7, 8, 9})    # Combines two sets
intersection_set = my_set.intersection({3, 4, 5})  # Finds common elements
```

**Note:** Sets do not allow duplicate values, and their elements cannot be modified, though new elements can be added or removed.

---

## 4. **Dictionary**

A dictionary is an unordered collection of key-value pairs.

### Characteristics:

- Unordered (prior to Python 3.7, insertion order was not maintained)
- Mutable
- Keys must be unique, but values can be duplicated
- Fast lookup due to hashing

### Syntax:

```python
my_dict = {'name': 'Alice', 'age': 25, 'city': 'New York'}
```

### Common Dictionary Methods:

```python
my_dict['age'] = 26    # Modify a value
my_dict['gender'] = 'Female'  # Add a new key-value pair
value = my_dict.get('age')  # Get value safely
my_dict.pop('city')    # Remove a key-value pair
keys = my_dict.keys()  # Get all keys
values = my_dict.values()  # Get all values
items = my_dict.items()  # Get key-value pairs
```

---
---
---
---

## 5. **Collections Module**

Python’s `collections` module provides additional collection types that enhance the standard ones.

### 5.1 **Deque (Double-Ended Queue)**

A deque is a list optimized for fast append and pop operations from both ends.

```python
from collections import deque
queue = deque([1, 2, 3])
queue.append(4)    # Add to right end
queue.appendleft(0) # Add to left end
queue.pop()        # Remove from right end
queue.popleft()    # Remove from left end
```

### 5.2 **Defaultdict**

A `defaultdict` provides a default value for missing keys.

```python
from collections import defaultdict
dd = defaultdict(int)
dd['a'] += 1  # Instead of getting KeyError, it initializes with 0
```

### 5.3 **OrderedDict**

An `OrderedDict` remembers the insertion order of keys (from Python 3.7+, regular dictionaries do this too).

```python
from collections import OrderedDict
od = OrderedDict()
od['a'] = 1
od['b'] = 2
od['c'] = 3
```

### 5.4 **Counter**

A `Counter` counts occurrences of elements in a collection.

```python
from collections import Counter
counter = Counter("banana")
print(counter)  # Output: Counter({'a': 3, 'n': 2, 'b': 1})
```

### 5.5 **NamedTuple**

A `namedtuple` is an immutable, lightweight alternative to classes.

```python
from collections import namedtuple
Person = namedtuple('Person', ['name', 'age'])
p = Person('Alice', 25)
print(p.name, p.age)
```

---

## Conclusion

Python provides various collection types, each suited for different use cases:

- **Lists** for ordered, mutable sequences
- **Tuples** for immutable sequences
- **Sets** for unordered collections without duplicates
- **Dictionaries** for key-value storage
- **Collections module** for advanced collection types like deque, defaultdict, Counter, and namedtuple

Understanding these collections and their functionalities will help you write more efficient and readable Python programs.