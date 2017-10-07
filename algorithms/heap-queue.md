# Heap Queue / Priority Queue

I recommend reading this: https://docs.python.org/2/library/heapq.html
and http://www.bogotobogo.com/python/python_PriorityQueue_heapq_Data_Structure.php

## What is Heap(Min):
> Heaps are binary trees for which every parent node has a value less than or equal to any of its children.

People often mix the Heap queue with the Priority Queue. They are similar but not actually the same. Here is some clarification from wikipedia:

## And What is Priority Queue:

> In computer science, a priority queue is an abstract data type which is like a regular queue or stack data structure, but where additionally each element has a "priority" associated with it. In a priority queue, an element with high priority is served before an element with low priority. If two elements have the same priority, they are served according to their order in the queue.

> While priority queues are often implemented with heaps, they are conceptually distinct from heaps. A priority queue is an abstract concept like "a list" or "a map"; just as a list can be implemented with a linked list or an array, a priority queue can be implemented with a heap or a variety of other methods such as an unordered array.

## Heap API:

The mostly used are these two, and you could use these two to implement `the heap sort`:
* `heapq.heappush(heap, item)`
* `heapq.heappop(heap)`

```py
import heapq
def heap_sort(l):
  heap = []
  for i in l:
    heapq.heappush(heap, i)
  return [heapq.heappop(heap) for i in range(len(heap))]
```
