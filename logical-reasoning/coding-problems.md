# Logical Problems Using Code

## Problem: Find Missing Number

### Question

Find the missing number in the sequence:

1, 2, 4, 5, 6

### Python Solution

```python
numbers = [1, 2, 4, 5, 6]

for i in range(1, 7):
    if i not in numbers:
        print("Missing number:", i)
```

### Output

Missing number: 3
