## GRID CONNECTIONS:

A supply chain manager at Amazon Logisitcs wants to determine the number of connections between warehouses, represented as nodes on a grid. A grid with m rows and n columns is used to form a cluster of nodes. If a point in the grid has a value of 1, then it represents a node.

Each node in the cluster has a level associated with it. A node located in the ith row of the grid is a level inode.

Here are the rules for creating a cluster:

- Every node at a level connects to the next level that contains at least 1 node (i.e., every node at level i connects to all the nodes at level k where k > i and k is the first level after level i than contains at least one note).
- When i reaches the last level in the grid, no more connections are possible.

Given such a grid, please help the supply chain manager by finding the number of connections present in the cluster.

Relevant Amazon OA Problems:

```python
from typing import List

def connections(grid: List[List[int]]) -> int:
    sum = 0
    counts = []
    for row in grid:
        count = 0
        for x in row:
            if x == 1:
                count += 1
        if count != 0:
            counts.append(count)
    for i in range(len(counts) - 1):
        sum += counts[i] * counts[i+1]
    return sum

if __name__ == '__main__':
    grid = [[int(x) for x in input().split()] for _ in range(int(input()))]
    res = connections(grid)
    print(res)
```

