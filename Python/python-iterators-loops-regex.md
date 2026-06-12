# Python Iterators, Loops, and Regular Expressions

## 1. Python Iterators

An iterator is an object that returns values one by one.

It is used to go through data step by step instead of loading everything at once.

### Why it matters

- Helps process large data (logs, wordlists)
- Used in automation scripts
- Efficient memory usage

### Key Methods

- `__iter__()` → returns iterator
- `__next__()` → returns next value

### Example

```python
data = [1, 2, 3]

it = iter(data)

print(next(it))  # 1
print(next(it))  # 2
print(next(it))  # 3
````

---

## 2. Iterator vs Iterable

| Term     | Meaning                             |
| -------- | ----------------------------------- |
| Iterable | Object you can loop over            |
| Iterator | Object that gives values one by one |

### Examples of Iterables

* list
* tuple
* string
* set
* dictionary

### Example

```python
text = "admin"

for char in text:
    print(char)
```

---

## 3. Python For Loops

A `for` loop is used to iterate over a sequence.

### Simple Example

```python
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)
```

### Practical Use

* Loop through payloads
* Try multiple usernames/passwords
* Process API responses

```python
users = ["admin", "test", "guest"]

for user in users:
    print("Trying:", user)
```

---

## 4. range() Function

Used to generate numbers.

### Syntax

```python
range(start, stop, step)
```

### Examples

```python
for i in range(5):
    print(i)   # 0 to 4
```

```python
for i in range(2, 6):
    print(i)   # 2 to 5
```

### Practical Use

* IDOR testing
* Parameter fuzzing

```python
for user_id in range(1, 5):
    print(f"/api/user/{user_id}")
```

---

## 5. Regular Expressions (RegEx)

A Regular Expression is used to match patterns in text.

### Why it matters

* Extract data from responses
* Find emails, tokens, IDs
* Validate input

---

## 6. RegEx Module

```python
import re
```

---

## 7. RegEx Functions

| Function    | Description         |
| ----------- | ------------------- |
| `findall()` | Returns all matches |
| `search()`  | Returns first match |
| `split()`   | Splits string       |
| `sub()`     | Replaces matches    |

---

## 8. RegEx Examples

### Extract Numbers

```python
import re

text = "user123 id456"

numbers = re.findall("\d+", text)
print(numbers)
```

---

### Extract Emails

```python
text = "Contact admin@test.com"

emails = re.findall(r"[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+", text)
print(emails)
```

---

### Find Token

```python
data = "token=abc123xyz"

match = re.search("token=.*", data)
print(match.group())
```

---

## 9. Metacharacters

| Symbol | Meaning        |    |
| ------ | -------------- | -- |
| `.`    | Any character  |    |
| `\d`   | Digit          |    |
| `\w`   | Word character |    |
| `^`    | Starts with    |    |
| `$`    | Ends with      |    |
| `*`    | 0 or more      |    |
| `+`    | 1 or more      |    |
| `?`    | Optional       |    |
| `{}`   | Exact count    |    |
| `      | `              | OR |
| `()`   | Group          |    |

---

## 10. RegEx Flags

| Flag   | Description   |
| ------ | ------------- |
| `re.I` | Ignore case   |
| `re.M` | Multi-line    |
| `re.S` | Match newline |

### Example

```python
import re

text = "Admin"

print(re.search("admin", text, re.I))
```

---

## 11. Combined Example

```python
import re

responses = [
    "user=admin id=1",
    "user=test id=2"
]

for res in responses:
    ids = re.findall("\d+", res)
    print(ids)
```

---

## 12. Summary

* Iterators return values one by one
* Iterable objects can be looped over
* `for` loops simplify iteration
* `range()` generates numbers
* RegEx is used for pattern matching
* `re` module provides regex functions

---

## 13. Practice Ideas

* Extract numbers from responses
* Find emails in text
* Loop through user IDs
* Parse logs for sensitive data
* Build simple automation scripts

```


