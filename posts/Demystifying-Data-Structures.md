---
title: Demystifying Data Structures A Beginner-Friendly Guide
image: 17.gif
description: DSA
---

Data structures are the backbone of problem-solving and acing programming interviews. If you're new to the world of computer science, don't worry! Understanding data structures might seem daunting at first, but with a little guidance, it can be simplified for beginners like you.

## Choosing the Right Data Structure

Before we dive into the nitty-gritty of data structures, let's understand the importance of choosing the right one. Each data structure has its strengths and weaknesses, and selecting the appropriate one can significantly impact the performance of your code. We often use Big O notation to measure their efficiency.

One of the fundamental data structures is the linked list, which consists of nodes with values and pointers. Linked lists are great for adding and deleting nodes but can be a bit slow when it comes to retrieving or searching elements.

### Three Key Data Structures You Should Know

To build a solid foundation in data structures, focus on three key ones: arrays, linked lists, and hash tables.

Arrays are fixed in size, making adding elements inefficient at times. However, they excel at retrieving items quickly by computing the item's location inside the array.

Linked lists are perfect for scenarios where you need to add or remove elements efficiently. However, accessing elements might be a bit slower compared to arrays.

Hash tables, on the other hand, allow for efficient retrieval of values based on keys. They use a hashing function to determine the memory location, making them incredibly fast for data retrieval.

### Handling Collisions in Hash Tables

While hash tables are powerful, they can suffer from collisions, where two keys hash to the same memory location. But fear not! There are various methods to resolve these collisions and ensure your hash table works flawlessly.

### Embracing Data Structures and Algorithms

Data structures and algorithms are the heart and soul of computer science. For instance, the depth-first search is a vital algorithm that's used extensively. Additionally, queues and stacks are efficient data structures employed in breadth-first search and other limited use cases.

Graphs and trees also play a crucial role in computer science. They share similarities with linked lists, where nodes point to other nodes, creating a complex but organized network.

### The Power of Binary Search Trees

When it comes to searching efficiently, Binary Search Trees (BSTs) take the crown. With specific rules governing node relationships, traversing a BST allows for quick element location, making it a popular choice in various applications.

### Building Your Skills

As a beginner, you might wonder how to enhance your skills in data structures and algorithms. Firstly, practice is key! Code Wars and Leet Code are fantastic platforms for honing your problem-solving abilities. Leet Code, in particular, features programming interview questions from tech companies, giving you real-world challenges to tackle.

### The Big Picture

Now that we got the base essentials out of the way. we can look further into the horizon and take a gander at some of the most important Algos there are. The main goal of an algorithm is to take in input, process it and provide an output that is expected. Algorithms can be classified based on the time and space complexity, the technique used for solving the problem, and the type of problem it solves. Examples of algorithms are sorting, searching, graph traversals, string manipulations, mathematical operations, and many more.

### Algorithms we will be talking about

1. Sorting algorithms: Sorting is a fundamental operation in computer science and there are several efficient algorithms for it, such as quicksort, merge sort and heap sort.
2. Search algorithms: Searching for an element in a large dataset is a common task and there are several efficient algorithms for it, such as binary search and hash tables.
3. Graph algorithms: Graph algorithms are used to solve problems related to graphs, such as finding the shortest path between two nodes or determining if a graph is connected.
4. Dynamic programming: Dynamic programming is a technique for solving problems by breaking them down into smaller subproblems and storing the solutions to these subproblems to avoid redundant computation.
5. Greedy algorithms: Greedy algorithms are used to solve optimization problems by making the locally optimal choice at each step with the hope of finding a global optimum.
6. Divide and Conquer: Divide and Conquer is an algorithm design paradigm based on multi-branched recursion. A divide and conquer algorithm breaks down a problem into sub-problems of the same or related type, until these become simple enough to be solved directly.
7. Backtracking: Backtracking is a general algorithmic technique that considers searching every possible combination in a systematic manner, and abandons a particular path as soon as it determines that it cannot be part of the solution.
8. Randomized Algorithm: Randomized algorithms use randomness to solve a problem. It can be useful to solve problems that cannot be solved deterministically or to improve the average case complexity of a problem.

These algorithms are widely used in various applications and it’s important for a programmer to have a strong understanding of them. So I will try my best to explain them.

## Sorting algorithms
</br>

