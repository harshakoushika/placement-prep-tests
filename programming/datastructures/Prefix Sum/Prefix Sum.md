# Prefix Sum Problems (DSA)

Prefix Sum is a technique used to **precompute cumulative sums of an array** to answer range queries efficiently.

If `prefix[i]` stores the sum of elements from index `0` to `i`:

prefix[i] = arr[0] + arr[1] + ... + arr[i]

To find sum from `L` to `R`:

sum(L, R) = prefix[R] - prefix[L-1]

Time Complexity:
- Prefix creation → O(n)
- Range query → O(1)

---

# Problem 1: Build Prefix Sum Array

### Problem
Given an array, construct its prefix sum array.

### Example
Input:
arr = [1,2,3,4]

Output:
[1,3,6,10]

### Solution

```python
arr = [1,2,3,4]

prefix = [0]*len(arr)

prefix[0] = arr[0]

for i in range(1,len(arr)):
    prefix[i] = prefix[i-1] + arr[i]

print(prefix)
```

---

# Problem 2: Range Sum Query

### Problem
Find sum between index L and R.

### Example
arr = [1,3,5,7,9]

Query: L=1, R=3

Output:
15

### Explanation
3 + 5 + 7 = 15

### Solution

```python
arr = [1,3,5,7,9]

prefix = [0]*len(arr)
prefix[0] = arr[0]

for i in range(1,len(arr)):
    prefix[i] = prefix[i-1] + arr[i]

L = 1
R = 3

if L == 0:
    print(prefix[R])
else:
    print(prefix[R] - prefix[L-1])
```

---

# Problem 3: Subarray Sum Equals K

### Problem
Find number of subarrays whose sum equals k.

### Example

arr = [1,1,1]
k = 2

Output:
2

### Solution

```python
arr = [1,1,1]
k = 2

prefix = 0
count = 0
freq = {0:1}

for num in arr:
    prefix += num

    if prefix-k in freq:
        count += freq[prefix-k]

    freq[prefix] = freq.get(prefix,0)+1

print(count)
```

---

# Problem 4: Running Sum of Array

### Problem
Return the running sum of an array.

Example

arr = [1,2,3,4]

Output

[1,3,6,10]

### Solution

```python
arr = [1,2,3,4]

for i in range(1,len(arr)):
    arr[i] += arr[i-1]

print(arr)
```

---

# Problem 5: Pivot Index

### Problem
Find index where left sum equals right sum.

Example

arr = [1,7,3,6,5,6]

Output

3

### Solution

```python
arr = [1,7,3,6,5,6]

total = sum(arr)
left = 0

for i in range(len(arr)):
    if left == total-left-arr[i]:
        print(i)
        break
    left += arr[i]
```

---

# Problem 6: Maximum Subarray Sum (Prefix Concept)

### Problem
Find maximum subarray sum.

Example

arr = [-2,1,-3,4,-1,2,1,-5,4]

Output

6

### Solution

```python
arr = [-2,1,-3,4,-1,2,1,-5,4]

max_sum = arr[0]
curr = arr[0]

for i in range(1,len(arr)):
    curr = max(arr[i], curr + arr[i])
    max_sum = max(max_sum, curr)

print(max_sum)
```

---

# Problem 7: Count Subarrays With Sum Divisible by K

### Problem
Count subarrays whose sum is divisible by k.

### Example

arr = [4,5,0,-2,-3,1]
k = 5

Output

7

### Solution

```python
arr = [4,5,0,-2,-3,1]
k = 5

prefix = 0
count = 0
freq = {0:1}

for num in arr:
    prefix = (prefix + num) % k

    count += freq.get(prefix,0)
    freq[prefix] = freq.get(prefix,0) + 1

print(count)
```

---

# Problem 8: Find Subarray With Given Sum

### Problem
Check if subarray with given sum exists.

Example

arr = [1,2,3,7,5]
target = 12

Output

True

### Solution

```python
arr = [1,2,3,7,5]
target = 12

prefix = 0
seen = {0}

for num in arr:
    prefix += num

    if prefix-target in seen:
        print(True)
        break

    seen.add(prefix)
```

---

# Problem 9: Range Sum Query (Multiple Queries)

### Problem
Answer multiple range sum queries efficiently.

### Solution

```python
arr = [2,4,6,8,10]

prefix = [0]*len(arr)
prefix[0] = arr[0]

for i in range(1,len(arr)):
    prefix[i] = prefix[i-1] + arr[i]

queries = [(1,3),(0,2)]

for L,R in queries:
    if L==0:
        print(prefix[R])
    else:
        print(prefix[R]-prefix[L-1])
```

---

# Problem 10: Count Subarrays With Equal 0s and 1s

### Problem
Count subarrays containing equal number of 0s and 1s.

### Idea

Convert:
0 → -1

Then count prefix sums.

### Solution

```python
arr = [0,1,0,1,1,0]

prefix = 0
count = 0
freq = {0:1}

for num in arr:

    if num == 0:
        num = -1

    prefix += num

    if prefix in freq:
        count += freq[prefix]

    freq[prefix] = freq.get(prefix,0)+1

print(count)
```

---

# Summary

Prefix Sum helps solve problems involving:

- Range sum queries
- Subarray sums
- Frequency based prefix techniques
- Counting subarrays

Typical complexity improvement:

Brute Force → O(n²)  
Prefix Sum → O(n)
