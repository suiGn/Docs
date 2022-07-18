## Shopping Patterns

1761. Minimum Degree of a Connected Trio in a Graph:  https://leetcode.com/problems/minimum-degree-of-a-connected-trio-in-a-graph/

You are given an undirected graph. You are given an integer `n` which is the number of nodes in the graph and an array `edges`, where each `edges[i] = [ui, vi]` indicates that there is an undirected edge between `ui` and `vi`.

A **connected trio** is a set of **three** nodes where there is an edge between **every** pair of them.

The **degree of a connected trio** is the number of edges where one endpoint is in the trio, and the other is not.

Return *the **minimum** degree of a connected trio in the graph, or* `-1` *if the graph has no connected trios.*

```js
var minTrioDegree = function(n, edges) {
     // create an adjacency list of all the edges;
    const adjacencyList = new Array(n + 1).fill(0).map(() => new Set());
    for (const [x, y] of edges) {
        adjacencyList[x].add(y);
        adjacencyList[y].add(x);
    }
let minimumDegree = Infinity;
// Find all the combinations of 3 vertices that connect
// and if they connect calculate the degree
for (let i = 1; i <= n; i++) {
    for (let j = i + 1; j <= n; j++) {
        for (let k = j + 1; k <= n; k++) {
            if (adjacencyList[i].has(j) && adjacencyList[i].has(k) && adjacencyList[j].has(k)) {
                // We minus 6 because we have 3 vertices and each vertices has 2 edges 
                // going out to the 3 connecting nodes
                const degree = adjacencyList[i].size + adjacencyList[j].size + adjacencyList[k].size - 6;
                minimumDegree = 
                    Math.min(minimumDegree, degree);
            }
        }
    }
}
return minimumDegree === Infinity ? -1 : minimumDegree;
};
```

