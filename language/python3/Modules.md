# heapq

**Features**

- `heap[k] <= heap[2*k+1]` and `heap[k] <= heap[2*k+2]`.
- `heap[0]` is the root and the smallest element.

**Functions**

- `heapq.heapify(x)`
  - Transform list *x* into a heap, in-place, in linear time.
- `heapq.heappush(heap, item)`
  - Push the value *item* onto the *heap*, maintaining the heap invariant.
- `heapq.heappop(heap, item)`
  - Pop and return the smallest item from the *heap*, maintaining the heap invariant.
- `heapq.heappushpop(heap, item)`
  - Push *item* on the heap, then pop and return the smallest item from the *heap*.
- `heapq.heapreplace(heap, item)`
  - Pop and return the smallest item from the *heap*, and then push the new *item*.
- `heapq.merge(*iterables, key=None, reverse=False)`
  - Merge multiple sorted inputs into a single sorted output
- `heapq.nlargest(n, iterable, key=None)`
  - Return a list with the *n* largest elements from the dataset defined by *iterable*. *key*, if provided, specifies a function of one argument that is used to extract a comparison key from each element in *iterable*.
- `heapq.nsmallest(n, iterable, key=None)`
  - Return a list with the *n* smallest elements from the dataset defined by *iterable*. *key*, if provided, specifies a function of one argument that is used to extract a comparison key from each element in *iterable*.

# random

# deque

**Features**

- short for "double-ended queue".
- support thread-safe, memory efficient appends and pops from either side of the deque with approximately the same O(1) performance in either direction.

**Construction**

```python3
# make a new deque with three items
d1 = deque('abc')
```

**Methods**

- `append(x)`
  - Add *x* to the right side of the deque.
- `appendleft(x)`
  - Add *x* to the left side of the deque.
- `insert(i, x)`
  - Insert *x* into the deque at position *i*.
- `pop()`
  - Remove and return an element from the right side of the deque.
- `popleft(x)`
  - Remove and return an element from the left side of the deque.
- `remove(value)`
  - Remove the first occurrence of *value*.
- `clear()`
  - Remove all elements from the deque leaving it with length 0.

- `index(x, [start], [stop])`
  - Return the position of *x* in the deque.

- `reverse()`
  - Reverse the elements of the deque in-place and then return `None`.
