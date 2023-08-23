---
title: Demystifying Data Structures A Beginner-Friendly Guided
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

Now that we got the base essentials out of the way. we can look further into the horizon and take a gander at some of the most important Algos there are.  The main goal of an algorithm is to take in input, process it and provide an output that is expected. Algorithms can be classified based on the time and space complexity, the technique used for solving the problem, and the type of problem it solves. Examples of algorithm are sorting, searching, graph traversals, string manipulations, mathematical operations, and many more.

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

- Quicksort: Quicksort is a divide-and-conquer algorithm that chooses a “pivot” element from the array and partitions the other elements into two sub-arrays, according to whether they are less than or greater than the pivot. The sub-arrays are then sorted recursively.

```js
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

```

- Merge Sort: The merge sort algorithm is a divide-and-conquer algorithm that divides an array in two, sorts the two halves, and then merges them back together.

```js
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

```

- Heap Sort: The heap sort algorithm is a comparison-based sorting algorithm that builds a heap from the input elements and then repeatedly extracts the maximum element from the heap and places it at the end of the sorted output array.

```js
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
    let left = 2 * i + 1;
    let right = 2 * i + 2;

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

```

## Search algorithms

- Binary Search: Binary search is an efficient algorithm for finding an item from a sorted list of items. It works by repeatedly dividing in half the portion of the array being searched, until the target value is found.

```javascript
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
```

In this implementation, the `binarySearch` function takes a sorted array (`arr`) and a target value (`target`) as inputs. It sets two pointers, `left` and `right`, initially pointing to the first and last elements of the array, respectively.

It then enters a loop that continues as long as `left` is less than or equal to `right`. In each iteration, it calculates the middle index (`mid`) of the current range. If the element at the middle index is equal to the target value, the function returns the index. If the target value is less than the element at `mid`, it updates `right` to search in the left half of the current range; otherwise, it updates `left` to search in the right half.

If the loop exits without finding the target value, the function returns `-1` to indicate that the target value is not present in the array.

The example usage demonstrates searching for the target value `9` in the sorted array. If the target value is found, it prints the index where it was found; otherwise, it indicates that the target value is not present in the array.

- Hash Tables: A hash table is a data structure that maps keys to values, using a hash function to compute an index into an array of buckets or slots, from which the desired value can be found.

```js
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

```

## Graph Algorithm

- Dijkstra’s shortest path algorithm: Dijkstra’s shortest path algorithm is an algorithm for finding the shortest path between nodes in a graph.

```js
const PriorityQueue = require('priorityqueuejs');

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
    'A': { 'B': 2, 'C': 3 },
    'B': { 'D': 4, 'E': 5 },
    'C': { 'F': 6 },
    'D': { 'G': 7 },
    'E': { 'G': 8, 'H': 9 },
    'F': { 'H': 10 },
    'G': {},
    'H': {}
};

console.log(dijkstra(graph, 'A'));
```

## Dynamic Programming

- Fibonacci sequence: A classic example of a problem that can be solved using dynamic programming is the Fibonacci sequence.

```js
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

```

## Greedy Algorithms

- Huffman coding is a lossless data compression algorithm that uses a greedy approach to construct a prefix code for a given set of symbols. It assigns variable-length codes to characters based on their frequency in the input data. The main idea is to give shorter codes to characters that appear more frequently and longer codes to characters that appear less often. This variable-length coding leads to a more efficient representation of the data during compression.

In other words, Huffman coding adapts its encoding scheme dynamically, tailoring it to the specific input data. Characters that occur more frequently, such as common letters in a text, are represented with shorter codes, reducing the overall size of the compressed data. On the contrary, less frequent characters, like rare symbols, receive longer codes, which may use more bits but are compensated by the savings achieved for frequently occurring characters.