### Quicksort: 
- Quicksort is a divide-and-conquer algorithm that chooses a “pivot” element from the array and partitions the other elements into two sub-arrays, according to whether they are less than or greater than the pivot. The sub-arrays are then sorted recursively.
</br>

# ![code](https://i.imgur.com/CwVKsYp.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Quicksort Code</summary>
  <pre style="padding: 1em 0em ">
  <code class="language-javascript">
function quicksort(arr) {
  if (arr.length <= 1) {
    return arr;
  }
  const pivot = arr[Math.floor(arr.length / 2)];
  const left = [];
  const middle = [];
  const right = [];
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] < pivot) {
      left.push(arr[i]);
    } else if (arr[i] === pivot) {
      middle.push(arr[i]);
    } else {
      right.push(arr[i]);
    }
  }
  return quicksort(left).concat(middle).concat(quicksort(right));
}
console.log(quicksort([3, 6, 8, 10, 1, 2, 1]));
</code></pre>
</details>

</br>

### Merge Sort
- The merge sort algorithm is a divide-and-conquer algorithm that divides an array in two, sorts the two halves, and then merges them back together.
</br>

# ![Merge Sort code](https://i.imgur.com/NOJFsRt.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Merge Sort Code</summary>
  <pre style="padding: 1em 0em ">
  <code class="language-javascript">
function merge_sort(arr) {
    if (arr.length <= 1) {
        return arr;
    }
    const mid = Math.floor(arr.length / 2);
    const left = merge_sort(arr.slice(0, mid));
    const right = merge_sort(arr.slice(mid));
    return merge(left, right);
}
function merge(left, right) {
    const result = [];
    let i = 0;
    let j = 0;
    while (i < left.length && j < right.length) {
        if (left[i] < right[j]) {
            result.push(left[i]);
            i++;
        } else {
            result.push(right[j]);
            j++;
        }
    }
    return result.concat(left.slice(i)).concat(right.slice(j));
}
console.log(merge_sort([3, 6, 8, 10, 1, 2, 1]));
</code>
</pre>
</details>

</br>

### Heap Sort

