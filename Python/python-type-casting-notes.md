# Python Type Casting Notes 

## What is Type Casting?

Type casting means converting one data type into another.

```python
x = "10"
y = int(x)  # string → integer
```

---

## Why Casting is Important?

* User input always comes as string
* APIs return string/JSON data
* Mathematical operations require correct data types

---

## Practice Questions

### Q1 (Basic)

Convert `"25"` into integer and add `10`.

---

### Q2 (Basic → Intermediate)

Convert float `12.78` → integer → string.
Print final value and type.

---

### Q3 (Intermediate)

```python
a = "15"
b = 5
```

Perform addition → output should be `20` (use casting).

---

### Q4 (Intermediate → Advanced)

```python
data = ["10", "20", "30", "40"]
```

Convert all elements into integers and calculate sum using a loop.

---

### Q5 (Advanced)

```python
user_input = "100.5"
```

* Convert into float
* Convert into integer
* Explain why integer value changes

---

## Common Mistakes

### 1. Direct Conversion Error

```python
int("100.5")  # ValueError
```

Fix:

```python
int(float("100.5"))
```

---

### 2. Data Loss in int()

```python
int(100.5)  # → 100 (.5 lost)
```

`int()` truncates, not rounds.

---

### 3. Overwriting Variables in Loop

```python
for i in data:
    res = int(i)  # only last value stored
```

Fix:

```python
total = 0
for i in data:
    total += int(i)
```

---

### 4. Mixing Data Types

```python
"15" + 5  # TypeError
```

Fix:

```python
int("15") + 5
```

---

## One-Line Tricks (Pythonic Code)

### Loop → One-liner pattern:

```python
# Normal
total = 0
for i in data:
    total += int(i)

# One-liner
sum(int(i) for i in data)
```

---

### List Creation

```python
# Normal
result = []
for i in nums:
    result.append(i * 2)

# One-liner
result = [i * 2 for i in nums]
```

---

## Data Loss & Precision Issues

### Float Precision Problem

```python
print(0.1 + 0.2)
# Output: 0.30000000000000004
```

---

## Best Practice for Money

Use Decimal module:

```python
from decimal import Decimal

price = Decimal("100.5")
```

* No precision loss
* Used in fintech / banking apps

---

## Hacker Insights

* Always validate data types from APIs
* Avoid blind casting
* Never use int() when precision matters
* Prefer Decimal for financial calculations

---

## Summary

* int() → removes decimal (data loss)
* float() → keeps decimal
* str() → converts to string
* Decimal → best for precision

---