By constructing a prefix code, Huffman coding ensures that each code assigned to a character is not a prefix of another code, preventing ambiguity during decoding. This clever design guarantees that when the compressed data is decompressed, we get back the exact original data without any loss of information. Thus, Huffman coding achieves efficient data compression while preserving data integrity.

### Detailed explanation

Huffman coding is a lossless data compression algorithm: Lossless means that when we compress the data using Huffman coding and then decompress it, we get back the exact same original data without any loss of information. In other words, no data is lost during the compression and decompression process.

that uses a greedy algorithm: A greedy algorithm is a method that makes the best choice at each step, without worrying about the overall result. In the case of Huffman coding, the algorithm makes decisions by focusing on the most immediate benefit, which is assigning shorter codes to more frequently occurring characters.

to construct a prefix code for a given set of symbols: A prefix code is a type of encoding where no code word (sequence of bits) is a prefix of another code word. In simple terms, each character's code is not the starting part of another character's code. This is important to avoid any ambiguity when decoding the compressed data. The Huffman coding algorithm constructs such a prefix code for a set of symbols, where each symbol represents a character from the input data.

Huffman coding assigns variable-length codes to characters based on their frequency in the input data: Instead of using fixed-length codes for each character (e.g., using 8 bits for each character), Huffman coding assigns shorter codes to characters that appear more frequently and longer codes to characters that appear less frequently. This dynamic assignment of code lengths allows more efficient compression because frequently occurring characters get shorter codes, reducing the overall size of the compressed data.

Characters that occur more frequently are assigned shorter codes, while less frequent characters are assigned longer codes: This statement further emphasizes that Huffman coding adapts its encoding based on the frequency of characters in the input data. Popular characters, which occur more often, are represented using shorter codes, reducing the size of the compressed data. On the other hand, less frequent characters, which occur rarely, are represented using longer codes, which may use more bits but are offset by the savings achieved for frequently occurring characters.

Overall, Huffman coding is an intelligent data compression technique that efficiently represents data by assigning shorter codes to common characters and longer codes to less common characters, resulting in a compressed data representation without any loss of information during compression and decompression.

### Below is an implementation of the Huffman coding algorithm in JavaScript

```javascript
class Node {
  constructor(char, freq) {
    this.char = char;
    this.freq = freq;
    this.left = null;
    this.right = null;
  }
}

function buildFrequencyTable(str) {
  const frequencyTable = {};

  for (let char of str) {
    frequencyTable[char] = (frequencyTable[char] || 0) + 1;
  }

  return frequencyTable;
}

function buildHuffmanTree(frequencyTable) {
  const priorityQueue = [];
  for (let char in frequencyTable) {
    const node = new Node(char, frequencyTable[char]);
    priorityQueue.push(node);
  }
  priorityQueue.sort((a, b) => a.freq - b.freq);

  while (priorityQueue.length > 1) {
    const left = priorityQueue.shift();
    const right = priorityQueue.shift();
    const newNode = new Node(null, left.freq + right.freq);
    newNode.left = left;
    newNode.right = right;
    priorityQueue.push(newNode);
    priorityQueue.sort((a, b) => a.freq - b.freq);
  }

  return priorityQueue[0];
}

function buildHuffmanCodes(node, code = '', huffmanCodes = {}) {
  if (node.char !== null) {
    huffmanCodes[node.char] = code;
  } else {
    buildHuffmanCodes(node.left, code + '0', huffmanCodes);
    buildHuffmanCodes(node.right, code + '1', huffmanCodes);
  }

  return huffmanCodes;
}

function huffmanEncode(str, huffmanCodes) {
  let encodedStr = '';
  for (let char of str) {
    encodedStr += huffmanCodes[char];
  }
  return encodedStr;
}

function huffmanDecode(encodedStr, huffmanTree) {
  let decodedStr = '';
  let currentNode = huffmanTree;

  for (let bit of encodedStr) {
    if (bit === '0') {
      currentNode = currentNode.left;
    } else {
      currentNode = currentNode.right;
    }

    if (currentNode.char !== null) {
      decodedStr += currentNode.char;
      currentNode = huffmanTree;
    }
  }

  return decodedStr;
}

// Example usage:
const inputString = 'huffman coding example';
const frequencyTable = buildFrequencyTable(inputString);
const huffmanTree = buildHuffmanTree(frequencyTable);
const huffmanCodes = buildHuffmanCodes(huffmanTree);
const encodedString = huffmanEncode(inputString, huffmanCodes);
const decodedString = huffmanDecode(encodedString, huffmanTree);

console.log('Original string:', inputString);
console.log('Encoded string:', encodedString);
console.log('Decoded string:', decodedString);
```