- The heap sort algorithm is a comparison-based sorting algorithm that builds a heap from the input elements and then repeatedly extracts the maximum element from the heap and places it at the end of the sorted output array.


 ![Heap Sort code](https://i.imgur.com/fkqO329.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Heap Sort Code</summary>
  <pre style="padding: 1em 0em ">
  <code class="language-javascript">
function heap_sort(arr) {
  const n = arr.length;
  for (let i = Math.floor(n / 2) - 1; i >= 0; i--) {
    heapify(arr, n, i);
  }
  for (let i = n - 1; i > 0; i--) {
    [arr[i], arr[0]] = [arr[0], arr[i]];
    heapify(arr, i, 0);
  }
}
function heapify(arr, n, i) {
  let largest = i;
  let left = 2 *i + 1;
  let right = 2* i + 2;
  if (left < n && arr[left] > arr[largest]) {
    largest = left;
  }
  if (right < n && arr[right] > arr[largest]) {
    largest = right;
  }
  if (largest !== i) {
    [arr[i], arr[largest]] = [arr[largest], arr[i]];
    heapify(arr, n, largest);
  }
}
const arr = [3, 6, 8, 10, 1, 2, 1];
heap_sort(arr);
console.log(arr);
</code>
</pre>
</details>

</br>

## Search algorithms

</br>

### Binary Search

- Binary search is an efficient algorithm for finding an item from a sorted list of items. It works by repeatedly dividing in half the portion of the array being searched until the target value is found.
</br>

![Binary search code](https://i.imgur.com/LdmwRQn.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Binary search Code</summary>
  <pre style="padding: 1em 0em ">
  <code class="language-javascript">
function binarySearch(arr, target) {
  let left = 0;
  let right = arr.length - 1;
  while (left <= right) {
    const mid = Math.floor((left + right) / 2);
    if (arr[mid] === target) {
      return mid; // Found the target, return its index
    } else if (arr[mid] < target) {
      left = mid + 1; // Target is in the right half of the current range
    } else {
      right = mid - 1; // Target is in the left half of the current range
    }
  }
  return -1; // Target not found in the array
}
// Example usage:
const sortedArray = [1, 3, 5, 7, 9, 11, 13, 15, 17];
const targetValue = 9;
const resultIndex = binarySearch(sortedArray, targetValue);
if (resultIndex !== -1) {
  console.log(`Target ${targetValue} found at index ${resultIndex}.`);
} else {
  console.log(`Target ${targetValue} not found in the array.`);
}
</code>
</pre>
</details>

In this implementation, the `binarySearch` function takes a sorted array (`arr`) and a target value (`target`) as inputs. It sets two pointers, `left` and `right`, initially pointing to the first and last elements of the array, respectively.

It then enters a loop that continues as long as `left` is less than or equal to `right`. In each iteration, it calculates the middle index (`mid`) of the current range. If the element at the middle index is equal to the target value, the function returns the index. If the target value is less than the element at `mid`, it updates `right` to search in the left half of the current range; otherwise, it updates `left` to search in the right half.

If the loop exits without finding the target value, the function returns `-1` to indicate that the target value is not present in the array.

The example usage demonstrates searching for the target value `9` in the sorted array. If the target value is found, it prints the index where it was found; otherwise, it indicates that the target value is not present in the array.

### Hash Tables

- A hash table is a fundamental data structure that plays a crucial role in many aspects of programming. To gain a deeper understanding of how it works and its practical applications, I highly recommend watching this informative [video](https://www.youtube.com/watch?v=LPzN8jgbnvA).

</br>

# ![Hash Tables code](https://i.imgur.com/DZrlIgL.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Hash Tables Code</summary>
   <pre style="padding: 1em 0em ">
  <code class="language-javascript">
class HashTable {
  constructor() {
    this.size = 10;
    this.keys = new Array(this.size);
    this.values = new Array(this.size);
  }
  put(key, data) {
    const index = this.hashFunction(key);
    while (this.keys[index] !== undefined) {
      if (this.keys[index] === key) {
        this.values[index] = data; // update
        return;
      }
      index = (index + 1) % this.size;
    }
    this.keys[index] = key;
    this.values[index] = data;
  }
  get(key) {
    const index = this.hashFunction(key);
    while (this.keys[index] !== undefined) {
      if (this.keys[index] === key) {
        return this.values[index];
      }
      index = (index + 1) % this.size;
    }
    return undefined;
  }
  hashFunction(key) {
    let sum = 0;
    for (let pos = 0; pos < key.length; pos++) {
      sum += key.charCodeAt(pos);
    }
    return sum % this.size;
  }
}
const t = new HashTable();
t.put("apple", 10);
t.put("orange", 20);
t.put("banana", 30);
console.log(t.get("orange"));
</code></pre>
</details>

</br>

## Graph Algorithm
</br>

### Dijkstra’s shortest path algorithm
- Dijkstra’s shortest path algorithm is an algorithm for finding the shortest path between nodes in a graph.
</br>

 ![Dijkstra’s code](https://i.imgur.com/QTvBbb0.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Dijkstra’s Code</summary>
  <pre style="padding: 1em 0em ">
  <code class="language-javascript">
const PriorityQueue = require("priorityqueuejs");
function dijkstra(graph, start) {
  const heap = new PriorityQueue((a, b) => a[0] - b[0]);
  const visited = new Set();
  heap.enq([0, start]);
  while (!heap.isEmpty()) {
    const [cost, v] = heap.deq();
    if (!visited.has(v)) {
      visited.add(v);
      for (let u in graph[v]) {
        if (!visited.has(u)) {
          heap.enq([cost + graph[v][u], u]);
        }
      }
    }
  }
  return visited;
}
const graph = {
  A: { B: 2, C: 3 },
  B: { D: 4, E: 5 },
  C: { F: 6 },
  D: { G: 7 },
  E: { G: 8, H: 9 },
  F: { H: 10 },
  G: {},
  H: {},
};
console.log(dijkstra(graph, "A"));
</code></pre>
</details>

</br>

## Dynamic Programming
</br>

### Fibonacci sequence: 

- A classic example of a problem that can be solved using dynamic programming is the Fibonacci sequence.
</br>

# ![Fibonacci  code](https://i.imgur.com/d7fSMp8.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Fibonacci Code</summary>
 <pre style="padding: 1em 0em ">
  <code class="language-javascript">
function fibonacci(n) {
  if (n <= 0) {
    return 0;
  } else if (n === 1) {
    return 1;
  } else {
    return fibonacci(n - 1) + fibonacci(n - 2);
  }
}
console.log(fibonacci(10));
</code></pre>
</details>

</br>

## Greedy Algorithms

- A greedy algorithm, aims to make the optimal choice at each step without considering the future steps. It focuses on finding the globally optimal solution locally, without looking ahead. This approach makes it fast but may not always result in the globally optimal solution. Greedy algorithms are used for various problems, including some well-known algorithms like Dijkstra's Algorithm, Kruskal's algorithm, Prim's algorithm, and Huffman trees.

To create a greedy algorithm, you need to follow the principle of choosing the optimal choice at each moment in time. For example, when counting change, you start with the highest denomination and work backward to select the coins that fit the change amount.

Here's a brief summary of the key points for this algo:

1. Greedy algorithms make locally optimal choices without considering future steps.
2. Greedy algorithms aim to find the globally optimal solution using this local approach.
3. Greedy algorithms are faster than alternatives like Divide & Conquer and Dynamic Programming.
4. Some popular algorithms that use the greedy approach include Dijkstra's Algorithm, Kruskal's algorithm, Prim's algorithm, and Huffman trees.
5. To create a greedy algorithm, follow the property of choosing the optimal choice at that exact moment in time.
6. The example of counting change demonstrates how a greedy algorithm works by starting with the highest denomination and working backward.
7. The provided Python code snippet demonstrates how to implement a greedy change-making algorithm.
8. Greedy algorithms are optimal locally but may not always be optimal globally, as shown in the example where they fail to find the best solution.

Remember that the runtime of a greedy algorithm is often dominated by the loops involved, making it O(n^2) in some cases. In situations where greedy algorithms fail to find the globally optimal solution, alternatives like Dynamic Programming may be necessary.

</br>

 ![Greedy code](https://i.imgur.com/vByWfbI.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary > <h3>Detailed explanation</h3> </summary>

1. **Definition of Greedy Algorithms:** Greedy algorithms are a class of algorithms that make locally optimal choices at each step with the hope of finding the globally optimal solution. They follow the principle of immediate gratification, focusing on what seems best at the current moment without considering the consequences of those choices on future steps.

2. **The Greedy Property:** The central idea behind greedy algorithms is the greedy property, which is defined as choosing the best option at that exact moment in time. This property guides the algorithm in making decisions, always selecting the most favorable choice available without foresight.

3. **Speed and Efficiency:** Greedy algorithms are known for their speed and efficiency. They often outperform alternative approaches like Divide & Conquer and Dynamic Programming, especially in scenarios where the globally optimal solution can be approximated effectively using local decisions.

4. **Applications:** Greedy algorithms find applications in various fields, including computer science, mathematics, and engineering. Some well-known algorithms that employ the greedy approach include:
   - Dijkstra's Algorithm for finding the shortest path in a graph.
   - Kruskal's Algorithm for finding the minimum spanning tree of a graph.
   - Prim's Algorithm for finding the minimum spanning tree of a weighted graph.
   - Huffman Trees for data compression.

5. **Designing Greedy Algorithms:** Creating a greedy algorithm involves defining the problem in such a way that you can identify the optimal choice at each step. This typically requires formulating the problem with specific constraints and objectives.

6. **Example: Counting Change:** An illustrative example of a greedy algorithm is counting change. The algorithm starts with the highest denomination and works backward, selecting coins that fit the change amount until it can no longer use a particular coin. This approach often works well in practice, as it approximates the optimal solution effectively for everyday scenarios.

7. **Algorithm Implementation:** The Python code snippet provided in the article demonstrates how to implement a greedy change-making algorithm. It uses a list to keep track of the number of each denomination of coins to return as change.

8. **Optimality of Greedy Algorithms:** While greedy algorithms excel in many cases, they are not always guaranteed to find the globally optimal solution. The article highlights an example where a greedy change-making algorithm fails to identify the best solution. In such cases, alternatives like Dynamic Programming or brute-force approaches may be required.

9. **Complexity:** The runtime complexity of a greedy algorithm often depends on the loops involved in the decision-making process. In some cases, it can be O(n^2) or worse. It's essential to analyze the specific algorithm and problem to determine its efficiency.

10. **Trade-offs:** Greedy algorithms trade off computational efficiency for the possibility of suboptimal solutions. They are suitable for problems where approximation is acceptable and speed is critical, but they may not be suitable for problems where finding the globally optimal solution is essential.

In summary, greedy algorithms are a powerful class of algorithms that make decisions based on local optimization, and they find use in a wide range of applications. While they are fast and efficient, it's crucial to be aware of their limitations and when they might not provide the best solution. In such cases, alternative algorithmic approaches should be considered.
</details>

### Below is an implementation of the Prim's algorithm in JavaScript

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Prim's algorithm Code</summary>
  <pre style="padding: 1em 0em ">
  <code class="language-javascript">
class Graph {
  constructor(vertices) {
    this.vertices = vertices;
    // Create an array to represent the graph, where each element is an adjacency list.
    this.graph = new Array(vertices).fill(null).map(() => []);
  }
  // Add an edge to the graph between source (src) and destination (dest) with a given weight.
  addEdge(src, dest, weight) {
    this.graph[src].push({ node: dest, weight });
    this.graph[dest].push({ node: src, weight });
  }
  // Function to find the Minimum Spanning Tree (MST) using Prim's algorithm.
  primMST() {
    const parent = new Array(this.vertices);
    const key = new Array(this.vertices);
    const visited = new Array(this.vertices).fill(false);
    // Initialize key and parent arrays.
    for (let i = 0; i < this.vertices; i++) {
      key[i] = Number.MAX_VALUE;
      visited[i] = false;
    }
    // Start from the first vertex.
    key[0] = 0;
    parent[0] = -1;
    // Find the MST.
    for (let count = 0; count < this.vertices - 1; count++) {
      const u = this.minKey(key, visited);
      visited[u] = true;
      // Update key and parent for adjacent vertices.
      for (const neighbor of this.graph[u]) {
        const v = neighbor.node;
        const weight = neighbor.weight;
        if (!visited[v] && weight < key[v]) {
          parent[v] = u;
          key[v] = weight;
        }
      }
    }
    // Print the Minimum Spanning Tree.
    this.printMST(parent);
  }
  // Helper function to find the vertex with the minimum key value among non-visited vertices.
  minKey(key, visited) {
    let min = Number.MAX_VALUE;
    let minIndex = -1;
    for (let v = 0; v < this.vertices; v++) {
      if (!visited[v] && key[v] < min) {
        min = key[v];
        minIndex = v;
      }
    }
    return minIndex;
  }
  // Function to print the edges of the Minimum Spanning Tree along with their weights.
  printMST(parent) {
    console.log("Edge \tWeight");
    for (let i = 1; i < this.vertices; i++) {
      console.log(`${parent[i]} - ${i} \t${this.graph[i][parent[i]].weight}`);
    }
  }
}
// Example usage
const vertices = 5;
const graph = new Graph(vertices);
// Add edges and their weights to the graph.
graph.addEdge(0, 1, 2);
graph.addEdge(0, 3, 6);
graph.addEdge(1, 2, 3);
graph.addEdge(1, 3, 8);
graph.addEdge(1, 4, 5);
graph.addEdge(2, 4, 7);
graph.addEdge(3, 4, 9);
// Find and print the Minimum Spanning Tree.
graph.primMST();
</code></pre>
</details>


</br>
</br>

## Divide and Conquer
</br>

### Merge Sort:
-  already explained above

</br>

## Backtracking
</br>

### The N-Queens Problem:
- The N-Queens problem is a classic problem that can be solved using backtracking. The goal is to place N queens on an NxN chessboard in such a way that no queen can attack any other queen.
</br>

 ![The N-Queens code](https://i.imgur.com/DFbPL8Y.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >N-Queens Code</summary>
   <pre style="padding: 1em 0em ">
  <code class="language-javascript">
var solveNQueens = function (n) {
  var res = [];
  if (n === 1 || n >= 4) dfs(res, [], n, 0);
  return res;
};
var dfs = function (res, points, n, index) {
  for (var i = index; i < n; i++) {
    if (points.length !== i) return;
    for (var j = 0; j < n; j++) {
      if (isValid(points, [i, j])) {
        points.push([i, j]);
        dfs(res, points, n, i + 1);
        if (points.length === n) res.push(buildRes(points));
        points.pop();
      }
    }
  }
};
var buildRes = function (points) {
  var res = [];
  var n = points.length;
  for (var i = 0; i < n; i++) {
    res[i] = "";
    for (var j = 0; j < n; j++) {
      res[i] += points[i][1] === j ? "Q" : ".";
    }
  }
  return res;
};
var isValid = function (oldPoints, newPoint) {
  var len = oldPoints.length;
  for (var i = 0; i < len; i++) {
    if (oldPoints[i][0] === newPoint[0] || oldPoints[i][1] === newPoint[1])
      return false;
    if (
      Math.abs(
        (oldPoints[i][0] - newPoint[0]) / (oldPoints[i][1] - newPoint[1])
      ) === 1
    )
      return false;
  }
  return true;
};
</code></pre>
</details>

The main function, `solveNQueens`, initializes an empty `res` array and calls the `dfs` function to perform the depth-first search. After the search is complete, the function returns the `res` array.

The `dfs` function takes a `res` array, a `points` array to store the positions of the queens, the board size `n`, and an `index` parameter indicating the row being considered. It iterates over the columns in the current row and checks if placing a queen at that position is valid according to the `isValid` function.

The `isValid` function determines whether placing a queen at the new point is valid by checking for conflicts with the queens already placed. It iterates through the `oldPoints` array, which contains the coordinates of previously placed queens, and checks for conflicts in row, column, and diagonal positions.

The `buildRes` function constructs a valid solution representation from the `points` array, where 'Q' represents a queen and '.' represents an empty position on the board.

Considering the `dfs` function, the worst-case time complexity occurs when all possible configurations need to be explored. This happens when the first `if` condition in the `dfs` function is met (`points.length !== i`), which causes the function to return early. In this case, the time complexity is proportional to the number of valid solutions.

For each row, the number of valid positions decreases, which reduces the branching factor. Therefore, the time complexity is not as high as O(N!), but it is still exponential. The exact time complexity of this implementation is difficult to determine precisely due to the varying number of valid positions at each row. In practice, it performs better than the straightforward backtracking solution but can still be slow for large values of N.

</br>

## Randomized Algorithm
</br>

### Randomized QuickSort: 
- A variation of quicksort algorithm where pivot is chosen randomly.
</br>

 ![Randomized QuickSort code](https://i.imgur.com/sBfWYpl.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Randomized QuickSort Code</summary>
   <pre style="padding: 1em 0em ">
  <code class="language-javascript">
function randomInt(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}
function swap(arr, i, j) {
  const temp = arr[i];
  arr[i] = arr[j];
  arr[j] = temp;
}
function partition(arr, low, high) {
  const pivotIndex = randomInt(low, high);
  const pivotValue = arr[pivotIndex];
  swap(arr, pivotIndex, high);
  let partitionIndex = low;
  for (let i = low; i < high; i++) {
    if (arr[i] < pivotValue) {
      swap(arr, i, partitionIndex);
      partitionIndex++;
    }
  }
  swap(arr, partitionIndex, high);
  return partitionIndex;
}
function quickSort(arr, low, high) {
  if (low < high) {
    const pivotIndex = partition(arr, low, high);
    quickSort(arr, low, pivotIndex - 1);
    quickSort(arr, pivotIndex + 1, high);
  }
}
// Example usage:
const arrayToSort = [9, 3, 7, 1, 5, 6, 8, 2, 4];
console.log("Original array:", arrayToSort);
quickSort(arrayToSort, 0, arrayToSort.length - 1);
console.log("Sorted array:", arrayToSort);
</code></pre>
</details>


In this implementation, `randomInt` is a helper function that generates a random integer between `min` and `max`, inclusive. The `swap` function is used to swap elements in the array. The `partition` function picks a random pivot element, places it at the end of the array, and rearranges the array so that all elements less than the pivot are on the left side, and all elements greater than or equal to the pivot are on the right side.

The `quickSort` function recursively calls itself on the left and right subarrays until the entire array is sorted.

Keep in mind that this implementation modifies the original array in place. If you want to keep the original array unchanged, you can make a copy of it and sort the copy instead.

These are some of the most commonly used algorithms that every programmer should be familiar with. Understanding these algorithms and their implementation can help a programmer to make better decisions when it comes to designing and implementing efficient solutions.

</br>

## Summary
<br />

### Sorting algorithms:

- Sorting is a fundamental operation in computer science and there are several efficient algorithms for it, such as quicksort, merge sort and heap sort.
- Quicksort is a divide-and-conquer algorithm that chooses a “pivot” element from the array and partitions the other elements into two sub-arrays, according to whether they are less than or greater than the pivot. The sub-arrays are then sorted recursively.
- The merge sort algorithm is a divide-and-conquer algorithm that divides an array in two, sorts the two halves, and then merges them back together.
- The heap sort algorithm is a comparison-based sorting algorithm that builds a heap from the input elements and then repeatedly extracts the maximum element from the heap and places it at the end of the sorted output array.
<br />

### Search algorithms:

- Binary search is an efficient algorithm for finding an item from a sorted list of items. It works by repeatedly dividing in half the portion of the array being searched, until the target value is found.
- A hash table is a data structure that maps keys to values, using a hash function to compute an index into an array of buckets or slots, from which the desired value can be found.

<br />

###  Graph algorithms:

- Graph algorithms are used to solve problems related to graphs, such as finding the shortest path between two nodes or determining if a graph is connected.
- Dynamic programming is a technique used to solve problems by breaking them down into smaller subproblems.
- The Fibonacci sequence is a classic example of a problem that can be solved using dynamic programming.

<br />

### Dynamic programming:

- Dynamic programming is a technique for solving problems by breaking them down into smaller subproblems and storing the solutions to these subproblems to avoid redundant computation.
<br />

### Greedy algorithms:

- Greedy algorithms are used to solve optimization problems by making the locally optimal choice at each step with the hope of finding a global optimum.
- Huffman coding is a lossless data compression algorithm that uses a greedy algorithm to construct a prefix code for a given set of symbols.
- It works by assigning shorter codes to more frequently occurring symbols.
<br />

### Divide and Conquer:

- Divide and Conquer is an algorithm design paradigm based on multi-branched recursion. A divide and conquer algorithm breaks down a problem into sub-problems of the same or related type, until these become simple enough to be solved directly.
- Merge sort is a sorting algorithm that uses the divide and conquer technique.
- It works by dividing the input array into smaller subarrays, sorting them, and then merging them back together.
<br />

### Backtracking:

- Backtracking is a general algorithmic technique that considers searching every possible combination in a systematic manner, and abandons a particular path as soon as it determines that it cannot be part of the solution.
- The N-Queens problem is a classic problem that can be solved using backtracking.
- The goal is to place N queens on an NxN chessboard in such a way that no queen can attack any other queen.
<br />

### Randomized Algorithm:

- Randomized algorithms use randomness to solve a problem. It can be useful to solve problems that cannot be solved deterministically or to improve the average case complexity of a problem.
- Randomized quicksort is a variation of the quicksort algorithm where the pivot is chosen randomly.
- It works by partitioning the array around the pivot and then recursively sorting the subarrays.
<br />

### Hash Tables:

- Hash tables are a data structure that allows for efficient lookup, insertion, and deletion of key-value pairs.
- They work by using a hash function to map keys to indices in an array.
<br />

### Dijkstra's Shortest Path Algorithm:

- Dijkstra's algorithm is used to find the shortest path between nodes in a graph.
- It uses a priority queue to keep track of the nodes with the shortest distance from the starting node.
<br />

## Conclusion

Data structures are the building blocks of efficient algorithms and problem-solving in computer science. While they might appear complex initially, with practice and the right guidance, you'll soon find yourself embracing their power and using them to create elegant and efficient solutions.

So, why wait? Start your data structure journey today and unlock the true potential of your coding skills. Remember, it's not just about mastering algorithms; it's about becoming a better problem solver and a skilled software engineer. Happy coding!

## Acknowledgements

Sites used for visualizations:

- [Visualgo](https://visualgo.net/en) - Visualgo website
- [Heap Visualization by Ben Frederickson](https://www.benfrederickson.com/heap-visualization/) - Heap Visualization by Ben Frederickson
- [Pathfinding Visualizer by Clement Mihailescu](https://clementmihailescu.github.io/Pathfinding-Visualizer/#) - Pathfinding Visualizer by Clement Mihailescu
- [CSVISTool](https://csvistool.com/) - CSVISTool website
- [Algorithms Visualization by cs.usfca.edu](https://www.cs.usfca.edu/~galles/visualization/Algorithms.html) - Algorithms Visualization by cs.usfca.edu