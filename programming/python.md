# Python Programming Notes

This document contains basic Python concepts, examples, and practice snippets.

---

## 1. Variables

Variables store data values.

Example:

```python
name = "Harsha"
age = 20

print(name)
print(age)
```

Output:
Harsha
20

---

## 2. Data Types

Common Python data types:

* int → integers
* float → decimal numbers
* str → text
* bool → True/False
* list → ordered collection
* dict → key-value pairs

Example:

```python
num = 10
price = 19.5
name = "Python"
is_valid = True
```

---

## 3. Conditional Statements

Used to make decisions in programs.

Example:

```python
age = 18

if age >= 18:
    print("Eligible to vote")
else:
    print("Not eligible")
```

---

## 4. Loops

Loops allow repeating tasks.

### For Loop

```python
for i in range(5):
    print(i)
```

Output:
0
1
2
3
4

### While Loop

```python
count = 0

while count < 3:
    print("Hello")
    count += 1
```

---

## 5. Functions

Functions allow code reuse.

Example:

```python
def greet(name):
    print("Hello", name)

greet("Harsha")
```

Output:
Hello Harsha

---

## 6. Lists

Lists store multiple values.

Example:

```python
numbers = [1, 2, 3, 4]

print(numbers[0])
print(len(numbers))
```

Output:
1
4

---

## 7. Dictionaries

Dictionaries store data in key-value pairs.

Example:

```python
student = {
    "name": "Harsha",
    "age": 20,
    "course": "CSE"
}

print(student["name"])
```

---

## 8. Example Program: Prime Number Check

```python
num = 7

if num > 1:
    for i in range(2, num):
        if num % i == 0:
            print("Not Prime")
            break
    else:
        print("Prime Number")
```

---

## Skills Practiced

* Python basics
* Problem solving
* Logical thinking
* Programming fundamentals