In this implementation, we define a `Node` class to represent the nodes in the Huffman tree. The `buildFrequencyTable` function creates a frequency table based on the input string. The `buildHuffmanTree` function constructs the Huffman tree using a priority queue. The `buildHuffmanCodes` function recursively builds the Huffman codes for each character in the tree. The `huffmanEncode` function encodes the input string using the generated Huffman codes. The `huffmanDecode` function decodes the encoded string using the Huffman tree.

## Divide and Conquer

- Merge Sort: already explained above

## Backtracking

- The N-Queens Problem: The N-Queens problem is a classic problem that can be solved using backtracking. The goal is to place N queens on an NxN chessboard in such a way that no queen can attack any other queen.

```js
var solveNQueens = function(n) {
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
    res[i] = '';
    for (var j = 0; j < n; j++) {
      res[i] += (points[i][1] === j ? 'Q' : '.');
    }
  }
  return res;
};

var isValid = function (oldPoints, newPoint) {
  var len = oldPoints.length;
  for (var i = 0; i < len; i++) {
    if (oldPoints[i][0] === newPoint[0] || oldPoints[i][1] === newPoint[1]) return false;
    if (Math.abs((oldPoints[i][0] - newPoint[0]) / (oldPoints[i][1] - newPoint[1])) === 1) return false;
  }
  return true;
};
```

The main function, `solveNQueens`, initializes an empty `res` array and calls the `dfs` function to perform the depth-first search. After the search is complete, the function returns the `res` array.

The `dfs` function takes a `res` array, a `points` array to store the positions of the queens, the board size `n`, and an `index` parameter indicating the row being considered. It iterates over the columns in the current row and checks if placing a queen at that position is valid according to the `isValid` function.

The `isValid` function determines whether placing a queen at the new point is valid by checking for conflicts with the queens already placed. It iterates through the `oldPoints` array, which contains the coordinates of previously placed queens, and checks for conflicts in row, column, and diagonal positions.

The `buildRes` function constructs a valid solution representation from the `points` array, where 'Q' represents a queen and '.' represents an empty position on the board.

Considering the `dfs` function, the worst-case time complexity occurs when all possible configurations need to be explored. This happens when the first `if` condition in the `dfs` function is met (`points.length !== i`), which causes the function to return early. In this case, the time complexity is proportional to the number of valid solutions.

For each row, the number of valid positions decreases, which reduces the branching factor. Therefore, the time complexity is not as high as O(N!), but it is still exponential. The exact time complexity of this implementation is difficult to determine precisely due to the varying number of valid positions at each row. In practice, it performs better than the straightforward backtracking solution but can still be slow for large values of N.

## Randomized Algorithm

Randomized QuickSort: A variation of quicksort algorithm where pivot is chosen randomly.

```javascript
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
```

In this implementation, `randomInt` is a helper function that generates a random integer between `min` and `max`, inclusive. The `swap` function is used to swap elements in the array. The `partition` function picks a random pivot element, places it at the end of the array, and rearranges the array so that all elements less than the pivot are on the left side, and all elements greater than or equal to the pivot are on the right side.

The `quickSort` function recursively calls itself on the left and right subarrays until the entire array is sorted.

Keep in mind that this implementation modifies the original array in place. If you want to keep the original array unchanged, you can make a copy of it and sort the copy instead.

