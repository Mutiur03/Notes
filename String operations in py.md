
Python provides a rich set of string operations that make it easy to manipulate text. Here’s a comprehensive list of all the common string operations in Python:

---

### 1. **String Creation**

```python
s = "Hello, World!"
```

Strings can be created using single, double, or triple quotes (for multi-line strings).

---

### 2. **Basic String Operations**

- **Concatenation:** Combines two strings.
    ```python
    s1 = "Hello"
    s2 = "World"
    result = s1 + " " + s2  # "Hello World"
    ```
    
- **Repetition:** Repeats the string a specified number of times.
    ```python
    s = "Hi" * 3  # "HiHiHi"
    ```
    
- **Length:** Returns the number of characters in the string.
    ```python
    length = len(s)  # 2 for "Hi"
    ```

---

### 3. **String Indexing and Slicing**

- **Indexing:** Accesses characters by position.
    ```python
    s = "Python"
    char = s[0]  # "P"
    char = s[-1]  # "n" (last character)
    ```
    
- **Slicing:** Extracts a substring.
    ```python
    s = "Python"
    substring = s[1:4]  # "yth"
    substring = s[:3]  # "Pyt"
    substring = s[3:]  # "hon"
    substring = s[::-1]  # "nohtyP" (reverses the string)
    ```   

---

### 4. **String Case Conversion**

- **Lowercase:** Converts all characters to lowercase.
    ```python
    s = "PYTHON"
    lower = s.lower()  # "python"
    ```
    
- **Uppercase:** Converts all characters to uppercase.
    ```python
    s = "python"
    upper = s.upper()  # "PYTHON"
    ```
    
- **Title Case:** Converts the first character of each word to uppercase.
    ```python
    s = "hello world"
    title = s.title()  # "Hello World"
    ```
    
- **Capitalize:** Capitalizes the first character of the string.
    ```python
    s = "hello"
    capitalized = s.capitalize()  # "Hello"
    ```
    
- **Swap Case:** Swaps the case of each character.
    ```python
    s = "Hello"
    swapped = s.swapcase()  # "hELLO"
    ```

---

### 5. **String Searching and Matching**

- **`find()`:** Returns the index of the first occurrence of a substring, or -1 if not found.
    ```python
    s = "hello world"
    index = s.find("world")  # 6
    ```
    
- **`index()`:** Similar to `find()` but raises an exception if not found.
    ```python
    s.index("world")  # 6
    ```
    
- **`startswith()`:** Checks if a string starts with a given substring.
    ```python
    s.startswith("hello")  # True
    ```
    
- **`endswith()`:** Checks if a string ends with a given substring.
    ```python
    s.endswith("world")  # True
    ```

---

### 6. **String Replacement**

- **`replace()`:** Replaces all occurrences of a substring with another substring.
    ```python
    s = "hello world"
    new_s = s.replace("world", "Python")  # "hello Python"
    ```

---

### 7. **Splitting and Joining Strings**

- **Splitting:** Breaks a string into a list of substrings.
    ```python
    s = "hello world"
    words = s.split()  # ["hello", "world"]
    ```
    
    You can also split by a custom delimiter:
    
    ```python
    s = "a,b,c"
    parts = s.split(",")  # ["a", "b", "c"]
    ```
    
- **Joining:** Joins a list of strings into one string.
    ```python
    words = ["hello", "world"]
    sentence = " ".join(words)  # "hello world"
    ```

---

### 8. **Whitespace Removal**

- **`strip()`:** Removes leading and trailing whitespace.
    ```python
    s = "  hello  "
    stripped = s.strip()  # "hello"
    ```
    
- **`lstrip()`:** Removes leading whitespace.
    ```python
    s = "  hello"
    stripped = s.lstrip()  # "hello"
    ```
    
- **`rstrip()`:** Removes trailing whitespace.
    ```python
    s = "hello  "
    stripped = s.rstrip()  # "hello"
    ```

---

### 9. **String Alignment**

- **`center()`:** Centers a string with padding.
    ```python
    s = "hello"
    centered = s.center(10, "-")  # "--hello---"
    ```
    
- **`ljust()`:** Left-aligns a string with padding.
    ```python
    left_aligned = s.ljust(10, "-")  # "hello-----"
    ```
    
- **`rjust()`:** Right-aligns a string with padding.
    ```python
    right_aligned = s.rjust(10, "-")  # "-----hello"
    ```
    
---

### 10. **Checking String Properties**

- **`isalpha()`:** Checks if all characters are alphabetic.
    ```python
    "hello".isalpha()  # True
    ```
    
- **`isdigit()`:** Checks if all characters are digits.
    ```python
    "123".isdigit()  # True
    ```
    
- **`isalnum()`:** Checks if all characters are alphanumeric.
    ```python
    "hello123".isalnum()  # True
    ```
    
- **`isspace()`:** Checks if all characters are whitespace.
    ```python
    "   ".isspace()  # True
    ```
    
- **`istitle()`:** Checks if the string is in title case.
    ```python
    "Hello World".istitle()  # True
    ```
    
- **`isupper()`:** Checks if all characters are uppercase.
    ```python
    "HELLO".isupper()  # True
    ```
    
- **`islower()`:** Checks if all characters are lowercase.
    ```python
    "hello".islower()  # True
    ```

---

### 11. **String Formatting**

- **`format()`:** Formats strings using placeholders.
    ```python
    name = "Alice"
    age = 25
    sentence = "My name is {} and I am {} years old.".format(name, age)
    ```
    
- **f-strings:** A more concise way of formatting (Python 3.6+).
    ```python
    sentence = f"My name is {name} and I am {age} years old."
    ```


---

### 12. **Escaping Special Characters**

- **Escape Sequence:** Adds special characters like newlines or quotes.
    ```python
    s = "He said, \"Hello!\""  # "He said, "Hello!""
    new_line = "Line 1\nLine 2"
    ```
