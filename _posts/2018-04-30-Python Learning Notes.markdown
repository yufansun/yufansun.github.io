---
layout: post
title:  "Python Learning Notes"
date:   2018-04-30 23:33:17 -0400
categories: Programming questions
author: Yufan Sun
---
## Priority queue: heapq
  * Def: every parent node has a value less than or equal to any of its children
    - `heapq.heappush(heap, item)`
    - `heapq.heappop(heap)`
    - `heapq.heapify(x)` 
        + (Transform list x into a heap, in-place, in linear time)

## Dictionary
* Initialize a dict with default value 0: `my_dict = collections.defaultdict(int)` 
* Initialize a dict of sets: `collections.defaultdict(set)`

## ASCII and char converesion
```python
# Get the ASCII number of a character
number = ord(char)

# Get the character given by an ASCII number
char = chr(number)`
```

## Notes
if ...:
	...
elif:
	...

list.pop([i])
Remove the item at the given position in the list, and return it. If no index is specified, a.pop() removes and returns the last item in the list. (The square brackets around the i in the method signature denote that the parameter is optional, not that you should type square brackets at that position. You will see this notation frequently in the Python Library Reference.)
list.pop() = stack
list.pop(0) = queue

## Customize comparator
```python
def greater(a, b):
    if (a % b) % 2 == 0:
        return 1
    return -1

x = [2,7,5,10,30,15]
sorted(x, cmp=greater)
```
     