These are some of the most commonly used algorithms that every programmer should be familiar with. Understanding these algorithms and their implementation can help a programmer to make better decisions when it comes to designing and implementing efficient solutions.

## Summary

1. Sorting algorithms:

- Sorting is a fundamental operation in computer science and there are several efficient algorithms for it, such as quicksort, merge sort and heap sort.
- Quicksort is a divide-and-conquer algorithm that chooses a “pivot” element from the array and partitions the other elements into two sub-arrays, according to whether they are less than or greater than the pivot. The sub-arrays are then sorted recursively.
- The merge sort algorithm is a divide-and-conquer algorithm that divides an array in two, sorts the two halves, and then merges them back together.
- The heap sort algorithm is a comparison-based sorting algorithm that builds a heap from the input elements and then repeatedly extracts the maximum element from the heap and places it at the end of the sorted output array.

2. Search algorithms:

- Binary search is an efficient algorithm for finding an item from a sorted list of items. It works by repeatedly dividing in half the portion of the array being searched, until the target value is found.
- A hash table is a data structure that maps keys to values, using a hash function to compute an index into an array of buckets or slots, from which the desired value can be found.

3. Graph algorithms:

- Graph algorithms are used to solve problems related to graphs, such as finding the shortest path between two nodes or determining if a graph is connected.
- Dynamic programming is a technique used to solve problems by breaking them down into smaller subproblems.
- The Fibonacci sequence is a classic example of a problem that can be solved using dynamic programming.

4. Dynamic programming:

- Dynamic programming is a technique for solving problems by breaking them down into smaller subproblems and storing the solutions to these subproblems to avoid redundant computation.

5. Greedy algorithms:

- Greedy algorithms are used to solve optimization problems by making the locally optimal choice at each step with the hope of finding a global optimum.
- Huffman coding is a lossless data compression algorithm that uses a greedy algorithm to construct a prefix code for a given set of symbols.
- It works by assigning shorter codes to more frequently occurring symbols.

6. Divide and Conquer:

- Divide and Conquer is an algorithm design paradigm based on multi-branched recursion. A divide and conquer algorithm breaks down a problem into sub-problems of the same or related type, until these become simple enough to be solved directly.
- Merge sort is a sorting algorithm that uses the divide and conquer technique.
- It works by dividing the input array into smaller subarrays, sorting them, and then merging them back together.

7. Backtracking:

- Backtracking is a general algorithmic technique that considers searching every possible combination in a systematic manner, and abandons a particular path as soon as it determines that it cannot be part of the solution.
    - - The N-Queens problem is a classic problem that can be solved using backtracking.
- The goal is to place N queens on an NxN chessboard in such a way that no queen can attack any other queen.

8. Randomized Algorithm:

- Randomized algorithms use randomness to solve a problem. It can be useful to solve problems that cannot be solved deterministically or to improve the average case complexity of a problem.
- Randomized quicksort is a variation of the quicksort algorithm where the pivot is chosen randomly.
- It works by partitioning the array around the pivot and then recursively sorting the subarrays.

9. Hash Tables:

- Hash tables are a data structure that allows for efficient lookup, insertion, and deletion of key-value pairs.
- They work by using a hash function to map keys to indices in an array.

10. Dijkstra's Shortest Path Algorithm:

- Dijkstra's algorithm is used to find the shortest path between nodes in a graph.
- It uses a priority queue to keep track of the nodes with the shortest distance from the starting node.

## Conclusion

Data structures are the building blocks of efficient algorithms and problem-solving in computer science. While they might appear complex initially, with practice and the right guidance, you'll soon find yourself embracing their power and using them to create elegant and efficient solutions.

So, why wait? Start your data structure journey today and unlock the true potential of your coding skills. Remember, it's not just about mastering algorithms; it's about becoming a better problem solver and a skilled software engineer. Happy coding!
